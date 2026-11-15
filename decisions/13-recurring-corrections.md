# 13 Rules from recurring corrections

Decided 2026-11-14, from the maintainer's Codex prompt history (4,013 prompts, 246 sessions,
April to November 2026). The number is the count of sessions showing the correction.

**Decision.** The global instructions carry a rule for each of these:

| Correction | Sessions |
| --- | --- |
| Over-built: layers, options, safeguards nobody needs | 31 |
| Text too long, then too cryptic once corrected | 23 |
| Wrong reading of the request or its target | 21 |
| Added things that trace to nothing, or invented facts | 18 |
| Did not finish, or reported done what did not work | 17 |
| Named things with invented terms | 16 |
| Worked around a problem instead of fixing its cause | 14 |
| Hand-rolled what the project, platform, or upstream provides | 13 |
| Scope creep | 13 |
| Artifact shaped by the conversation | 11 |
| Stalled or handed the work back | 11 |
| Fragile or needless tests | 10 |
| Touched secrets or public channels without asking | 10 |
| Hardcoded values | 10 |
| Left obsolete material behind | 10 |
| Wrong attribution, or invented model name | 9 |
| Worked in the wrong host, repository, or file | 8 |
| Dropped content the maintainer wanted kept | 6 |
| Unsigned commits or overridden identity | 6 |
| Documentation that goes stale | 6 |
| Commit or push state left unclear | 6 |

"Simple" and "concise" are not used as instructions. The maintainer rejected "simplest" for
inviting shortcuts and "as short as possible" for producing text nobody can read. Rules name
the goal: direct and idiomatic work, text sized to what its reader needs.

**Why.** A rule earns its place by a failure that recurs. These recurred.

**Carried by.** `instructions/CLAUDE.md`, book entries 2.7 and 4.8.
