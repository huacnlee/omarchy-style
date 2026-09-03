# Omarchy Community Design System

> Brand, interface, website, poster, logo, icon, and keyboard-shortcut guidance for AI and human designers.
>
> Version 1.1 · Derived from the Omarchy website, Manual, the official `basecamp/omarchy` repository, and community visual references · 2026-09-03

## 0. How to use this document

This file is the single entry point for Omarchy's community visual and interaction language. Before designing, identify which layer the artifact belongs to:

1. **Brand core:** Wordmark, typographic character, terminal syntax, keyboard-first behavior, square construction, and direct copy. These must remain stable.
2. **Theme system:** Backgrounds, foregrounds, accents, status colors, and wallpapers. Use semantic color roles; never mistake one theme for the permanent brand palette.
3. **Community expression:** Cities, meetups, cultural symbols, pixel illustration, photography, and local color. This layer may vary boldly while remaining anchored by the first two.

When rules conflict, use this priority: **usability and accessibility > Omarchy product behavior > brand recognition > one-off creative expression**.

## 1. Brand essence

Understand Omarchy as:

> An efficient, adaptable, keyboard-driven modern Linux workstation that combines the honest structure of the terminal with the aesthetic freedom of a personal desktop.

### 1.1 Core character

- **Beautiful:** Beauty comes from a coherent environment across theme, wallpaper, terminal, and application colors—not decorative accumulation.
- **Modern:** Clear, responsive, automatically tiled, and suited to current hardware and workflows.
- **Opinionated:** Defaults are deliberate. Do not return every decision to the user.
- **Keyboard-first:** The interface should feel like a command system: learnable, predictable, and increasingly fast with practice.
- **Hackable:** Configuration, scripts, paths, and state should feel natural and visible rather than hidden.
- **Community-local:** Community artwork may strongly express its city, landmarks, language, and local culture.

### 1.2 Atmosphere scales

- Product UI density: **8/10 — Cockpit Dense**.
- Website and documentation density: **5/10 — Daily App Balanced**.
- Community poster density: **6–9/10**, depending on illustration complexity.
- Layout variance: **4/10**. Begin with a strict grid and introduce offsets only with purpose.
- Motion intensity: **3/10**. Fast, restrained, and tied to state changes.
- Roundness: **1/10**. Square by default; small controls, code blocks, and media may use slight rounding.

### 1.3 At-a-glance recognition

An Omarchy artifact should satisfy at least four of these seven conditions:

- It uses the official Omarchy wordmark or its approved ASCII/pixel logic.
- Monospaced typography establishes the primary information hierarchy.
- It uses a dark terminal canvas or a rigorously themed light canvas.
- Thin borders, tiled grids, and limited shadows define the structure.
- One clear accent connects focus, links, selection, and key decoration.
- Copy is short, specific, and slightly personal rather than corporate boilerplate.
- Graphics include real elements from terminals, cursors, pixels, city silhouettes, or desktop workflows.

## 2. Logo system

### 2.1 Official wordmark

