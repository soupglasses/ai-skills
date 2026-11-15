# 12 Code uses the idiom of the declared language version

Decided 2026-11-14.

**Decision.** Code the agent writes uses the newest forms the project's declared version
allows, and is formatted with the project's standard formatter. The `modern-code` skill
lists, per language, what newer versions added as short keywords, from about 2019 on. The
agent writes with those, then runs the language's modernizer as a second pass. When a project
declares a newer version than the skill covers, the agent first reads that version's
release notes and updates the skill. Each reference has the same shape, so it can be kept up
to date the same way.

**Why.** Models write in the style of the older code that dominates their training data, and
a general instruction to use the newest idioms is often ignored. A list of what each version
added, plus the language's own modernizer tool, gives the agent something concrete to follow.

**Basis.** Read on 2026-11-15:

- Older style by default: LLM tools "tended ... to produce Go code in a style similar to the
  mass of Go code used during training", and "often refused to use the newer ways even when
  directed to do so in general terms such as "always use the latest idioms of Go 1.25""
  ([Donovan, Go blog](https://go.dev/blog/gofix)).
- Outdated context makes it worse: across seven models, deprecated API use ran "25% to 38%",
  and "70%-90%" when the surrounding code already used the old API, against 9% to 18% when it
  used the new one ([Wang et al., ICSE 2025](https://arxiv.org/abs/2406.09834)).
- "About 2019" is the maintainer's estimate. No source was found for a number of years.

**Carried by.** `skills/modern-code`, `instructions/CLAUDE.md` (Code).
