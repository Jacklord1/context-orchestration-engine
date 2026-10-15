# ARCHITECTURE.md template

How the parts fit together: overview, data, components, integrations
and constraints. Prose comes first. Add a diagram only where the
prose can't carry it.

A non-technical project can use this for how the moving parts
connect (people, suppliers, handoffs), or leave it as
`_To be populated_`.

## Template

```markdown
# {Project} — ARCHITECTURE

## 1. Overview
{1–2 paragraphs: what hosts what, what talks to what, where the
trust boundaries are.}

## 2. Data
{The main things the system stores and how they relate. Point to
the real schema in code; don't copy it here.}

## 3. Components
### {Component}
{What it does, where it runs, how it fails.}

## 4. Integrations
{External systems: inbound webhooks, outbound APIs, scheduled
syncs.}

## 5. Cross-cutting concerns
- **Auth:** {model}
- **Backups:** {what, where}
- **Privacy:** {what personal data, where it lives}

## 6. Constraints
{Hard limits: where data has to live, budget, latency, regulation.}

## 7. Specs
- [specs/{topic}-v{n}.md](./specs/{topic}-v{n}.md) — {what it
  covers}
```

## How to use it

- **Reference, don't inline.** Long designs belong in `specs/`, and
  ARCHITECTURE explains how they fit together.
- **Past about 600 lines, split it.** Keep the overview here and
  move component detail to `specs/`. Log the split in DECISIONS.

## What goes here and what goes elsewhere

- **ARCHITECTURE:** how things connect.
- **STACK:** what the things are.
- **RUNBOOK:** how to operate them.
- **Code repo:** the actual schema and config.
