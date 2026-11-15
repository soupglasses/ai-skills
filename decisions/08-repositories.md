# 08 Repository access

Carried over from the previous setup on 2026-11-14.

**Decision.** Work that belongs to another repository happens in that repository's checkout,
cloned under `<host>/<owner>/<repository>` when there is none. `/tmp` is for throwaway
checkouts. Uncommitted work is kept. Internal names and code stay out of public web searches.

**Why.** Agents worked in the wrong repository often enough to need a rule. The rest is not
recorded.

**Carried by.** `instructions/CLAUDE.md` (The work, Secrets and live systems).
