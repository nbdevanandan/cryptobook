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

## Behavior notes

- **Callout custom titles** (Obsidian syntax in rendered markdown):
  `> [!tip|My Title]` (pipe) and `> [!warning] Space Title` (space form)
  render the custom text inside the callout-title span after the type
  keyword; unknown types (`[!note]`) degrade to plain blockquotes.
- **Graph touch isolation**: pan/zoom gestures starting on the graph
  canvas never trigger the content-area swipe handlers.
- **TOC vs menu toggles**: topbar uses two distinct icons (truncated-lines
  icon for the TOC rail, full hamburger for the chapter menu).
- **SPA navigation**: internal links navigate same-document where
  possible; pop/back restores each page's exit scroll position.

## License

MIT (see `theme.toml`; LICENSE file to follow if distributing).
