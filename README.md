# Grok Themes for Oh My Pi

Two themes for [oh-my-pi](https://github.com/can1357/oh-my-pi) (`omp`) built from
the same graphite and ivory palette as the Zed and Pebrel versions.

- **grok-obsidian** — dark. Status line and chrome at `#0C0C0C`, terminal canvas
  at `#101010`.
- **grok-parchment** — light. Neutral paper chrome with the same muted syntax
  palette.

Both themes are colors-only. They define the complete omp theme token set,
including the optional `assistantMessageText` token; they do not change symbols,
spinners, terminal escape behavior, or wallpapers.

## Installation (omp)

OMP reads themes from the active agent directory. Copy the JSON files and select
them in the dark and light slots:

```sh
mkdir -p ~/.omp/agent/themes
cp themes/grok-obsidian.json themes/grok-parchment.json ~/.omp/agent/themes/

omp config set theme.dark grok-obsidian
omp config set theme.light grok-parchment
```

Restart omp, or open `/settings` → **Appearance** and choose the themes. omp
selects the slot from the terminal background.

For a named profile, install into
`~/.omp/profiles/<name>/agent/themes/`. If `PI_CODING_AGENT_DIR` is set for the
default profile, use `$PI_CODING_AGENT_DIR/themes/`.

## Package Listing

The themes are also published as the Pi package
[`grok-omp-theme`](https://pi.dev/packages/grok-omp-theme) for discovery and for
Pi-compatible hosts. OMP 18.18 loads themes from the agent themes directory, not
from installed plugin packages, so the file copy above is the supported OMP
installation path. The package is installed from npm with:

```sh
omp install npm:grok-omp-theme
```

## Palette

| Role | Obsidian | Parchment |
| --- | --- | --- |
| Chrome / status line | `#0C0C0C` | `#EFEEEB` |
| Terminal canvas | `#101010` | `#FBFBF9` |
| UI text / muted | `#E6E4DF` / `#9A9892` | `#242422` / `#686866` |
| Assistant prose | `#C9C3B7` | `#242422` |
| Accent, model | `#A9BCCB` | `#4C6478` |
| Keyword | `#A6B8C6` | `#4C6478` |
| Function | `#D4C8B4` | `#4E6A5A` |
| String | `#AEBE9C` | `#5C6B3F` |
| Type | `#9DBFB6` | `#2F5F5A` |
| Number | `#C7A9A0` | `#8A5A52` |

The dark theme keeps tool cards and the status line darker than assistant text.
Assistant prose, user/custom message text, and the terminal foreground use the
softened `#C9C3B7`; UI chrome and dialogs keep the brighter `#E6E4DF`. The light
theme mirrors the same contrast steps rather than inverting them.

## Verification

- All 66 required color tokens are present, plus `assistantMessageText`.
- `omp gallery --width 100` renders the full tool, composer, and status-line
  catalog with both variants; ANSI output was checked for the expected palette
  values and no fallback palette.
- Tested with omp 18.18.1 and 18.18.2 on Windows 11 (x64).

## Repository Layout

```text
themes/grok-obsidian.json
themes/grok-parchment.json
package.json            npm / Pi package manifest
README.md
LICENSE
```

## Status and Links

- Source: https://github.com/MistanKh/ohmypi-grok-theme
- npm package: https://pi.dev/packages/grok-omp-theme
- Community post: https://github.com/can1357/oh-my-pi/discussions/18542
- Release: https://github.com/MistanKh/ohmypi-grok-theme/releases/tag/v1.0.0

## License

MIT. Independent and unofficial; not affiliated with xAI.
