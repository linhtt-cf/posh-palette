# Contributing to Posh Palette

Posh Palette is built from small, independent JSON files. The most useful
contribution is usually a single new theme layer — **one JSON file, one PR**.

## Add a theme layer

Each layer lives in its own folder and can be contributed on its own:

| Folder | What it holds |
|--------|---------------|
| `schemes/` | a Windows Terminal color scheme (16 ANSI colors + bg/fg/cursor) |
| `palettes/` | PSReadLine input colors + `$PSStyle` output colors |
| `prompts/` | an oh-my-posh prompt reference |
| `themes/` | a **composition** that ties one entry from each layer together |

Workflow:

1. Copy an existing file in the matching folder.
2. Change the `id`, `name`, and the values.
3. (Optional) Add a `themes/` composition that references your new layer(s).
4. Open a PR.

Keep `id` kebab-case and matching the filename (e.g. `tokyo-night.json` → `"id": "tokyo-night"`).
If you add a full theme, make sure the same `id` exists across the layers it
references so the resolver can expand it.

## Naming conventions

The project/brand is **Posh Palette** (repo: `posh-palette`, kebab-case like
`oh-my-posh` / `nerd-fonts`). The PowerShell module and its commands use
PascalCase (`PoshPalette`, `Start-PoshPalette`) because command nouns can't
contain hyphens. Keep that split when adding docs or commands.

## Keep the gallery in sync

The theme gallery (`docs/themes.html`) embeds a hand-maintained snapshot of every
theme's colors. If you add or change a scheme/palette, update the matching entry on
that page so the preview matches what actually gets applied (site == reality).
