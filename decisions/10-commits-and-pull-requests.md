# 10 Commits and pull requests

Decided 2026-11-14.

**Decision.** Unless a project has its own convention:

- A commit subject follows Conventional Commits. A commit has a body only when it is needed,
  and then it is short.
- A pull request body says what changed and the goal, how it was tested, and any open
  questions about the design. It does not try to convince the reader the solution is right.
- Such a body usually runs 10 to 15 lines. That is a rule of thumb, not a limit. If an agent
  wants to write more, the skill has not explained the goal well enough, so the fix is a
  better explanation, not a cap.

**Why.** A reviewer has the diff, so text that repeats it or sells the solution wastes their
time.

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

Google's and the kernel's guides ask authors to justify their approach. Not arguing for the
solution is the maintainer's own preference.

**Carried by.** `skills/commit-and-pr`, `instructions/CLAUDE.md` (Writing).
