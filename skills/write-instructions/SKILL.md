---
name: write-instructions
description: Write or revise standing instructions for an agent, meaning a skill or a global or project CLAUDE.md. Use when creating or editing a skill or instruction file, or when told to fix the instructions after a correction.
---

# Write instructions

The reader cannot ask what was meant and acts on every word. Numbers are entries in
[05 Rules](../../book/05-rules.md).

**Before writing.** State the behaviour wanted and the behaviour without the rule. If they
match, write nothing (5.8). Read the rules already covering the case (5.6). Place the rule:
global `CLAUDE.md` if it holds in every session, a project `CLAUDE.md` if it holds in one
repository, a skill if it is a procedure for some tasks, the book if it explains a failure, a decision if it is the maintainer's choice.

**A rule:**

- names its actor, object, and occasion (5.9),
- states the action wanted (5.10),
- names the goal, not a quality word such as "simplest" or "concise" that stands for it (5.7),
- uses a verb sized for the response wanted (5.2),
- gives its reason in a clause when that decides unnamed cases (5.3),
- uses one term per thing (5.4),
- is a plain imperative, with "must" and "never" kept for rules without exception (5.5),
- is one idea per sentence.

**From a correction.** State in one sentence what the agent did and what was wanted. Find
why no rule prevented it: missing, worded for a different action, or contradicted. Make the
smallest edit that would have prevented it, preferring a reworded rule to a new one. Word
it as the general behaviour, without the incident's details. Edit the global file unless
told otherwise, and ask the maintainer before deleting a rule.

**Revising.** Replace the rule with one worded for the behaviour wanted (5.1), then reread
the whole file for contradiction and repetition. A revision that only adds lines is a patch.

**A skill** is `skills/<name>/SKILL.md`. `name` is lowercase letters, digits, and hyphens,
and equals the directory name. `description` is third person, at most 1,024 characters, and
says what the skill does and when to use it: the agent sees only that line when choosing.
In this repository, cite the book as `../../book/<chapter>.md`, and run `bin/install --apply`
after adding or renaming a skill.

**Check.** For each sentence, name the action it causes, and delete a sentence that causes
none: the whole file is read on every load, and a longer one is followed less well (5.8).
Answer each Check in chapter 05. Show the change as a diff.
