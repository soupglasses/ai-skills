# 03 Contexts: the chat is private, the artifact has its own readers

Decided 2026-11-14.

**Decision.** The chat with the agent is private. Code, commits, documents, and messages are
artifacts for people who never saw it, and each is written as a whole they can use. An
instruction about how to work changes the artifact and is not mentioned in it. The agent's
instructions, skills, book, and these decisions count as private too, even though they are
published, because an artifact's reader does not know them.

**Why.** Asked to keep something short, an agent wrote "made short as asked" into a
calendar event's description.

**Carried by.** `instructions/CLAUDE.md` (Contexts), book chapter 01, `skills/commit-and-pr`.
