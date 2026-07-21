Quickstart:

```bash
npx skills add toxicgozen/matt-skills --skill=to-spec
```

```bash
npx skills update to-spec
```

[Source](https://github.com/toxicgozen/matt-skills/tree/main/skills/engineering/to-spec)

## What it does

`to-spec` turns the current conversation and your codebase understanding into a spec (you may know this document as a PRD), using the destination and shape declared by the current project.

It does **not** interview you again. By the time you reach for it, the alignment work is done — `to-spec` synthesises what is already known rather than asking a fresh round of questions.

## When to reach for it

You invoke this by typing `/to-spec` — the agent won't reach for it on its own.

Reach for it once a change has been talked through and the domain language is settled, and you want that shared understanding written down before any code is written. If you *haven't* aligned yet, grill first — for that, use [grill-with-docs](https://aihero.dev/skills-grill-with-docs). To split the finished spec into tickets, use [to-tickets](https://aihero.dev/skills-to-tickets).

## Prerequisites

When the repo has its own spec contract, `to-spec` reads that contract before writing. Without one, it returns the fallback spec in the conversation. It never creates an external issue or applies tracker labels unless you explicitly request external publication in the current task.

## What the spec includes

- **Problem statement** — what is broken or missing, and why it's worth solving, in the project's own vocabulary.
- **Solution** — the shape of the fix at a high level, before any implementation detail.
- **User stories** — a prioritized list of the concrete behaviours the change must support, each one independently checkable and included only when it adds signal.
- **Implementation decisions** — the choices already settled during the conversation, so they aren't relitigated later.
- **Testing decisions** — the seams the feature will be tested at, and what "done" looks like.
- **Out-of-scope items** — what this change deliberately does *not* cover, to keep the ticket bounded.
- **Further notes** — anything else worth carrying forward that doesn't fit the sections above.

## Deep modules

Before writing the spec, `to-spec` sketches the **seams** at which the feature will be tested and looks for **deep module** opportunities — a lot of functionality hidden behind a small, stable interface. It prefers existing seams to new ones and the highest seam possible, ideally just one across the whole change.

That matters for agentic development: a good interface gives tests something durable to target, so the code underneath can change without the tests moving.

## It's working if

- It starts writing the spec instead of asking you a fresh round of questions.
- It checks material seam decisions with you before writing, and proposes as few as possible.
- The spec comes back in your project's domain vocabulary, not generic boilerplate.
- The spec lands in the project-declared destination without an implicit external write.

## Where it fits

`to-spec` is a step in the main build chain:

```txt
grill-with-docs → to-spec → to-tickets → implement → code-review
```

Reach for it after the plan and domain language are resolved, and before you break the work into implementation tickets. Its key neighbours are [grill-with-docs](https://aihero.dev/skills-grill-with-docs), which sharpens the context so the spec is precise, and [to-tickets](https://aihero.dev/skills-to-tickets), which turns the spec into a set of tickets for [implement](https://aihero.dev/skills-implement) to build. When you're unsure which skill or flow fits, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
