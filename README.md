# Grok Theme for Oh My Pi

Two omp themes built from the same graphite/ivory palette as the Zed and Pebrel
versions: near-black chrome, warm text, one desaturated steel accent.

- **grok-obsidian** — dark. `statusLineBg` sits at `#0C0C0C`; terminal canvas at `#101010`.
- **grok-parchment** — light. Neutral paper chrome with the same muted syntax palette.

Both are colors-only: no shaders, wallpapers, symbols, or terminal escape hooks.

Published as [`grok-omp-theme`](https://pi.dev/packages/grok-omp-theme) for package
discovery and Pi compatibility. OMP 18.18 loads themes from the agent themes
directory, not from plugin packages, so use the file steps below for OMP.

## Install

```sh
mkdir -p ~/.omp/agent/themes
cp themes/grok-obsidian.json themes/grok-parchment.json ~/.omp/agent/themes/

omp config set theme.dark grok-obsidian
omp config set theme.light grok-parchment
```

Restart omp, or open `/settings` → **Appearance** and pick the theme in the dark
and light slots. omp chooses the slot from the terminal background.

For a named profile, install into
`~/.omp/profiles/<name>/agent/themes/` instead. If `PI_CODING_AGENT_DIR` is set
for the default profile, use `$PI_CODING_AGENT_DIR/themes/`.

## Palette

| Role | Obsidian | Parchment |
| --- | --- | --- |
| Chrome / status line | `#0C0C0C` | `#EFEEEB` |
| Terminal canvas | `#101010` | `#FBFBF9` |
| Text / muted | `#E6E4DF` / `#9A9892` | `#242422` / `#686866` |
| Accent, model | `#A9BCCB` | `#4C6478` |
| Keyword | `#A6B8C6` | `#4C6478` |
| Function | `#D4C8B4` | `#4E6A5A` |
| String | `#AEBE9C` | `#5C6B3F` |
| Type | `#9DBFB6` | `#2F5F5A` |
| Number | `#C7A9A0` | `#8A5A52` |

The dark theme keeps tool cards and the status line darker than assistant text;
the light theme mirrors the same contrast steps rather than inverting them.

## Verification

- All 66 required color tokens are present, plus `assistantMessageText`.
- `omp gallery --width 100` renders the full tool/composer/status-line catalog
  with both variants; ANSI output was checked for the expected palette values.
- Tested with omp `18.18.1` on Windows 11 (x64).

`assistantMessageText` and `text` are both set: omp uses the former for assistant
prose and the latter for explicit editor/dialog text.

## License

MIT. Unofficial theme, not affiliated with xAI.
