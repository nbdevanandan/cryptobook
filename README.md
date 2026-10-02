# Cryptobook

Ultra-lightweight Zola theme for math / cryptography knowledge bases.
Stripped MATbook fork, Tera v2 components, SSR-first.

## Layout

- `templates/` — `base.html` shell (`page` / `index` / `section` / `graph` /
  `chapters` / `login` / `offline`), `components.html` (`kb.*`), partials
- `static/js/` — `core.js` (enhancements + SPA router) + `graph.js` (canvas graph)
- `static/` — `elasticlunr.min.js`, `fonts/` (self-hosted woff2)
- `sass/` — `book.scss` / `print.scss` entries + partials

## Requirements

Zola 0.23+ (`theme.toml` pins the floor: Tera v2 components).
Site `config.toml` must set:

```toml
theme = "cryptobook"
build_search_index = true
compile_sass = true

[search]
index_format = "elasticlunr_json"

[markdown.highlighting]
style = "class"
light_theme = "github-light"
dark_theme = "github-dark"
```

## Components (`kb.*`)

`callout`, numbered `theorem` / `lemma` / `definition` / `example` /
`remark` / `notation` (+ unnumbered `proof`), `details`, `math`, `figure`,
graph macros. See downstream docs for contracts.

## License

MIT (see `theme.toml`; LICENSE file to follow if distributing).
