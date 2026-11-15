# 05 Attribution names the model

Decided 2026-11-14.

**Decision.** Attribution names the model, not the harness, as the session reports it. With
no reported name, the agent says so and leaves the line out.

- Commit trailer: `Co-authored-by: Fable 5.2 <noreply@anthropic.com>` for Claude Fable 5.2.
- A pull request description, issue, or comment the agent writes ends with
  `Written by [Fable 5.2](https://platform.claude.com/docs/en/models).` It signs that text
  only, not attached content such as the commits.
- Copyright and license text names the maintainer, never the model, following the
  project's own form.
- Files carry no model byline.

**Why.** The model, not the harness, determines the quality of the work.

**Carried by.** `instructions/CLAUDE.md` (Attribution), `skills/commit-and-pr`.
