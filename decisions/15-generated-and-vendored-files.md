# 15 Generated and vendored files

Decided 2026-11-15.

**Decision.** A generated file changes only through its generator, and the agent names each
generated file its change touched. When the file's own comment says how it may be edited,
as a config file inside a generated folder sometimes does, the agent follows that comment.
A comment saying not to edit a file is a signal to stop before a hand edit. Vendored code is patched in place only
when it is never updated from upstream. When it is updated, by a tool or by intent, the
patch lives outside the copy: a fork, a patch file, or the package manager's own mechanism.

**Why.** Agents recognise a generated file and edit it by hand anyway, repeatedly, and a
later agent does not notice. The next regeneration or upstream update silently erases the
edit.

**Carried by.** `instructions/CLAUDE.md` (Generated and vendored files), book chapter 07,
`skills/check-behaviour`.
