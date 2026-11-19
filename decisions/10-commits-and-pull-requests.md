# 10 Commits and pull requests

Decided 2026-11-14, revised 2026-11-19.

**Decision.** Unless a project has its own convention:

- A commit subject follows Conventional Commits. A commit has a body only when it is needed,
  and then it is short.
- A pull request body says what changed and the goal, how it was tested, and any open
  questions about the design. It does not try to convince the reader the solution is right.
- Such a body usually runs 10 to 15 lines. That is a rule of thumb, not a limit. If an agent
  wants to write more, the skill has not explained the goal well enough, so the fix is a
  better explanation, not a cap.
- A pull request is opened when the work is meant for review and merge, against the default
  branch, not stacked on another open pull request. It is a draft only when the work is
  plainly unfinished; uncertain CI is not a reason. Its body is kept true as commits are
  added.
- A pull request is merged after its checks pass, by the project's preferred method. Without
  one, it is squash-merged as `<title> (#<number>)`, so its work and fix commits land as one
  commit. Its branch is then deleted.
- A review comment raises one problem in the changed lines, says what change is wanted, and
  is marked blocking or non-blocking.

**Why.** A reviewer has the diff, so text that repeats it or sells the solution wastes their
time. Draft status states an intention, not a test result. Stacked pull requests have to be
rebased after each squash merge. One commit per pull request keeps the default branch's
history one task per entry.

**Basis.** Read on 2026-11-14:

- Body only when needed: "not every commit requires both a subject and a body"
  ([Beams](https://cbea.ms/git-commit/)).
- Parts of a description: "the problem, the approach, and the result", and "where reviewers
  should pay special attention"
  ([GitHub](https://docs.github.com/en/pull-requests/concepts/helping-others-review-your-changes)).
- Ask for what you want: "stating the desired feedback type best predicts change acceptance
  and reviewer engagement" ([Pirouzkhah et al.](https://arxiv.org/abs/2602.14611), 80K pull
  requests).
- Claims must match the diff: in agent-written pull requests, "descriptions claim
  unimplemented changes was the most common issue" ([Gong et al.](https://arxiv.org/abs/2601.04886)).
- Long means split: "If your description starts to get long, that's a sign that you probably
  need to split up your patch"
  ([kernel](https://docs.kernel.org/process/submitting-patches.html)).
- Example over cap: "Positive examples showing how Claude can communicate with the
  appropriate level of concision tend to be more effective than negative examples"
  ([Anthropic](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-4-8)).

Read on 2026-11-19:

- Severity: "Consider labeling the severity of your comments, differentiating required
  changes from guidelines or suggestions"
  ([Google](https://google.github.io/eng-practices/review/reviewer/comments.html)).
- Agent review noise: "56.3% were rejected", mainly for "invalid suggestions that were false
  positives, redundant, or out of scope" ([Lin et al.](https://arxiv.org/abs/2607.03316)).

Google's and the kernel's guides ask authors to justify their approach. Not arguing for the
solution is the maintainer's own preference.

**Carried by.** `skills/commit-and-pr`, `instructions/CLAUDE.md` (Writing).