- Use the official `logo.svg`. Never redraw it manually.
- The mark follows the pixel/military-display logic of **Delta Corps Priest 1**. The official ASCII wordmark is [`logo.txt`](https://github.com/basecamp/omarchy/blob/quattro/logo.txt); `omarchy show logo` prints it, and `omarchy transcode ascii <image>` converts other silhouettes.
- The formal brand name is always **Omarchy**. The graphic wordmark may use its all-caps `OMARCHY` form.
- Render the wordmark in one solid theme foreground, accent, black, or white. Never add multicolor gradient fills, glow outlines, bevels, stretching, or perspective distortion.
- Keep pixel edges crisp. Raster exports must use integer scaling and must not introduce bilinear blur.

### 2.2 Clear space and minimum size

- Let `x` equal the width of one vertical pixel stroke in the wordmark. Preserve at least `2x` clear space on every side.
- The complete wordmark should be at least `160px` wide in digital interfaces. Below that size, use the official Omarchy icon or the plain-text name.
- A poster wordmark may occupy `68–90%` of the canvas width, but it must not touch the edge. Keep at least one body-text line-height between it and the city or event name.
- Never overlap the wordmark with people, buildings, window borders, or other text.

### 2.3 ASCII mark

- Prefer the official `logo.txt` in terminals, About surfaces, screensavers, and developer-facing pages.
- Place ASCII art in a monospaced environment and preserve its original line breaks. Do not wrap it or compress character spacing.
- Custom ASCII art should use single-column characters. Emoji and double-width characters break the grid and should not form structural artwork.
- When converting an image, use a crisp silhouette with high contrast. Do not convert a complex photograph directly to ASCII.

### 2.4 Compact icon

- `U+E900` in the private Omarchy icon font is the official Omarchy mark. Product interfaces should use it or the official SVG.
- Brand icons are monochrome and inherit the current theme's foreground or accent.
- Do not crop a random letter from the wordmark to invent a new icon. Use the approved compact mark.

### 2.5 Wordmark-style display lettering

[Omarchy Font](https://github.com/markcuda/Omarchy-Font) (family `Omarchy Font`, MIT, a community project by Mark Cuda) is the wordmark's construction as an installable TTF: its `O M A R C H Y` glyphs match `logo.svg` pixel for pixel, and the remaining letters, digits, and ASCII punctuation follow the same Delta Corps Priest 1 rules. Download [`Omarchy Font.ttf`](https://github.com/markcuda/Omarchy-Font/blob/main/Omarchy%20Font.ttf) from that repository when a task needs it; this Skill does not bundle it.

Use it for city and event labels such as `CHENGDU MEETUP`, short poster or hero headlines that must share the wordmark's voice, and live-text renderings of the wordmark in HTML or slides when embedding the SVG is impractical.

- `logo.svg` stays the canonical wordmark. When Omarchy Font sets `OMARCHY`, compare it against the SVG at `1×` before delivery.
- Uppercase only; the font is unicase. Keep `letter-spacing: 0` and weight `400`; cell spacing is built in, and faux bold, italic, stretching, outlines, and gradients break the pixel grid.
- Use integer pixel sizes and integer-scaled raster exports so the 1:2 cells land on whole pixels.
- One solid color per line from `foreground`, `accent`, black, or white.
- Keep it subordinate to the wordmark: a city label sits below the wordmark, smaller and never heavier.
- Never use it for body copy, navigation labels, table data, or instructions; ASCII coverage only, so pair CJK text with the CJK face from § 4.1.
- Credit it as community lettering when provenance is requested; it is not an official Basecamp asset.

```css
@font-face { font-family: "Omarchy Font"; src: url("Omarchy Font.ttf") format("truetype"); }
.city-label { font: 400 32px/1 "Omarchy Font", "JetBrains Mono", monospace; letter-spacing: 0; text-transform: uppercase; }
```

## 3. Color system

### 3.1 Stable brand, variable themes

Omarchy does not have one permanent “brand green” for every context. The current website uses a Tokyo Night family palette, while the operating system can retint terminals, window borders, editors, browsers, the top bar, menus, notifications, OSDs, and the lock screen together. Future work must model color through semantic roles.

Every theme should define at least:

```toml
mode = "dark" # or "light"

accent = "#7AA2F7"
selection = "#292E42"
muted = "#414868"

background = "#1A1B26"
dark_background = "#13141C"
darker_background = "#0E0E14"
lighter_background = "#24283B"

foreground = "#A9B1D6"
dark_foreground = "#565F89"
light_foreground = "#B4BEE6"
bright_foreground = "#C0CAF5"

red = "#F7768E"
yellow = "#E0AF68"
orange = "#EB927B"
green = "#9ECE6A"
cyan = "#449DAB"
blue = "#7AA2F7"
magenta = "#AD8EE6"
brown = "#75493D"
```

These values are the website and Tokyo Night baseline, not mandatory permanent colors for every Omarchy artifact.

### 3.2 Semantic roles

| Role | Purpose | Rule |
|---|---|---|
| `background` | Main page, window, and menu surface | Primary canvas; do not add purposeless gradients |
| `dark_background` | Deeper immersive surface | Terminal depth, media background, footer |
| `darker_background` | Deepest surface | Scrims, edges, lowest background layer |
| `lighter_background` | Raised surface | Code blocks, list hover, secondary panels |
| `foreground` | Body copy and standard UI | Must meet readable contrast |
| `bright_foreground` | Headings and input cursor | Highest text level; use sparingly |
| `dark_foreground` | Secondary information | Placeholders, comments, disabled items |
| `accent` | Focus, links, and current item | Use one primary accent per screen |
| `selection` | Text and list selection background | Pair with `bright_foreground` |
| `muted` | Dividers, comments, and tracks | Never use for critical copy |
| `red` | Error, danger, recording, and alert | Do not confuse brand accent with error |
| Other ANSI colors | Charts, code, and status | Use only with meaning; avoid rainbow UI |

### 3.3 Website baseline palette

When an artifact needs the official website feel and no theme is specified, use:

- **Night Canvas** `#1A1B26`: Main page background.
- **Storm Surface** `#24283B`: Code blocks and raised surfaces.
- **Terminal Blue** `#7AA2F7`: Buttons, links, and primary emphasis.
- **Terminal White** `#C0CAF5`: Body copy and high-contrast text.
- **Omarchy Green** `#9ECE6A`: ASCII wordmark, numbering, and list markers.
- **Terminal Cyan** `#7DCFFF`: Bright informational links. The system theme's cyan may be darker; use this value for the website presentation.
- **Muted Terminal** `#414868`: Borders, comments, and low-level information.
- **Pure White** `#FFFFFF`: Highest-level headings or hover peaks only; never a large dark-theme surface.

### 3.4 Community poster color

- Choose one parent theme per poster: black-and-green terminal, Tokyo Night blue, sunset magenta/orange, regional flag colors, or a local nightscape palette.
- Use **one primary accent plus no more than two supporting status colors**. Imagery may contain more color, but text and framework remain constrained.
- Black and green are not the only answer. Berlin, Hamburg, Warsaw, and Leiden show that monochrome pixel linework works; Dubai, Brno, and Seoul show that themed photography and illustration also work.
- Use a flag only in a clearly relevant regional context. Do not force its colors across every UI element.
- Local pixel dithering, scanlines, and grain are allowed. Avoid blurry neon outer glow.

### 3.5 Contrast and state

- Body copy must meet WCAG AA against its background. Small text and shortcut hints should reach at least `4.5:1`.
- Focus must not rely on color alone. Combine color with border, fill, cursor, or weight.
- Prefer `red`, `yellow/orange`, and `green` for error, warning, and success respectively, paired with text or an icon.
- A light theme must invert the full hierarchy rather than merely switching the background to white. Flexoki Light's warm `#FFFCF0` canvas and `#100F0F` ink are the reference.

## 4. Typography

### 4.1 Font families

- **Product UI, website, documentation, body text, numbers, and shortcuts:** `JetBrains Mono`.
- **The actual Linux desktop:** `JetBrainsMono Nerd Font`, the system `monospace` alias that also supplies every functional UI glyph (§ 6).
- **Wordmark:** Official SVG or `logo.txt`. Never typeset it in JetBrains Mono or a generic pixel font.
- **Wordmark-style display lines:** `Omarchy Font`, per § 2.5.
- **Brand marks:** The private `omarchy` icon font, only for the glyphs it defines (§ 6).
- Fallback: `"JetBrains Mono", "JetBrainsMono Nerd Font", ui-monospace, monospace`.

Do not corporate-wash Omarchy with Inter, generic sans serif, or serif typography. For CJK text, choose a monospaced or visually stable fallback that aligns with the Latin baseline. Test `Noto Sans Mono CJK` or `Sarasa Mono` on the target platform; do not assume bilingual text aligns automatically.

### 4.2 Product UI scale

Use the shell's `12px` base:

| Token | Size | Use |
|---|---:|---|
| `caption` | `10px` | Very short metadata and auxiliary hints |
| `body-small` | `11px` | Secondary information in dense lists |
| `body` | `12px` | Default UI text |
| `subtitle` | `13px` | Group subtitles |
| `title` | `14px` | Panel titles and emphasized controls |
| `heading` | `16px` | Page and dialog headings |
| `display` | `24px` | Status numbers and important results |
| `display-large` | `28px` | Large status or supporting brand display |

- Website body copy should use approximately `clamp(13px, 1.25vw, 16px)`, `1.4–1.5` line-height, and a maximum measure of `68ch`.
- Establish hierarchy through weight, color, and spacing rather than enormous type.
- Use monospaced numerals for dates, temperatures, progress, and system state so columns remain aligned.

### 4.3 Weight and case

- Body text uses `300–400`; links, headings, and buttons use `700`. Avoid unnecessary intermediate weights.
- Product menus use natural title or sentence case: `File manager`, `Default Browser`, `With desktop audio`.
- Website buttons may use uppercase with compact labels: `MANUAL`, `ISO`, `GITHUB`.
- `OMARCHY` may be uppercase in posters. City names, dates, and event names may also be uppercase, but body copy should not be.
- Do not fake futurism with excessive tracking. Use controlled letter spacing only for short place names, metadata, or pixel subtitles.

## 5. Imagery and illustration

### 5.1 Community poster composition

Prefer a 1:1 canvas with this vertical structure:

1. Omarchy wordmark at approximately `70–88%` of canvas width.
2. City, event, or year as the second recognition layer.
3. City landmark, community scene, or thematic graphic as the main narrative area.
4. Factual information such as date, location, openness, and sponsor.

Three visual modes are recommended:

- **Pixel linework:** Black background, one- or two-color landmark skyline, reflected water, dot matrix, and compact terminal symbols.
- **Themed illustration:** Pixel or retro-futurist imagery with high-contrast sunsets, night cities, roads, vehicles, or regional landscapes.
- **Real scene plus pixel typography:** Low-light photography or illustrated photography paired with the official wordmark and monospaced information.

### 5.2 Content rules

- Landmarks must be recognizable and genuinely local. Never generate a generic skyline and label it as a real city.
- When people represent community, show authentic collaboration, computers, and gatherings rather than generic business handshakes.
- Linux or Tux may appear as a cultural symbol, but not every image needs it.
- Use official Arch, Hyprland, and partner assets and keep them subordinate to Omarchy.
- Verify cars, buildings, flags, and sponsor marks. Do not fabricate or combine nonexistent details.

### 5.3 Texture

- Pixel art: Hard edges, limited palette, integer pixels, controlled dithering.
- Photography: Night scenes, low light, screen glow, and real working environments. Preserve shadow; avoid candy-colored HDR.
- Retro-futurism: Scanlines, CRT grain, dot matrix, and low-resolution sunsets are allowed. Generic purple-blue AI neon and purposeless circuit traces are not.
- Texture must never reduce text contrast. Use a solid scrim rather than glow outlines to restore readability.

### 5.4 Extended visual dialects

Community applications do not all need to imitate a system settings panel. These dialects remain compatible with the Omarchy core:

- **Vintage print/advertising:** Aged paper, halftones, faded ink, 1970s–1990s advertising composition, and opinionated slogans. Display type may vary, while system windows, data, and controls return to monospace.
- **Highly saturated themed desktop:** Wallpaper may be bold, cinematic, or synthwave. Floating panels need sufficiently opaque theme surfaces and clear borders.
- **Playful utility:** Pets, gamified status, and pixel animation may be humorous. Progress, actions, and errors must remain accurate.
- **Single-purpose panel:** Car, rocket, headphones, or AI quota panels may build domain-specific information architecture around a real object while retaining terminal labels, aligned numbers, and fast actions.

Experimental lettering, vintage type, and unofficial logos must be identified as event or community artwork and must not replace official brand assets.

## 6. Icon design

Omarchy ships no SVG icon set. Every interface icon is a text glyph from one of two fonts:

| Kind | Font | Where it comes from |
|---|---|---|
| Functional and object icons: menus, bar, weather, status | `JetBrainsMono Nerd Font` (the system `monospace`) | The icon sets bundled in every [Nerd Font](https://www.nerdfonts.com/cheat-sheet): Material Design Icons `nf-md-*` (`U+F0001`–`U+F1AF0`), Font Awesome `nf-fa-*`, Codicons `nf-cod-*`, Octicons `nf-oct-*`, Devicons `nf-dev-*`, Seti `nf-seti-*`, Weather `nf-weather-*` |
| Brand marks that Nerd Fonts lacks | Private `omarchy` icon font, `U+E900`–`U+E908` | [`default/fonts/omarchy/omarchy.ttf`](https://github.com/basecamp/omarchy/tree/quattro/default/fonts/omarchy) in the official repository; its README lists every glyph and source. Installed to `/usr/share/fonts/omarchy/omarchy.ttf` |

Menu rows draw `icon` in the menu font; a brand row adds `"iconFont":"omarchy"` ([`docs/menu.md`](https://github.com/basecamp/omarchy/blob/quattro/docs/menu.md)). The bar launcher is `U+E900` in the same font.

Reuse the glyphs the official menu already uses so prototypes match the desktop. The full list is [`default/omarchy/omarchy-menu.jsonc`](https://github.com/basecamp/omarchy/blob/quattro/default/omarchy/omarchy-menu.jsonc); the roots are:

| Row | Codepoint | Nerd Font name | Row | Codepoint | Nerd Font name |
|---|---|---|---|---|---|
| Apps | `U+F003B` | `nf-md-apps` | Update | `U+F021` | `nf-fa-refresh` |
| Learn | `U+F09D1` | `nf-md-brain` | About | `U+EA74` | `nf-cod-info` |
| Trigger | `U+F14DE` | `nf-md-rocket_launch` | System | `U+F011` | `nf-fa-power_off` |
| Style | `U+EBCF` | `nf-cod-wand` | Lock | `U+F023` | `nf-fa-lock` |
| Setup | `U+E615` | `nf-seti-config` | Logout | `U+F0343` | `nf-md-logout` |
| Install | `U+F0249` | `nf-md-floppy` | Reboot | `U+F0709` | `nf-md-restart` |
| Remove | `U+F0B4C` | `nf-md-tab_remove` | Shutdown | `U+F0425` | `nf-md-power` |

Brand glyphs in `omarchy.ttf`: `U+E900` Omarchy, `U+E901` Pi, `U+E902` OpenCode, `U+E903` omp, `U+E904` Grok, `U+E905` Codex, `U+E906` LM Studio, `U+E907` Ollama, `U+E908` T3 Code. Agents that Nerd Fonts already covers stay on Nerd Font glyphs: Claude `U+F06C4`, Copilot `U+F4B8`, Gemini `U+F0AE2`.

In HTML prototypes, self-host both fonts with `@font-face` (`JetBrainsMonoNerdFont-Regular.ttf` from the `JetBrainsMono.zip` [Nerd Fonts release](https://github.com/ryanoasis/nerd-fonts/releases), `omarchy.ttf` from the official repository) and place each glyph in a fixed-width span with `aria-hidden="true"` and a text label. When a font cannot ship, inline the same glyph as a monochrome SVG from its origin set at `currentColor` and keep the codepoint in a data attribute. Do not import Simple Icons, Lucide, Heroicons, Font Awesome CSS, Material Symbols, or any other library as the interface icon set.

- Design new glyphs on a `24 × 24` or `32 × 32` grid with consistent visual weight, aligned with the text baseline.
- Outline icons should use approximately `1.5–2px` strokes. Pixel icons must land on the integer grid.
- Default to no container, gradient, or shadow. Only application icons require an independent tile.
- Place menu icons in a fixed-width column so varying glyph widths never move labels.
- Brand marks are monochrome. Selection changes them to `accent`; it does not add glow.
- Do not replace functional icons with emoji. Emoji may be user content, not system navigation language.

### 6.1 Brand glyph sources

Simple Icons is a source for adding marks to the `omarchy` icon font, not a UI icon library. Reach for a new brand glyph only when a Nerd Font glyph would misrepresent the thing: one robot for four AI apps justifies real marks; a folder or microphone does not. See [`agents/skills/icon-font.md`](https://github.com/basecamp/omarchy/blob/quattro/agents/skills/icon-font.md).

- First choose the flat monochrome mark published by the brand. Use a redraw from [Simple Icons](https://simpleicons.org/) only when the brand provides no suitable source.
- Input must be a monochrome SVG containing exactly one `<path>`. The menu recolors it with the current theme's foreground and selection colors; original colors are discarded.
- Do not use ordinary app favicons. They are commonly multicolor, placed on a container tile, or split across several paths.
- Two-tone marks are a trap. Every path becomes one foreground color, so a logo that depends on light and dark halves turns into an unreadable blob.
- Judge the source by one test: does its solid-color silhouette remain recognizable? Reject marks dependent on fine internal texture, lettering, or tiny negative space.
- Record the brand, source URL, Private Use Area codepoint, and relevant notes in the font README.

### 6.2 Official font workflow

Do not edit `omarchy.ttf` manually. In the official repository, use:

```bash
omarchy dev font list
omarchy dev font add ollama https://simpleicons.org/icons/ollama.svg
```

`add` fetches the SVG, scales it into the `64..960` coordinate box shared by existing marks so it lands at their optical size, appends it at the next free Private Use Area codepoint, and updates the font README. It prints the codepoint and glyph. Verify the result in both normal and selected menu states.

## 7. UI design language

### 7.1 Grid and spacing

- Prefer explicit tiling and CSS Grid. The interface should feel like a readable window-manager layout, not a cloud of floating cards.
- Base spacing sequence: `2, 3, 4, 6, 8, 10, 12, 14, 18px`; large pages may extend to `24, 32, 48, 64px`.
- Shell baseline: compact inner space with greater outer separation. Official Hyprland defaults are `gaps_in: 5px`, `gaps_out: 10px`, and a `2px` border.
- Choose content width by task: approximately `50em` for reading; no more than `1600px` for a complex workbench, with outer margins.
- Below `768px`, collapse to one column. Page-level horizontal scrolling is a failure; code and tables may scroll within local containers.

### 7.2 Geometry

- System windows default to `0px` radius, no window shadow, and no blur.
- Buttons and search-result containers may use subtle `0.3–0.5em` rounding. Do not use pill buttons.
- Use `1–2px` borders and spacing for structure rather than large shadows.
- Borders use `muted`, low-alpha foreground, or the current active-border color. Active windows and focus must be unmistakable.
- Use gradients only when the current theme explicitly defines an active-border gradient. Never invent a permanent “brand gradient.”

### 7.3 Surface hierarchy

- Page base: `background`.
- Raised surface: `lighter_background` or foreground at `4–8%` alpha.
- Hover/keyboard cursor: foreground `8%` fill plus `25%` border.
- Focus: Use the same visual vocabulary as hover so mouse and keyboard do not create separate systems.
- Selected: foreground `18%` fill; text may change to `accent` when useful.
- Pressed: foreground `22%` fill plus subtle press displacement.
- Full-screen menu scrim: `background` at approximately `50%` alpha.

### 7.4 Buttons

- Primary: `accent` fill, dark text, bold, and a short label. Usually allow only one primary action per region.
- Secondary: Transparent with a `1px` low-contrast border, or a text link.
- Product UI height starts at `28px`; touch-first web targets must be at least `44px`.
- Keep icon-to-label spacing near `1ch`. Use an icon only when it contributes meaning.
- Hover changes background, text, or border. It does not scale, rotate, or glow.
- Active may use `translateY(1px)`. Disabled catalog items remain visible, reduce contrast, and may show `✓` when already installed or satisfied.

### 7.5 Menus and lists

- A menu is a command tree, not marketing navigation. Each row leads to a clear noun destination or action.
- Use fixed icon, label, and optional shortcut/status columns.
- Default row height is `28px`: dense but scannable. Pointer hover and keyboard cursor share the same state.
- A submenu title may be more specific than its entry: `Browser` may open `Default Browser`.
- Mark current choices with `✓`. Installed disabled items remain visible and dimmed; Remove entries that do not apply may be hidden.
- Search labels, the final segment of stable IDs, and descriptions. Do not add aliases casually.

### 7.6 Inputs and forms

- Put labels above inputs, helper copy below, and errors adjacent to the field.
- Search may use a quiet underline: transparent background and a `1px` bottom border that switches to accent on focus.
- Configuration confirmation suits a terminal table: `Field | Value`, followed by a direct question such as `Does this look right?`.
- Highlight the default option with a solid row and expose direct keys such as `y Yes` and `n No`.
- Password, deletion, disk formatting, and other high-risk actions must state the consequence plainly. Humor must never obscure risk.

### 7.7 Notifications, OSDs, and status panels

- Use the theme background, foreground text, and a border derived from the active window.
- Structure information as icon/key value → short title → necessary one-line detail.
- Time, date, and battery copy should read naturally: `Friday 12:10 · 14 August 2026 · Week 33`.
- Rich weather and battery panels may use large numbers while preserving one thin border, no shadow, and no glass blur.
- Update state in place. Do not create a new card for every refresh.

### 7.8 Code, tables, and technical content

- Inline code uses a translucent `lighter_background`/`muted` fill and cyan or accent text.
- Code blocks may use at most `0.5em` radius. Never add fake macOS red/yellow/green window controls.
- Tables use `1px` low-contrast borders, left alignment, and compact cells. Right-align numeric columns.
- List markers, chapter numbers, and heading anchors may use green or accent for a terminal-index feel.
- Align long logs and system metrics into columns; use monospace for all numbers.

### 7.9 Empty, loading, and error states

- An empty state explains what belongs there and which action populates it. Do not show only `No data`.
- Loading uses low-contrast skeletons matching the final layout or a one-line terminal progress indicator, not a large circular spinner.
- Errors name the failed object, reason, and recovery action. Technical users may expand the command or log.
- Success feedback is brief—`Theme applied`, `Copied`, or `Installed`—and dismisses automatically.

### 7.10 Data panels and domain widgets

- Panel headers use object icon + object name + short state/subtitle, with one key value optionally aligned right.
- Group by task with thin dividers rather than nested cards: overview → progress → details → actions.
- Labels use muted foreground; values use normal or bright foreground. Units stay attached to aligned values.
- Progress tracks use muted surfaces and foreground/accent fill. Switch to a status color only at a meaningful threshold.
- Binary toggles, modes, and current choices require position, fill, or `✓`; text color alone is insufficient.
- Keep no more than two or three peer actions at the bottom. The primary action uses solid or selected fill; others use outlines.
- A panel may float over a vivid wallpaper, but its scrim and surface must remain opaque enough that the image does not pollute body copy.

### 7.11 Plugin directories and marketplaces

- Plugin browsing is a comparable collection and may use a regular card grid. This is distinct from a marketing page's generic three-card feature row.
- Card order is fixed: preview → name and trust/popularity → author and type → one concrete sentence → tags and installation method.
- Keep card height, metadata, and action positions consistent for horizontal scanning. Truncate overflow and provide a details view.
- `Verified`, `Unverified`, `Updated`, and `Manual setup` represent maintenance and risk. Show them with clear text and contrast, never color alone.
- Favorites, likes, views, and copies use monochrome icons with monospaced numbers and remain subordinate to the plugin's purpose.
- Responsive grid: three columns on large screens, two on medium screens, and one on small screens. Use a `1px` border, square geometry, and no exaggerated hover elevation.
- Search and filters for category, verification, and setup method must be keyboard-accessible. Card focus and internal action order must be explicit.

### 7.12 Dense desktop applications

- Mail, music, files, and administration tools may use a classic master-detail structure: navigation sidebar → list/collection → detail. Do not wrap every item in an independent floating card.
- Prefer three columns on wide screens. Narrow windows become a top mode/category strip plus one list; opening an item enters a single detail view with a visible `← Back` action.
- A persistent footer may expose contextual shortcuts such as `j / k move`, `Enter open`, and `e archive`. Show only commands relevant to the current view.
- Use a fixed list-row structure: title, secondary summary, time/status, and inline actions. Hover and keyboard cursor share the same fill. Reveal low-frequency actions only on the cursor row when that reduces noise.
- Media applications may let album artwork provide content color while application chrome remains themed, bordered, and monospaced.
- An empty detail area may teach the interface with an object icon, collection name, item count, and three to six essential keyboard commands.
- Make search scope explicit with copy such as `In Red Hot Chili Peppers`; avoid ambiguous filtering.

### 7.13 Shell component state model

- A panel displays only one keyboard cursor at a time. The panel root maintains `focusSection + selectedIndex`; mouse entry updates the same model rather than creating a second highlight.
- Initial open may show no highlighted row. Reveal the single cursor after the first directional key or pointer movement.
- State priority is fixed: `pressed > activeFocus > hover/cursor > selected/active > idle`.
- `selected` is persistent choice, `cursor` is the transient navigation target, and `activeFocus` receives text or control input. Do not collapse them into one state.
- Reserve the maximum state-border width so hover or focus never changes component size or moves neighbors.
- Tooltip delay is approximately `400ms`. Use tooltips only for non-obvious icons or actions and provide equivalent help for keyboard focus.
- Section headings use small, bold, muted terminal small-caps character. Dividers use a `1px` hairline at approximately `12%` foreground alpha.

## 8. Website design

- Preferred page sequence: ASCII/official wordmark → one-line proposition → core entry points → real product demonstration or content.
- A homepage may center the wordmark. Content and tool pages should use left alignment and a clear grid.
- Large navigation sets may wrap naturally. Preserve even gaps and avoid stranding the last button awkwardly.
- Links use the accent and retain underlines; hover lifts them to bright foreground.
- Documentation sidebars use zero-padded chapter numbers, low-contrast default entries, and a high-contrast current entry.
- Content headings should be only `1.1–1.75×` body size. Technical documentation does not need giant marketing headlines.
- Body images may use `0.5em` radius. Posters, pixel art, and logos must not inherit forced rounding.
- Desktop sidebars may be sticky. Mobile hides the sidebar but retains search and chapter navigation access.

## 9. Motion and feedback

- Default transition: `150ms cubic-bezier(0.33, 1, 0.68, 1)`.
- Window entry may use a quick `popin` from approximately `87% → 100%`; exit should be faster.
- Animate only `transform` and `opacity`. Do not spend continuous CPU on decoration.
- Approved brand micro-motion: a brief green glint crossing ASCII art every few seconds, followed by complete stillness.
- Lists do not need waterfall entrance animation. Keyboard response must be immediate.
- Respect `prefers-reduced-motion`; all information must remain complete without animation.
- No bouncing arrows, infinitely floating cards, breathing halos, layered parallax, or custom cursors.

## 10. Copy style

### 10.1 Voice

- **Direct:** State the action and result.
- **Specific:** Write `Open file manager in terminal's current directory`, not `Boost your workflow`.
- **Opinionated, not arrogant:** Recommend defaults and explain how to change them.
- **Technically honest:** Paths, shortcuts, risks, and limitations may be stated directly.
- **Slightly personal:** Documentation may use natural speech and restrained humor. Errors, security, and destructive actions remain serious.

### 10.2 Microcopy

- Menu labels use short nouns or verbs: `Apps`, `Style`, `Install`, `Lock`, `Share`.
- Launch entries use object names: `Terminal`, `Browser`, `File manager`.
- Toggles use `Toggle + object`; defaults use `Default + object`.
- In progress uses present participle: `Installing…`; completion uses past tense: `Installed`.
- Dangerous actions name their object: `Reset Computer`, `Erase disk`, not merely `Continue`.
- Avoid `Elevate`, `Unleash`, `Seamless`, `Next-gen`, `Supercharge`, and `Reimagine`.
- Do not use emoji as UI voice. Nerd Font glyphs are interface syntax, not copy.

### 10.3 Punctuation and numbers

- English UI uses sentence case; menu labels do not end with periods.
- Descriptive sentences use full punctuation. Terminal output may omit the final period.
- Write shortcuts as `Super + Shift + F`, with spaces around `+`.
- Put paths, commands, and key names in backticks. Write UI paths as `Style > Font`.
- Follow the target locale's date and time convention. Never mix `12:10 PM` and `12:10` in one interface.

## 11. Naming

### 11.1 User-facing names

- Brand: `Omarchy`, never `OMarchy`, `O'Marchy`, or `Omarchy OS` unless the context requires naming the category.
- Prefer concrete objects for features: `Theme`, `Background`, `Font`, `Screenrecord`.
- Keep sibling menu entries grammatically parallel. Do not mix nouns with marketing phrases.
- Preserve official capitalization: `Hyprland`, `Neovim`, `GitHub`, `ChatGPT`, `OpenCode`.

### 11.2 Menu IDs

- Use lowercase `kebab-case` with dotted hierarchy: `trigger.capture.screenshot`, `setup.default.browser`.
- IDs define the navigation tree; do not duplicate hierarchy with a separate `parent` field.
- Treat published IDs as stable interfaces. Renaming must account for CLI routes and user scripts.
- Reserve `aliases` for established names users already type. Do not use them as a keyword dump.

### 11.3 Commands and files

- Every user command begins with `omarchy-`.
- Purpose prefixes include `launch-`, `install-`, `setup-`, `toggle-`, `theme-`, `update-`, `capture-`, `restart-`, `refresh-`, `pkg-`, and `hw-`.
- User-facing CLI groups follow `omarchy theme set <name>`.
- Community theme repositories should use `omarchy-[theme-name]-theme`.
- Theme directories and technical IDs use lowercase kebab-case; display names may use natural title case.
- Name images by purpose and place: `meetup-seoul-2026-square.webp`, never `final-final-2.png`.

### 11.4 Plugin names

- Official plugin IDs use the reserved `omarchy.*` namespace, such as `omarchy.clock` and `omarchy.network`.
- Third-party plugins use an author or organization namespace such as `alice.weather`; they must not claim `omarchy.*`.
- Manifest `id` is a stable machine identifier; `name` is human-readable. Do not include a version in either.
- A plugin may declare `bar-widget`, `panel`, `overlay`, `menu`, `service`, or `bar`. Its name and preview must accurately reflect its entry points.
- Personalized clones use `<username>.<plugin>`; a display name such as `My Clock` clearly identifies a private derivative.

## 12. Keyboard shortcuts

### 12.1 Modifier grammar

Omarchy shortcuts follow a hierarchy:

| Pattern | Meaning | Example |
|---|---|---|
| `Super + key` | Core navigation and window action | `Super + Space` menu; `Super + F` fullscreen |
| `Super + Shift + key` | Launch a primary application | `Super + Shift + F` file manager |
| `Super + Ctrl + key` | System tool, panel, or direct control | `Super + Ctrl + T` Activity |
| `Super + Alt + key` | Alternate version or secondary entry | `Super + Alt + Return` Tmux |
| Add `Shift/Alt/Ctrl` | Variant within one action family | Private browser, previous item, dismiss all |

### 12.2 Assignment rules

- Choose a mnemonic letter first: `B` browser, `F` files, `T` terminal/activity, `K` keybindings.
- Keep variants on the same primary key and distinguish them with modifiers.
- Reserve `Super + Shift` for application launch, `Super + Ctrl` for system control, and `Super + Alt` for alternate modes.
- Every global shortcut must be discoverable through `Super + K` Keybindings.
- Check for conflicts before rebinding. Explicitly unbind an existing binding and tell the user what it previously did.
- Do not use four modifiers for frequent actions. Complex combinations are for low-frequency, dangerous, or advanced variants.
- Keyboard, pointer, and touch paths must produce the same state and result. Keyboard is never secondary.

### 12.3 Shortcut display

- Either render each key as an independent keycap with an ordinary `+` separator, or write `Super + Shift + F` in dense lists.
- Keycaps use a `1px` border, theme background, and monospaced bold type—never plastic 3D styling.
- Display modifiers as `Super` → `Ctrl` → `Shift` → `Alt` → primary key, while preserving established official order when documenting an existing binding.
- Use consistent names such as `Return`, `Escape`, `Backspace`, `Print`, and `Arrow Left`. Do not mix `Enter` and `Return` on one page.
- Keep shortcut columns on one line. On mobile, wrap the description below instead.

### 12.4 In-panel navigation

- List and grid panels support arrows and Vim keys: `j/k` vertically and `h/l` horizontally.
- `Return`/`Enter` activates the primary action, `Space` activates or toggles the current control, and `Escape` closes the panel.
- `Tab`/`Shift + Tab` moves between semantic sections rather than traversing dozens of read-only labels.
- Use `x` for deletion only when context makes it obvious and expose it in the footer hint. High-risk deletion still requires confirmation.
- While a text field is active, suspend panel-level shortcuts so text input and editing keys take priority; restore panel navigation afterward.
- Recommended footer format: `↑↓/jk row · ←→/hl adjust · Tab section · Backspace reset · Esc close`. Show only currently available actions.

## 13. Responsive design and accessibility

- Every primary action is keyboard-accessible, and focus order follows visual order.
- `:focus-visible` must be clear through accent or active border. Never remove outline without replacement.
- Touch targets are at least `44 × 44px`. Dense desktop shell rows may be `28px` high when full keyboard control exists.
- Icon buttons require accessible names. Hide decorative ASCII/SVG from assistive technology and provide a textual brand name.
- The interface remains usable at `200%` zoom. Body text should not fall below `13px`; primary web copy should normally be at least `16px`.
- Color is never the only signal. Pair status with text, icon, or `✓`.
- Pixel type is for wordmarks and short display lines, never long body copy or critical instructions.
- Check contrast, image scrims, and code highlighting independently in both dark and light themes.

## 14. Prohibited patterns

- Do not reduce Omarchy to “black background + neon green + hooded hacker.”
- No generic SaaS blue-purple gradients, glassmorphism, glowing rounded cards, or pill-heavy UI.
- Do not use three equal “feature cards” as the default marketing-page structure. Comparable collections such as a plugin marketplace may use a regular card grid.
- Do not replace the official wordmark with giant generic sans-serif marketing type.
- Do not use pixel fonts for body copy.
- Do not add radius and shadow to every container.
- Do not stack low-contrast gray text on a dark theme.
- Do not substitute emoji for functional icons, and do not import a third-party icon library in place of Nerd Font and `omarchy` icon-font glyphs.
- Do not invent fake terminal output, random hexadecimal strings, or meaningless code rain.
- Do not generate landmarks unrelated to the stated place or factually incorrect.
- Do not let decoration cross text, controls, or clickable regions.
- Do not hide the real consequences of a dangerous action.
- Do not invent shortcuts that conflict with official bindings.
- Do not hard-code a specific theme color as the permanent color of a cross-theme component.

## 15. AI generation checklist

Before generation:

- [ ] The artifact has been classified as brand core, product theme, or community expression.
- [ ] A target theme and `mode` are specified, or the Tokyo Night website baseline is intentionally selected.
- [ ] Official logo and icon assets are available rather than reconstructed from memory: `logo.svg`, `omarchy.ttf`, JetBrainsMono Nerd Font, and Omarchy Font when display lettering is needed.
- [ ] City, date, landmark, sponsor, and shortcut facts have been verified.

During generation:

- [ ] JetBrains Mono/Nerd Font syntax and the correct wordmark are used.
- [ ] One primary accent is used, and status colors retain semantic meaning.
- [ ] Grid, borders, and spacing carry structure; shadow and radius stay restrained.
- [ ] Copy is short, concrete, and actionable, with no AI marketing clichés.
- [ ] Hover, focus, selected, pressed, and disabled states are defined.
- [ ] Desktop and mobile layouts both work, with complete keyboard paths.

Before delivery:

- [ ] Pixel edges and wordmark clarity have been checked at `1×` and `2×`.
- [ ] WCAG contrast, keyboard focus, zoom, and reduced motion have been checked.
- [ ] Dark and light themes have been checked for hard-coded color leakage.
- [ ] Shortcuts have been checked against official Keybindings.
- [ ] Purposeless glow, gradient, glass, marketing cards, and decoration have been removed; panels with real hierarchy or comparison value remain.

## 16. Reusable AI design prompt

```text
Design this as part of the Omarchy community system.

Preserve the brand core: official sharp pixel/ASCII Omarchy wordmark, JetBrains Mono typography, terminal-native information structure, keyboard-first interaction, dense grid-based layout, thin borders, square geometry, restrained motion, and concise opinionated copy.

Treat color as a theme, not a fixed brand palette. Use semantic roles for background, darker/lighter surfaces, foreground levels, accent, selection, muted, and ANSI status colors. Use one primary accent per screen. Default to the official website's Tokyo Night palette only when no theme is specified.

For community artwork, ground the image in the real local city or culture. Choose pixel-line skyline, themed retro-futurist illustration, or authentic low-light community photography. Keep the official wordmark dominant and crisp. Avoid generic cyberpunk, neon glow, glassmorphism, pill-shaped UI, SaaS card grids, fake terminal noise, emojis as UI icons, and AI marketing copy.

Every interaction must define keyboard behavior and visible hover, focus, selected, pressed, disabled, loading, empty, success, and error states. Validate responsive layout, contrast, reduced motion, factual place details, and shortcut conflicts before delivery.
```

## 17. Sources

This system was derived from the following primary sources. When implementation changes, the official source and Manual take precedence:

- [Omarchy website](https://omarchy.org/): Website palette, JetBrains Mono, ASCII wordmark, buttons, and page structure.
- [Omarchy Manual](https://omarchy.org/manual/): Product voice, navigation, installation, themes, fonts, backgrounds, and usage model.
- [Hotkeys](https://omarchy.org/manual/hotkeys/): Official keyboard-shortcut system.
- [Navigation](https://omarchy.org/manual/navigation/): Keyboard-first operation and Hyprland tiling behavior.
- [Fonts](https://omarchy.org/manual/fonts/): Default JetBrainsMono Nerd Font and replaceable font system.
- [Branding](https://omarchy.org/manual/branding/): Logo, ASCII, screensaver, About, and Delta Corps Priest 1.
- [Making your own theme](https://omarchy.org/manual/making-your-own-theme/): Theme structure, cross-application color synchronization, and repository naming.
- [Omarchy CLI](https://omarchy.org/manual/omarchy-cli/): Command and menu-route model.
- [Shell Plugins](https://omarchy.org/manual/shell-plugins/): Plugin kinds, namespaces, installation safety, and user extension model.
- [Official source repository](https://github.com/basecamp/omarchy): `logo.svg`, `logo.txt`, themes, Hyprland, Shell, menu, and icon font.
- [Theming reference](https://github.com/basecamp/omarchy/blob/quattro/docs/theming.md): `colors.toml` semantics, Shell control states, and theme rendering.
- [Menu reference](https://github.com/basecamp/omarchy/blob/quattro/docs/menu.md): Menu IDs, providers, guards, and selected/disabled behavior.
- [Shell reference](https://github.com/basecamp/omarchy/blob/quattro/docs/omarchy-shell.md): Type scale, spacing, bar dimensions, and Shell tokens.
- [`Style.qml`, `Button.qml`, `PanelKeyCatcher.qml`, and visual verification guidance](https://github.com/basecamp/omarchy): State priority, single cursor, Vim navigation, tooltips, and visual verification.
- [Official `logo.svg`](https://github.com/basecamp/omarchy/blob/quattro/logo.svg) and [`logo.txt`](https://github.com/basecamp/omarchy/blob/quattro/logo.txt): Canonical wordmark assets.
- [Icon font](https://github.com/basecamp/omarchy/tree/quattro/default/fonts/omarchy) and [icon-font agent skill](https://github.com/basecamp/omarchy/blob/quattro/agents/skills/icon-font.md): Brand glyph codepoints, provenance, and the `omarchy dev font` workflow.
- [Menu definition](https://github.com/basecamp/omarchy/blob/quattro/default/omarchy/omarchy-menu.jsonc): Every functional Nerd Font glyph the desktop uses.
- [Omarchy Font](https://github.com/markcuda/Omarchy-Font): Community MIT TTF of the wordmark lettering for display lines.
- [Official theme palettes](https://github.com/basecamp/omarchy/tree/quattro/themes): Tokyo Night, Gruvbox, Catppuccin, Kanagawa, Osaka Jade, Flexoki Light, and others.
- User-provided official and community references: City posters, installer, wordmark, top bar, notifications, weather, plugin marketplace, domain widgets, dense applications, and multi-theme desktops.
