# Webjocke's agent skills

Reusable, opinionated skills for AI coding agents. Each skill is self-contained
and follows the open [Agent Skills specification](https://agentskills.io/).

## Skills

### `code-style`

A practical code-writing and refactoring guide that favors locality, minimal
indirection, small durable state, and code whose main flow is easy to follow.
It also includes a focused self-review checklist for simplifying completed
changes.

## Installation

List the skills available in this repository:

```sh
npx skills add webjocke/skills --list
```

Install `code-style`:

```sh
npx skills add webjocke/skills --skill code-style
```

The skills use the portable `SKILL.md` format and can be installed by agents
that support the Agent Skills specification.
