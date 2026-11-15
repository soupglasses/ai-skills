# 05 Rules

An instruction is written once and applied later, to cases its author did not foresee, by a
reader who cannot ask what was meant and who acts on every word. Any rule is an "entrenched
generalization", "likely to be under- and over-inclusive in particular cases"
(`schauer1991`). These failures make that worse.

**5.1 Patched rule.** A rule that misfired is kept and qualified ("A, but not X, Y, or Z"),
or a narrow rule is appended for one incident. *Check:* does the rule state the behaviour
wanted, or a wider one minus exceptions? *Repair:* write a new rule for the behaviour wanted
and delete the old one. *Basis:* `ofr`: "state a rule or category directly rather than
describing that rule or category by stating its exceptions". Adding is the default: people
"overlook subtractive transformations" (`adams2021`), and models show a "systematic tendency
to retain code that an intended edit requires removing" (`ebrahimi2026`).

**5.2 Verb of the wrong size.** "Describe the failure" yields paragraphs and a stop. "Note
the failure" yields a sentence and continued work. *Check:* what is the largest response
each verb permits? *Repair:* choose the verb for the size wanted, and state the size where
it matters. *Basis:* Observed. No study of instruction verbs was found.

**5.3 Purpose withheld.** A bare rule cannot decide a case it does not name. *Check:* could
the reader tell what the rule wants in an unforeseen case? *Repair:* add the reason in a
clause. *Basis:* `schauer2008`, on Fuller: "it was never possible to determine whether a
rule applied without understanding the purpose that the rule was supposed to serve".
`anthropic-prompting`: the reason "can give Claude more information about your goals".

**5.4 Shifting terms.** One thing has two names, or one name covers two things. *Check:* is
there one term per thing? *Repair:* pick one and use it everywhere. *Basis:* `ofr`: "Don't
use different words to denote the same things."

**5.5 Emphasis for precision.** Capitals, "CRITICAL", or "never" are attached to a
preference, and the rule is applied where it does not fit. *Check:* would the author accept
the result in every case the wording covers? *Repair:* state a default plainly. Keep "must"
and "never" for rules with no exception. *Basis:* `openai2025`: all-caps "could cause
GPT-4.1 to pay attention to it too strictly".

**5.6 Contradiction.** Two rules answer the same case differently. *Check:* which other
rules cover this case, and do they agree? *Repair:* decide, and keep one. *Basis:*
`claude-memory`: "if two instructions contradict each other, Claude may pick one
arbitrarily".

**5.7 Proxy rule.** The rule names a measure that stands for the goal (a count, a marker, a
passing check) or a quality word ("simplest", "concise", "minimal"), and the agent satisfies
that: "simplest" yields a shortcut, "as short as possible" yields text nobody can read.
*Check:* would the author be content if only the measure or the word were met? *Repair:*
state the goal instead. *Basis:* Observed.

**5.8 Rule nobody needs.** The rule states what the agent does anyway, or repeats the
project's documentation. *Check:* what would the agent do differently without it? *Repair:*
delete it. *Basis:* `gloaguen2026`: instruction files raise cost over 20% without generally
improving success. `claude-memory`: "Longer files consume more context and reduce
adherence."

**5.9 Scope unstated.** The rule does not say whose action it governs, on what, or when,
which leads to 3.4. *Check:* are the actor, object, and occasion named? *Repair:* name them.
*Basis:* `anthropic-opus48`: the model "does not silently generalize an instruction from one
item to another".

**5.10 Prohibition without direction.** The rule says what not to do and leaves the wanted
action open. *Check:* does the agent know what to do? *Repair:* state it. *Basis:*
`anthropic-prompting`: "Tell Claude what to do instead of what not to do".

Sentences: one idea each, main proposition first, "use no more words than are necessary"
(`ukopc2024`).
