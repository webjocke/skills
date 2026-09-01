---
name: code-style
description: Write and refactor application code with minimal indirection, local logic, small durable state, and deliberate self-review. Use when implementing features, simplifying code, designing persistence, or reviewing a completed change.
---

# Code Style

Write code that a reader can understand with few jumps and little ceremony.
When principles conflict, prefer the option that makes the behavior easiest to
follow in its real context.

## 1. Put tunable values in configuration

A value belongs in configuration when it could plausibly change without
changing the surrounding logic: timeouts, limits, external URLs, retry counts,
or feature toggles.

```ts
// config.ts
export const appConfig = {
  http: { requestTimeoutMs: 10_000 },
};

// api-client.ts
const response = await fetch(url, {
  signal: AbortSignal.timeout(appConfig.http.requestTimeoutMs),
});
```

Keep a value inline when changing it would require rethinking the operation
anyway, such as an HTTP status code or a slice length required by a fixed wire
format. Moving every literal into configuration hurts locality.

## 2. Remove pass-through wrappers

Delete functions that only forward arguments or add a trivial fixed option.
Call the defining operation directly and keep the small detail at the call
site.

```ts
// Avoid: callers should use issueTracker.listIssues(...) directly.
async function listOpenIssues(projectId: string) {
  return issueTracker.listIssues(projectId, { state: "open" });
}
```

The same applies to proxy re-exports and type aliases that only rename another
type. Keep them only when they form a deliberate architectural boundary.

## 3. Avoid layer ceremony

For a simple operation, perform the work directly at the boundary, including
validation and SQL. Do not create service, repository, or manager layers merely
to relay the same operation.

```ts
routes.post("/api/projects/:id/name", async (req) => {
  const { name } = z
    .object({ name: z.string().trim().min(1) })
    .parse(await req.json());

  await sql`
    update projects
    set name = ${name}
    where id = ${req.params.id}
  `;

  return Response.json({ ok: true });
});
```

A shared query or service is justified when it enforces a rule that must not
drift, serves several genuinely different callers, or is large enough to
obscure the main flow.

## 4. Build only what the change needs

Avoid single-implementation interfaces, factories, dependency-injection
containers, error-class hierarchies, and speculative extension points. Every
function, file, and type should earn its existence.

If deleting an abstraction and inlining its body makes the code easier to
follow without losing an important boundary, delete it.

## 5. Keep the main flow visible

Reading a handler, job, command, or component from top to bottom should reveal
the feature's complete story. Keep the logic that defines the feature there.

Extracted functions should be leaves rather than links in a call chain. Good
leaf helpers handle cross-cutting concerns, reusable parsing, or one genuinely
large sub-step; they should not conceal the sequence of the main operation.

```text
Avoid:
handler -> executeChange -> validateChange -> loadRecord -> saveRecord

Prefer:
handler
  requireSession(...)     // cross-cutting leaf
  validate input
  load and update record
  return response
```

## 6. Optimize for locality

Keep things used together close together: a callee near its caller, constants
near the operation they tune, and parsing at the boundary where shaped data is
first consumed. Order files so their main behavior reads from top to bottom.

Move code away from its usage only for a concrete reason, such as reuse,
independent complexity, or a stable architectural boundary.

## 7. Split files by cohesive behavior, not technical layer

Start with one file for a small domain. A single `notifications.ts` containing
preference lookup, message selection, and delivery is often easier to follow
than separate repository, service, and dispatcher files.

Split a part out when it becomes genuinely large and can be understood as a
cohesive sub-feature, such as moving report rendering into `report-pdf.tsx`.
Avoid splitting solely into technical layers such as `routes.ts`, `service.ts`,
and `repository.ts`.

## 8. Remove relay variables without compressing intent

Prefer direct composition over intermediate variables that only pass a value
between steps.

```ts
// Unnecessary relay variables
const rows = await sql`select * from users where id = ${id}`;
const row = rows[0];
const user = userSchema.parse(row);
return user;

// Direct, while still readable
return userSchema.parse(
  (await sql`select * from users where id = ${id}`)[0],
);
```

An intermediate variable is useful when its name adds domain meaning, captures
a real combined condition such as `isOverdue`, or makes a complex expression
substantially easier to read. Do not compress code into lines that require
rereading.

## 9. Deduplicate when drift would be a bug

Extract shared code when copies must remain identical for correctness, such as
authorization checks, validation rules, calculations, or protocol invariants.
Duplicating a little unimportant boilerplate can be clearer than introducing an
abstraction.

Repeated volume is another valid trigger: when the same non-flow code appears
in many places, a shared helper can reduce the total amount a reader must
understand.

## 10. Keep durable state small and derive the rest

Persist the smallest set of facts that explains the system. Derive values that
can be calculated reliably instead of storing fields that must be synchronized.

```ts
// Two values that can disagree
project.openTaskCount;
project.tasks;

// One durable collection, one derived value
const openTaskCount = project.tasks.filter(
  (task) => task.status !== "completed",
).length;
```

Persist derived state when calculation cost, query patterns, or an explicit
historical decision makes it necessary. Treat duplicated state as a design
smell until that reason is clear.

## 11. Store raw facts first and snapshot deliberately

When data enters through an API, webhook, import, or user action, preserve the
durable fact before reducing it to today's interpretation. This lets future
logic change without rewriting history.

Use a snapshot when an accepted record must not change under future code or
configuration. An accepted price quote, for example, should retain its currency,
line items, and totals rather than recalculate them from the current product
catalog.

When adding persisted fields, ask whether each one is a raw fact, a deliberate
snapshot, or derived state stored only for convenience. The last category needs
a concrete justification.

## 12. Prefer single-write state transitions

Shape workflows so a state change is usually represented by one insert or one
update. After that write commits, other behavior should be derived from the
durable result.

Transactions remain appropriate for real cross-record invariants. If a feature
needs several coordinated writes only to keep duplicated state synchronized,
first consider removing the duplication or choosing one record as the durable
fact.

Useful default shapes include:

- insert one audit event and derive downstream notifications from it;
- update one import job with the result of an attempt;
- insert one accepted quote as the immutable commercial snapshot.

## 13. Perform a simplification pass

After the behavior works, reread the complete diff and simplify it. Look for:

- one-use helpers that are clearer inline;
- pass-through wrappers and proxy re-exports;
- variables that only rename or relay a value;
- layers or files introduced from habit;
- duplicated persisted state that can be derived;
- raw input discarded before a durable fact exists;
- transactions that only synchronize avoidable duplicate state;
- dead code left behind by the change.

The code should become shorter because unnecessary structure disappeared, not
because intent was compressed.

## 14. Surface out-of-scope architecture changes

Apply simplifications that are naturally within the current task. When a change
reveals a larger architectural cleanup outside that scope, explain the concrete
opportunity and ask for a clear decision before expanding the work.

For example: "The new derived count makes the `project_statistics` table
redundant. Should I remove that table and its writers?"

Do not silently perform the larger refactor, but do not leave the discovery as
an easy-to-miss aside either.
