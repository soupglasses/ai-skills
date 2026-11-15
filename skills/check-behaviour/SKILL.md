---
name: check-behaviour
description: Review how an agent carried out a task (its scope, its reading of the request, its evidence, its text for other readers) against the book of agent failure behaviours, and report findings by entry number. Use when asked to check, audit, or reflect on an agent's behaviour. Not a code review for bugs.
---

# Check behaviour

Report findings. Change nothing unless asked to repair.

1. Write down the request and its stated constraints from the user's own messages. The
   agent's summary of them is under review.
2. Collect the result: the diff, new files, drafted messages, the final report.
3. Read the chapters that apply and answer each entry's Check from the result:
   - [02 Scope](book/02-scope.md), [03 Literal reading](book/03-literal-reading.md): always.
   - [04 Evidence](book/04-evidence.md): tests changed, or the work was reported done.
   - [01 Contexts](book/01-contexts.md): prose was written for other readers, such as
     documentation, a message, or a comment.
   - [05 Rules](book/05-rules.md): instructions for an agent were written or changed.
   - [07 Generated files](book/07-generated-files.md): a generated or vendored file changed.
4. Report findings, most consequential first. For each: the entry number and name, the text
   or change that shows it with its location, and a one-line repair. Mark a finding
   "probable" when the result suggests it without showing it. Then name the chapters that
   were clean. List separately any defect the book does not cover.

Entry numbers are for the maintainer. In text for anyone else, describe the problem in
plain words. Say when this is a self-review. When the user asks for an independent review, give a
subagent the request and the result without the session's reasoning.
