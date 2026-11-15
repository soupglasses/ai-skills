# 01 Contexts

The conversation is private: the user and the agent share all of it. An artifact (code, a
commit, a README, a calendar entry, a pull request) is read by people who share none of it.
Each failure here writes for the first reader inside the second context.

**1.1 Instruction echoed.** The artifact mentions the request or the standing rule that
shaped it: "made short as asked" in a calendar event, "per the commit guideline" in a pull
request, an entry number from this book in a review comment. The agent's instructions are
private to its reader even when they are published somewhere, because the reader does not
know them and has no reason to look. *Check:* does any sentence refer to a request, a
preference, the person asking, or the agent's rules ("as requested", "as discussed", "you",
"my instructions")? *Repair:* apply the instruction and delete the mention. *Basis:*
Observed.

**1.2 Unseen reference.** The text points to material its reader has not seen, or uses a
label the agent coined. *Check:* can the reader resolve every name and "the X" from the
artifact and its public surroundings? *Repair:* rewrite the sentence to stand alone, in the
project's terms. *Basis:* `jiang2026b`: 54% of 480 agent replies failed this test, mostly
because they "point to material the requester has not seen or use labels that the agent
coined during its work".

**1.3 Conversation-shaped.** The artifact follows the order of requests and objections.
*Check:* would the structure be the same had the result been reached in one step? *Repair:*
rebuild it around what the reader does with it, and drop abandoned approaches. *Basis:*
Observed.

**1.4 Session as subject.** A long-lived file is recast around this session's change: the
README leads with the newest feature, or explains why the work was needed. *Check:* would a
maintainer writing a year from now include it? *Repair:* put the change where the project's
structure places it, and the account of the work in the commit or pull request. *Basis:*
Observed.

**1.5 Private context published.** Published text carries internal names, the user's
reasons, or the conversation. *Check:* would the user say every sentence to this audience?
*Repair:* remove it, and give the public technical reason where one exists. *Basis:*
Observed. `sterken2025` name the hazard context collapse, "the flattening and merging of
multiple distinct audiences".

**1.6 Public context removed.** The reverse of 1.5: the issue link, the standard, or the
technical reason is stripped along with the conversational text. *Check:* can a reviewer
evaluate the change from what is written and linked? *Repair:* restore it. *Basis:* Observed.

**1.7 Attribution claims too much.** A signature credits the agent with other authors'
commits, or with output the edited software will generate later. *Check:* did the agent
write everything the signature covers? *Repair:* sign only the agent's own message. *Basis:*
Observed.
