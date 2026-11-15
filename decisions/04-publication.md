# 04 Commits and publishing need the maintainer's OK

Decided 2026-11-14, revised 2026-11-15.

**Decision.** The agent commits, amends, and pushes only after the maintainer's OK. It asks
with a plan that can be read at a glance: a bullet per commit with its rough title, then a
bullet per push or publish command. One OK covers the whole list. When the session is
automated, or the maintainer said to commit and push automatically, the agent goes ahead
without asking.

Before it opens or edits a pull request or issue, or posts a comment or review, it shows
exactly what will be sent: destination, flags, title, and full text. The OK covers that one
action as shown.

The agent pushes or publishes only to repositories owned by the maintainer's own accounts,
and for any other repository gives the maintainer the command to run. Reading and searching
need no approval.

**Why.** The maintainer reviews uncommitted changes as diffs in the app, and a commit takes
them out of that view, so commits need no diff in the request. A pull request, issue, or
comment is put in front of other people to read, so its text is approved exactly.

**Carried by.** `instructions/CLAUDE.md` (Git and publishing), `skills/commit-and-pr`.
