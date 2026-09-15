# Webjocke's agent skills

Reusable, opinionated skills for AI coding agents. Each skill is self-contained
and follows the open [Agent Skills specification](https://agentskills.io/).
The skills use the portable `SKILL.md` format and can be installed by agents
that support the specification.

## Skills

List the skills available in this repository:

```sh
npx skills add webjocke/skills --list
```

### `code-style`

A practical code-writing and refactoring guide that favors locality, minimal
indirection, small durable state, and code whose main flow is easy to follow.
It also includes a focused self-review checklist for simplifying completed
changes.

Read the [full skill](skills/code-style/SKILL.md).

Install `code-style`:

```sh
npx skills add webjocke/skills --skill code-style
```

### `spiris-bookkeeping`

A Swedish-language workflow for reviewing and completing unfinished bookkeeping
in Spiris, including unmatched bank transactions, uploaded receipts, unposted
drafts, and invoice due dates. It uses Spiris MCP first and the browser when MCP
support is unavailable, checks comparable bookkeeping history, and presents a
numbered action plan for explicit approval before making bookkeeping changes.
The skill includes standing permission to reclassify clearly identified,
unresolved uploads as receipts or supplier invoices.

Read the [full skill](skills/spiris-bookkeeping/SKILL.md).

Install `spiris-bookkeeping`:

```sh
npx skills add webjocke/skills --skill spiris-bookkeeping
```
