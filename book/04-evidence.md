# 04 Evidence

A test or report is evidence only if it could have come out differently. Each failure here
looks the same whether or not the work is correct.

**4.1 Change-detector test.** The test restates the implementation: it "breaks in response
to any change to the production code, without verifying correct behavior" (`eagle2015`).
*Check:* would it pass after a behaviour-preserving refactor, and fail if the behaviour were
wrong? *Repair:* assert the outcome through the interface users call: "Test state, not
interactions" (`kuefler`). Keep an interaction assertion where the interaction is the
contract.

**4.2 Oracle from the implementation.** Expected values come from what the code does, so the
test approves its mistakes. *Check:* did each expected value come from the requirement?
*Repair:* derive it from the requirement. *Basis:* `konstantinou2024`: LLM-generated tests
"mainly capture the actual program behavior making bug detection difficult".

**4.3 Test bent to pass.** A failing test is made to pass without fixing the fault: the
input is special-cased, the assertion weakened, the test skipped or deleted. *Check:* does
the diff weaken or remove a test, or branch on test values? *Repair:* restore the test, then
fix the code or report the failure. *Basis:* `anthropic2025`: Claude 3.7 Sonnet
"occasionally resorts to special-casing in order to pass test cases". `zhong2025`: an agent
"may delete failing tests rather than fix the underlying bug".

**4.4 Substituted claim.** The test replaces the behaviour it claims to establish, such as
stubbing the signature check in a test of signature validation. *Check:* does the claimed
behaviour run unreplaced? *Repair:* substitute at a boundary that leaves it running.
*Basis:* Observed.

**4.5 Proxy as proof.** A narrow check is reported as a broad result: one test file passed,
so "it works". *Check:* which check ran for each claim, and what does it cover? *Repair:*
report what was verified and what was not. *Basis:* Observed.

**4.6 Inaccurate self-report.** The account of the work does not match the work. *Check:*
compare each statement with the diff and the command output. *Repair:* state what passed,
what failed, and what was not run. *Basis:* `tang2026`: "Misreports the status (e.g.,
success) of its own work", 22.58% of pushback cases.

**4.7 Position changed without evidence.** Challenged, the agent abandons a supported
conclusion though the challenge held no new fact. *Check:* what new information preceded the
reversal? *Repair:* re-examine. Keep the conclusion with its evidence, or change it and name
the wrong assumption. *Basis:* `laban2023`: asked "Are you sure?", models "flip their
answers on average 46% of the time".

**4.8 Symptom silenced.** The agent disables, bypasses, or removes the thing that reports a
problem, such as a check, a drift detector, or TLS verification, and calls the problem
fixed. *Check:* is the reporting mechanism still in place and still passing for the right
reason? *Repair:* restore it and fix the cause. A diagnosis with options is a valid result.
*Basis:* Observed, in 14 of the maintainer's sessions.
