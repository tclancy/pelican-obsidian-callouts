# pelican-obsidian-callouts

A [Pelican](https://getpelican.com/) plugin that renders
[Obsidian-style callouts](https://help.obsidian.md/callouts) from standard
Markdown blockquotes.

## Installation

```bash
pip install pelican-obsidian-callouts
```

Then add it to your `pelicanconf.py`:

```python
PLUGINS = ["pelican.plugins.obsidian_callouts"]
```

## Usage

Write callouts in your Markdown content using Obsidian syntax:

```markdown
> [!note]
> This is a note.

> [!warning] Watch out!
> Something to be careful about.

> [!tip]+
> Foldable callout, expanded by default.

> [!danger]-
> Foldable callout, collapsed by default.
```

### Supported types

`note`, `tip`, `important`, `warning`, `caution`, `abstract`, `info`,
`todo`, `success`, `question`, `failure`, `danger`, `bug`, `example`, `quote`

Unknown types are left as plain blockquotes.

### Foldable callouts

Append `+` (expanded by default) or `-` (collapsed by default) after the
callout type. A small inline `<script>` block is injected once per page to
wire the click handler — no external JS dependency.

## HTML output

```html
<div class="pelican-callout pelican-callout-note">
  <div class="pelican-callout-title">
    <img src="..." class="pelican-callout-icon" alt="note" width="18" height="18">
    Note
  </div>
  <div class="pelican-callout-body">
    <p>Body text here.</p>
  </div>
</div>
```

### CSS classes

| Class | Purpose |
|-------|---------|
| `.pelican-callout` | Outermost container |
| `.pelican-callout-[type]` | e.g. `.pelican-callout-warning` |
| `.pelican-callout-title` | Title row (icon + text) |
| `.pelican-callout-icon` | Lucide icon `<img>` |
| `.pelican-callout-body` | Body content |
| `.pelican-callout-foldable` | Added when callout is foldable |
| `.pelican-callout-expanded` | Foldable callout, currently open |
| `.pelican-callout-collapsed` | Foldable callout, currently closed |

Icons come from [lucide-static](https://unpkg.com/lucide-static) via unpkg CDN.

## Development

```bash
git clone https://github.com/tclancy/pelican-obsidian-callouts
cd pelican-obsidian-callouts
uv sync --all-groups
uv run pytest
```

## License

MIT
