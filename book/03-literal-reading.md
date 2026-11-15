# 03 Literal reading

An instruction has wording and a purpose. The skill is telling apart an instruction, an
example, a placeholder, and content meant for the artifact. Inferring more is not always
right: a shell script keeps `$HOME` as written.

**3.1 Unresolved placeholder.** Text meant to be filled in is emitted as written:
`$VARIABLE`, "(your model here)". *Check:* is each template token meant to survive to
runtime, or to be substituted now? *Repair:* substitute the value. When it is unknown, say
so and leave the item out. *Basis:* Observed.

**3.2 Example as specification.** An illustration, sample phrase, or permitted option is
reproduced as though required. *Check:* does the result cover cases the example did not
show? *Repair:* implement what the example illustrates. *Basis:* `tambon2024`: the model
"excessively relies on provided examples or particular terms in the prompt". `openai2025`:
"When provided sample phrases, models can use those quotes verbatim".

**3.3 Letter over purpose.** The action satisfies the words and defeats the aim: a correctly
formatted signature that states a false authorship, a length limit met by deleting what the
reader needs. *Check:* state the purpose in one sentence. Does the result serve it?
*Repair:* serve the purpose, and report a conflict with the wording. *Basis:* `openai2025`:
GPT-4.1 follows instructions "more closely and more literally than its predecessors".

**3.4 Wrong subject.** A rule about the agent's conduct is applied to the product, or the
reverse: told to sign its comments, the agent signs the template a CI job posts from.
*Check:* whose action does the rule govern? *Repair:* apply it there only. *Basis:* Observed.

**3.5 Default over instruction.** The agent's usual practice replaces a stated preference.
*Check:* is each constraint the user stated met? *Repair:* follow it, and say so if it seems
mistaken. *Basis:* `tang2026`: "Violates an explicit developer constraint", 38.33% of
pushback cases.

**3.6 Gap filled by a guess.** The request has two readings and the agent picks one
silently. *Check:* did the agent say which reading it took? *Repair:* take the likelier one
and state it. Ask first when the readings differ in something hard to undo. *Basis:*
`tang2026`: "Acts on a wrong interpretation of what was requested", 26.95%.
