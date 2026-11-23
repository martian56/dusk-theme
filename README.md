# dusk-theme

Twenty themes for the [dusk](https://github.com/martian56/dusk) editor, and a
few ways to wander through them. A theme here is more than colors: each one
also picks its own bold and italic syntax, swaps dusk's glyphs (the brand in
the tab bar, tree arrows, borders, corners), and renames the modes in the
status bar. In `hal-9000`, normal mode reads `I AM SORRY` and insert mode
`DAVE...`.

Needs dusk 0.5.0 or newer.

## Install

```
:plugin install github.com/martian56/dusk-theme
```

dusk clones the repository, builds the plugin with `rvpm`, and loads the
themes. Then `:theme` lists them and `:theme synthwave-84` switches.

## The themes

| Theme | Mood | Brand | Normal / insert |
| --- | --- | --- | --- |
| `abyssal-glow` | Bioluminescent things drifting where sunlight never goes | `≈ ABYSS ≈` | DRIFTING / GLOWING |
| `amber-crt` | Phosphor amber on a humming 1982 terminal | `>_ CRT` | READY. / TYPING |
| `arctic-lab` | A clean light theme from a research station at minus forty | `❄ ARCTIC` | FROZEN / THAWING |
| `blueprint` | White lines on drafting blue, for architects of code | `⌂ BLUEPRINT` | DRAFTING / SKETCHING |
| `bubblegum-pop` | Pastel pink, a light theme that chews loudly | `✿ POP ✿` | CHEWING / BLOWING |
| `candy-unicorn` | Rainbow syntax for people who think code should sparkle | `✧ UNICORN ✧` | PRANCING / SPARKLING |
| `coffee-shop` | Warm espresso, cream, and the hiss of the milk wand | `c[_] dusk` | SIPPING / BREWING |
| `dragon-hoard` | Gold coins, emerald scales, and a lair full of old code | `♛ HOARD` | GUARDING / HOARDING |
| `event-horizon` | Starlight bending around a very patient black hole | `◉ HORIZON` | ORBITING / FALLING |
| `game-cartridge` | Four shades of green on a brick in your pocket | `◘ PLAYER 1` | PLAYER 1 / INSERT COIN |
| `hal-9000` | A calm red eye. It can't let you do that, Dave | `● HAL 9000` | I AM SORRY / DAVE... |
| `mars-colony` | Rust dust, a thin sky, and oxygen at eighty percent | `♂ OLYMPUS` | HABITAT / TERRAFORM |
| `neo-tokyo` | Rain on neon signs at 3 a.m. in a city that never compiles | `NEO-TOKYO` | NIGHT CITY / HACKING |
| `noir-detective` | Black and white, cigarette smoke, and one red clue | `◐ NOIR` | STAKEOUT / CONFESSING |
| `retro-terminal-90s` | Teal desktop, double-line borders, and a modem singing in the next room | `[dusk.exe]` | READY / TYPING... |
| `solar-flare` | The sun sneezed. Everything is gold and slightly on fire | `☀ FLARE ☀` | SHINING / ERUPTING |
| `synthwave-84` | Neon sunset over an endless 1984 highway | `▲ SYNTH ▲` | CRUISE / DRIVE |
| `the-matrix` | Green rain. There is no spoon, only buffers | `01 MATRIX 10` | WATCHING / JACKED IN |
| `toxic-spill` | Radioactive green, hazard purple, do not lick the screen | `☢ TOXIC ☢` | STABLE / MUTATING |
| `zen-garden` | Raked sand, moss, and a light theme that breathes slowly | `◯ zen` | STILL / FLOWING |

## Commands

| Command | Key | What it does |
| --- | --- | --- |
| `theme.gallery` | `space T` | A panel with every theme and its description. Enter wears one; the buttons roll a surprise or a chaos theme, and the box below takes a mood. |
| `theme.surprise` | `space S` | Wears a random theme other than the current one. |
| `theme.chaos` | | Invents a brand new theme named `chaos`: a random hue scheme, random labels, and a random brand. Run it again for another. |
| `theme.mood` | | Asks how you feel and picks a theme: happy, sleepy, hacking, cold, retro, epic, and more. |
| `theme.clock` | | Follows the time of day: `arctic-lab` at dawn, `coffee-shop` in the morning, `zen-garden` in the afternoon, `synthwave-84` at sunset, `neo-tokyo` in the evening, and `event-horizon` at night. Run it again to stop. |

## Making your own

Each theme is one TOML file in `themes/`, and dusk also reads
`~/.config/dusk/themes/*.toml`, so copying one there is the quickest way to
start. A file has a `name`, a `description`, a built-in `base`, and four
optional tables:

```toml
name = "harbor"
description = "Fog over a dark harbor"
base = "nord"

[colors]
"ui.bg" = "#1b2330"
keyword = "#e0a458"

[styles]
keyword = "bold italic"

[glyphs]
brand = " ~harbor~ "

[labels]
normal = "DRIFT"
```

The names of every color, glyph, and label are listed in dusk's README under
Themes.

## Development

```
rvpm build
rvpm test
```

`src/pack.rv` holds the mood and clock tables and the chaos generator;
`src/main.rv` wires them to dusk with
[dusk-plugin](https://github.com/martian56/dusk-plugin).

## License

MIT
