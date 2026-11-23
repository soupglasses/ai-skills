---
name: commit-and-pr
description: Write a commit message, a pull request title and description, an issue, or a review comment, and merge a pull request. Use before drafting any of these or merging.
---

# Commits and pull requests

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

Open a pull request against the default branch when the work is meant for review and
merge. Open it as a draft only when it is plainly unfinished; pending checks are no reason
for a draft. Avoid stacking a pull request on another open one. When a later push makes a
claim in the body untrue, update the body.

An issue follows the same parts: goal, what is known, open questions.

## Review comment

- Comment only on a problem you can show in the changed lines. Leave out praise, guesses,
  and anything outside the change.
- Name the problem and its effect, then the change you want, as a suggestion block when it
  is small.
- Mark each comment as blocking or non-blocking.
- Raise one issue per comment, and post none when there is no issue.

````
issue (blocking): `parse_port` returns `None` for `"0"` because `if not port` treats 0 as
false, so a config with port 0 is dropped. Compare with `None` instead:

```suggestion
if port is None:
```
````

## Merge

Merge once the checks pass, with the method the project prefers, as its allowed merge
methods or its history show. Without a preference, squash into one commit whose body is
written as for a commit:

```
gh pr merge <number> --squash --subject "<title> (#<number>)" --delete-branch
```

Pass `--delete-branch` with any method, so the branch is removed on the remote and locally.

## Before showing it

- Read it as someone who never saw the conversation. It does not mention the request or
  these instructions, names nothing they have not seen, holds nothing private, and keeps
  the public links they need, except references to a third party's issue, pull request, or
  commit that the global instructions place in a code comment or file.
- Replace every placeholder with its value.
- Make each claim match the diff and the command output.
- End a pull request, issue, or comment with the signature from the global instructions.

Publishing, merging included, follows the global instructions on asking first.
