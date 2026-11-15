---
name: commit-and-pr
description: Write a commit message, a pull request title and description, an issue, or a review comment. Use before drafting any of these.
---

# Commit and pull request text

A project's own convention or template comes first. This is the default without one.

**The reader** is a reviewer or a later maintainer. They have the diff open and have not
seen the conversation. The diff already shows what changed, line by line. The text gives
what the diff cannot: why the change exists, how to find one's way through it, what was
verified, and what is undecided. Whatever the diff, the code, or a linked document already
says is left out. That is what sets the length.

## Commit

- Subject: `type(scope): summary` in Conventional Commits form, imperative, naming what the
  change does.
- No body when the subject carries the what and the why. Otherwise add the why in a
  sentence or two of plain text.
- End with the co-author trailer from the global instructions.

```
fix(config): reject duplicate keys in a section

A repeated key silently kept the last value, which hid typos in deployed files.
```

## Pull request

The title has the form of a commit subject. The body has these parts, in this order, each
present only when it has something to say:

1. **Goal.** What was wrong or missing, and what is true after the change.
2. **Change.** The approach in a sentence, and where a reviewer should look closely. Not a
   list of files.
3. **Verification.** What was run and its result, including what was not run.
4. **Open questions.** What you want the reviewer to decide or look at.

The body reports. It does not argue that the solution is right, praise it, list rejected
alternatives, or retell how the work went. A reviewer who doubts the approach will ask.

```
A key repeated within one section silently kept its last value, so a typo in a deployed
file went unnoticed. Loading now fails with the line numbers of both occurrences.

The check is in parse_section() in config/parser.py. Keys repeated across sections are
still allowed.

pytest tests/test_parser.py passes. Not tried against the production files.

Should this be a warning for one release before it becomes an error?
```

These two show the form, not wording to reuse. That body is ordinary for a change of that
size. A one-line fix needs one line, and a
change that touches several subsystems needs more. A draft that runs long usually restates
the diff or defends the solution, so remove that. If it is still long, the change is
probably several changes, and saying so is more useful than describing them all.

An issue follows the same parts: goal, what is known, open questions.

## Before showing it

- Read it as someone who never saw the conversation. It does not mention the request or
  these instructions, names nothing they have not seen, holds nothing private, and keeps
  the public links they need.
- Replace every placeholder with its value.
- Make each claim match the diff and the command output.
- End a pull request, issue, or comment with the signature from the global instructions.

This skill does not publish.
