# Go

- **Covers:** 1.18 to 1.27
- **Declared version:** the `go` line in `go.mod`. The compiler rejects newer features.
- **Release notes:** `https://go.dev/doc/go1.N`
- **Format:** `gofmt`, or `goimports` when the project uses it
- **Modernize:** `go fix -diff ./...` previews the standard modernizers, and `go fix ./...`
  applies them (from 1.26)

| Since | Prefer |
| --- | --- |
| 1.18 | `any`, type parameters, `strings.Cut`, `netip.Addr` |
| 1.20 | `errors.Join`, several `%w` in one `fmt.Errorf`, `context.WithCancelCause`, `strings.CutPrefix`, `time.DateOnly`, `time.DateTime` |
| 1.21 | `min`, `max`, `clear`, `slices`, `maps`, `log/slog`, `sync.OnceValue`, `context.AfterFunc`, `context.WithoutCancel` |
| 1.22 | per-iteration loop variables (no `x := x`), `for i := range n`, `math/rand/v2`, `ServeMux` patterns `"POST /items/{id}"` with `r.PathValue`, `slices.Concat`, `cmp.Or` |
| 1.23 | range-over-func iterators, `iter.Seq`, `slices.Sorted(maps.Keys(m))`, `slices.Collect`, `slices.Chunk`, unreferenced timers need no `Stop` |
| 1.24 | `b.Loop()`, `t.Context()`, `t.Chdir`, `omitzero`, `strings.SplitSeq`, `os.OpenRoot`, `tool` lines in `go.mod`, `runtime.AddCleanup` |
| 1.25 | `wg.Go`, `testing/synctest` |
| 1.26 | `new(expr)`, `errors.AsType`, `reflect.Type.Fields` |
| 1.27 | `encoding/json/v2`, `encoding/json/jsontext`, generic methods, standard `uuid` package, `strings.CutLast`, `url.URL.Clone`, `synctest.Sleep`, HTTP/1 `Close` drains the body |