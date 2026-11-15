# 07 Generated and vendored files

Some files have a source elsewhere: a generator's input, or an upstream project. The agent
can tell that a file is generated or vendored, and still edits it as if it were the source.

**7.1 Generated file edited by hand.** The agent sees that a file is generated and edits it
directly anyway, again and again. The next generator run erases the edit. *Check:* does a
changed file say it is generated, with a header such as "DO NOT EDIT" or `@generated`, or
"generated" in its name or path? Was it changed only by its generator? *Repair:* revert the
hand edit, change the input, and rerun the generator. When the file's own comment says how it
may be edited, as a config file inside a generated folder sometimes does, follow that
comment. *Basis:*
Observed, repeatedly.

**7.2 Do-not-edit marker ignored.** A comment tells the reader not to edit the file, and
the agent edits it by hand. The marker exists to catch exactly this mistake. *Check:* did
the agent hand-edit a file that says not to? *Repair:* stop before the edit and tell the
user. *Basis:* Observed.

**7.3 Earlier tampering unnoticed.** A generated or vendored file already holds a hand edit,
and a later agent or reviewer does not see it. *Check:* when the agent regenerated the file,
did lines change that the input did not touch? *Repair:* report those lines as an earlier
hand edit instead of silently keeping or dropping them. *Basis:* `github-linguist`:
generated files are "hidden by default in diffs". `go-mod`: "The `go` command does not check
that packages in the `vendor` directory have not been modified".

**7.4 Vendored copy patched in place.** The agent fixes a bug inside a vendored copy of
upstream code that is still updated from upstream, by a tool or by intent. The next update
replaces the copy and the fix with it. *Check:* is the vendored code ever updated from
upstream? *Repair:* keep the patch outside the copy, in a fork, a patch file, or the
package manager's own patch mechanism. A copy that is never updated may be patched in
place. *Basis:* `go-mod`: "`go mod vendor` removes the `vendor` directory if it exists
before re-constructing it. Local changes should not be made to vendored packages."
