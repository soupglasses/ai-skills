# Kotlin

- **Covers:** 1.5 to 2.4
- **Declared version:** the Kotlin plugin version in `build.gradle(.kts)`, in
  `gradle/libs.versions.toml`, or `<kotlin.version>` in `pom.xml`. A `languageVersion` in
  `compilerOptions` lowers it for language features, and `apiVersion` for the library.
- **Release notes:** `https://kotlinlang.org/docs/whatsnewXY.html` (`whatsnew24.html`,
  `whatsnew2420.html`)
- **Format:** the formatter task the build configures, such as ktlint, ktfmt, or Spotless.
  Without one, the official style (`kotlin.code.style=official`) by hand.
- **Modernize:** none. Compiler deprecation warnings name the replacement.

| Since | Prefer |
| --- | --- |
| 1.5 | `uppercase()`, `lowercase()`, `replaceFirstChar`, `uppercaseChar()`, `Char.code`, `digitToInt()`, `@JvmInline value class`, `firstNotNullOf` |
| 1.6 | `readln()`, `10.seconds`, `inWholeMinutes`, `buildList`/`buildMap`/`buildSet` without opt-in, exhaustive `when` statements |
| 1.7 | `max()`/`min()` that throw on empty, `_` for an inferred type argument, `@OptIn` without a compiler flag |
| 1.8 | `kotlin-stdlib` alone, without `-jdk7`/`-jdk8` |
| 1.9 | `entries`, `data object`, `..<`, `measureTime`, `measureTimedValue`, named regex groups in common code, `kotlin.concurrent.Volatile` |
| 2.0 | `enumEntries<T>()`, smart casts through local `val`s, after `\|\|`, on function-typed properties, and in inline lambdas |
| 2.1 | `when` on a sealed type parameter without `else`, `Path.walk()`, `visitFileTree { }` |
| 2.2 | guard conditions `is X if cond ->`, `break`/`continue` in lambdas, `$$"""..."""`, `Base64` and `toHexString` without opt-in, `-jvm-default` |
| 2.3 | nested `typealias`, data-flow exhaustive `when`, `return` in an elvis expression body, `kotlin.time.Clock`, `kotlin.time.Instant` |
| 2.4 | context parameters, explicit backing fields `field =`, `@all:` annotation target, `kotlin.uuid.Uuid`, `toBigInteger()`, `isSorted()` |