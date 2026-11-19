# ai-skills

Global instructions and skills for Claude Code, derived from a short reference of the ways
agent work goes wrong.

| Path | Contents |
| --- | --- |
| [book/](book/README.md) | Numbered failure behaviours, each with a check, a repair, and its basis |
| [decisions/](decisions/README.md) | What the maintainer has decided, and why |
| [instructions/CLAUDE.md](instructions/CLAUDE.md) | Global instructions, loaded in every session |
| `skills/check-behaviour` | Review a session, diff, or files against the book |
| `skills/commit-and-pr` | Write a commit message, pull request, issue, or comment, and merge a pull request |
| `skills/modern-code` | Code and manifests in the idiom of the project's declared version |
| `skills/write-instructions` | Write or revise a skill, a `CLAUDE.md`, or a subagent prompt |

Rules cite book entries by number, so a rule traces to its reason and a review finding to
its rule. Skills link to the book as `../../book/`, which works on GitHub and, once
installed, through the `book` link in the configuration directory.

```sh
bin/install          # print what would change
bin/install --apply  # link into ~/.claude (or $CLAUDE_CONFIG_DIR), backing up what it replaces
```

Keep this checkout in place, and start a new session after installing.
