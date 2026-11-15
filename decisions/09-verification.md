# 09 Verification

Carried over from the previous setup on 2026-11-14.

**Decision.** Tests check behaviour a user can observe, through the interface they use. The
agent finishes a batch of related edits before running checks, and runs the checks for the
task at hand, not the full suite. Its report says what passed, what failed, and what was not
run.

**Why.** Not recorded.

**Carried by.** `instructions/CLAUDE.md` (Verification), book chapter 04.
