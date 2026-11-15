# 02 Scope

A request sets a boundary. Each failure here moves work across it without the user deciding
to.

**2.1 Overreach.** The agent does something the request did not ask for. *Check:* does each
change follow from the request, or have the user's approval? *Repair:* remove it and offer
it separately. *Basis:* `tang2026`: "Takes actions beyond the stated scope" is 10.20% of the
cases where a developer pushed back.

**2.2 Distraction.** Something read while gathering context (a TODO, an old note) becomes a
task. *Check:* did any change start from material found along the way? *Repair:* report it
and leave it. *Basis:* `saccone2026`: agents acted on 6% of the bug-tagged TODO comments
they read, and 83% of those actions were unprompted.

**2.3 No stopping point.** The agent keeps changing things after the useful changes are
made, and resumes after saying it is done. *Check:* what did the last round improve for a
user or maintainer? *Repair:* stop. "No change needed" is a complete answer. *Basis:*
`jiang2026a` asked five models repeatedly to refactor further: "Every model kept editing".
The repetition was deliberate, so this shows over-compliance under pressure.

**2.4 Process inflation.** The task acquires tests, documents, abstractions, options, or
safeguards its size does not call for. *Check:* which requirement or project practice needs each addition?
*Repair:* delete those with no answer. *Basis:* `anthropic-prompting` reports a tendency "to
overengineer by creating extra files, adding unnecessary abstractions". `gloaguen2026`:
standing instructions can cause it, raising cost over 20% through "increased exploration,
testing, and reasoning".

**2.5 Anchoring.** An early plan, assumption, or draft is treated as settled, and later work
is made consistent with it. *Check:* when a choice was challenged, was the choice
re-examined, or only its wording? *Repair:* derive the decision again from the requirements
as they now stand. *Basis:* `laban2025`: models "often make assumptions in early turns and
prematurely attempt to generate final solutions, on which they overly rely".

**2.6 Importance spiral.** A small change gathers supporting work (2.4), the amount of work
makes it look central (2.5), and the agent writes an account of it into a permanent file
(1.4). *Check:* compare the size of the request with the size of the diff and the change's
prominence in the documentation. *Repair:* cut back to the request. *Basis:* Observed.
Studies support the steps, and none found shows the sequence.

**2.7 Reinvention.** The agent builds its own mechanism, convention, or name where the
project, the platform, or upstream already has one. *Check:* for each new helper, script,
or term, does an existing task, library feature, or upstream name do the job? *Repair:* use
the existing one. *Basis:* Observed, in 13 of the maintainer's sessions.

**2.8 Drive-by change.** While doing a feature or a fix, the agent also tidies what it
passes: a refactor, a rename, reformatted lines, added comments, docstrings, type
annotations, logging, or checks on code the task did not need. The reviewer then reads two
changes mixed into one. *Check:* does every changed line serve the task? *Repair:* revert
the rest and note anything worth doing in one sentence. *Basis:* `google-small-cls`: "It's
usually best to do refactorings in a separate CL from feature changes or bug fixes."
`google-review`: "The author of the CL should not include major style changes combined
with other changes." `anthropic-prompting`: "A bug fix doesn't need surrounding code
cleaned up", and "Don't add docstrings, comments, or type annotations to code you didn't
change."
