# 16 Changes stay focused for the reviewer

Decided 2026-11-15.

**Decision.** Code written for a feature or a fix is targeted, and reads as one complete
whole for a reviewer. It carries none of the niceties agents add unasked: refactors,
renames, reformatting, or added comments, docstrings, annotations, logging, or checks on
code outside the task. The project's conventions come first. Within them, the code the
task writes prefers newer language and library features.

**Why.** A reviewer reads every changed line, and unrelated changes hide the one that
matters.

**Basis.** Read on 2026-11-15:

- Separate refactors: "It's usually best to do refactorings in a separate CL from feature
  changes or bug fixes" ([Google, Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html)).
- No mixed style changes, and consistency: "The author of the CL should not include major
  style changes combined with other changes", and "If no other rule applies, the author
  should maintain consistency with the existing code"
  ([Google, code review](https://google.github.io/eng-practices/review/reviewer/looking-for.html)).
- Agents overreach: taking "actions beyond the stated scope" is 10.20% of the cases where a
  developer pushed back, in 20,574 agent sessions (book entry 2.1, `tang2026`).

**Carried by.** `instructions/CLAUDE.md` (Code), book entry 2.8, `skills/modern-code`.
