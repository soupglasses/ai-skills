---
name: modern-code
description: Write Python, Go, Kotlin, or Kubernetes manifests in the idiom of the version a project declares, using newer forms in place of the older ones a model writes by habit. Use when writing or changing code or manifests in one of these.
---

# Modern code

Models write in the style of the older code they were trained on, and a general instruction
to use the newest idioms is often ignored. So this skill works in two passes: write with the
forms each reference lists, then run the language's modernizer over the result. References:
[python.md](python.md), [go.md](go.md), [kotlin.md](kotlin.md),
[kubernetes.md](kubernetes.md).

1. **Open the reference** and find the project's declared version the way its **Declared
   version** line says. That version is the newest whose forms may be used.
2. **Bring the reference up to date first** when the declared version is newer than
   **Covers**. Read the **Release notes** of each missing version, add its new forms as
   keywords, and raise **Covers**. Add only what the notes state.
3. **First pass: write with the listed forms.** Prefer each keyword listed at or below the
   declared version where it fits the code you write or change and the project's
   conventions.
4. **Second pass: run the Modernize tool** the reference names on the files you changed,
   and apply its findings to the lines you wrote or changed. Where it names no tool, act on
   the deprecation warnings it points to. Say so when a tool is not installed, and do not
   install one.
5. **Run the Format tool** on the files you changed.
6. **Leave what you were not asked to change in its existing form.** Mention in one
   sentence that it could be modernized.

Experimental and preview features are used only when the project already enables them.

## A reference

Every reference has this shape, so a new language is one new file:

```
# Name

- **Covers:** oldest to newest version listed
- **Declared version:** where a project states it
- **Release notes:** URL pattern for one version
- **Format:** the standard formatter, and how to tell which a project uses
- **Modernize:** a tool that reports or rewrites older forms, or where warnings appear

| Since | Prefer |

## Best practice

- `new` over `old`, and why in a few words: removals, and advice no tool or warning reports
```

A row lists, as short keywords, the stable forms a version added that replace an older way
of writing the same thing. A feature with no older equivalent has no row. Each keyword
comes from the release notes, not from memory. Rows start at releases from about 2019,
since models already write the forms older than that. Best practice is short bullets,
one fact each.
