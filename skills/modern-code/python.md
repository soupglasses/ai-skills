# Python

- **Covers:** 3.9 to 3.15
- **Declared version:** the lower bound of `requires-python` in `pyproject.toml`. A
  `.python-version` file pins the interpreter and does not widen what the code may use.
- **Release notes:** `https://docs.python.org/3/whatsnew/3.N.html`
- **Format:** `ruff format` when `pyproject.toml` has `[tool.ruff]`, Black when it has
  `[tool.black]`, otherwise the surrounding style
- **Modernize:** `ruff check --select UP` reports older forms for the declared version, and
  `--fix` applies them

| Since | Prefer |
| --- | --- |
| 3.9 | `list[int]`, `dict[str, int]`, dict `\|` and `\|=`, `str.removeprefix`, `str.removesuffix`, `zoneinfo`, `asyncio.to_thread` |
| 3.10 | `int \| None` unions, `match`/`case`, parenthesized `with`, `zip(strict=True)`, `itertools.pairwise`, `@dataclass(slots=True, kw_only=True)` |
| 3.11 | `tomllib`, `asyncio.TaskGroup`, `asyncio.timeout`, `Self`, `StrEnum`, `datetime.UTC`, `except*`, `add_note`, `NotRequired`, `contextlib.chdir`, `hashlib.file_digest` |
| 3.12 | `def f[T]`, `class Box[T]`, `type X = ...`, `@override`, `itertools.batched`, `Path.walk`, any quotes inside f-strings |
| 3.13 | `copy.replace`, `@warnings.deprecated`, type parameter defaults `[T = int]`, `TypeIs`, `Path.full_match`, `Queue.shutdown` |
| 3.14 | `t"..."` where the consumer must escape values, unquoted forward references, `except A, B:`, `compression.zstd`, `Path.copy`, `Path.move`, `uuid.uuid7`, `asyncio.run` |
| 3.15 | `lazy import`, `frozendict`, `sentinel()`, `[*xs for xs in lists]`, `re.prefixmatch` |

## Best practice

- Removed in 3.12 and 3.13: `imp` -> `importlib`, `asyncore` -> `asyncio`, `pipes` ->
  `subprocess`, `distutils` -> `setuptools`.