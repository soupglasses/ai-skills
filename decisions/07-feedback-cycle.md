# 07 The maintainer starts the feedback cycle

Decided 2026-11-14.

**Decision.** When a correction shows a gap in the agent's instructions, the agent may
suggest the fix in one sentence. The maintainer decides, and when told to fix its
instructions, the agent edits the book, a skill, or the global instructions with
`write-instructions` and shows the diff.

**Why.** The maintainer chooses which corrections become rules.

**Carried by.** `instructions/CLAUDE.md` (The work), `skills/write-instructions`.
