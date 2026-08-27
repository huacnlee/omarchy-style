---
name: omarchy-style
description: Use when designing, reviewing, or rewriting Omarchy-branded UI, websites, themes, posters, illustrations, logos, icons, product copy, menus, keyboard shortcuts, or community artifacts that must match Omarchy's official visual and interaction language.
---

# Omarchy Style

Apply Omarchy's official community design system across visual, interaction, and language work. Preserve the brand core while allowing themes and local community expression to vary.

## Required foundation

Read [references/design-system.md](references/design-system.md) completely before changing or creating an Omarchy artifact. Use [assets/logo.svg](assets/logo.svg) whenever the official wordmark appears; never redraw it with a font or ask an image model to reproduce it.

## Route by task

| Task | Required guidance |
|---|---|
| UI, settings, shell, panels, states | Design system §§ 3–7 and 13–15 |
| Website or documentation layout | Design system §§ 3–4, 7–10, and 13–15 |
| Product copy, labels, menus, naming | Design system §§ 10–11 |
| Keyboard shortcuts or hint rails | Design system § 12; verify existing bindings before proposing new ones |
| Logo, icon, or glyph | Design system §§ 2 and 6; use official assets and sources |
| Poster, illustration, city cover | Read [references/illustration-design.md](references/illustration-design.md) in addition to the design system |
| Theme or palette | Design system § 3 and official theme semantics; treat color as roles, not permanent brand colors |

For city artwork, verify unsupported local claims against authoritative sources during the task. Keep research notes outside the distributable Skill; include only the short rationale needed to explain the delivered concept.

## Shared contract

An Omarchy artifact must preserve:

- the official sharp wordmark or approved ASCII/icon form;
- JetBrains Mono / Nerd Font information hierarchy;
- terminal-native, keyboard-first structure;
- strict grids, square geometry, thin borders, and restrained effects;
- one primary semantic accent per screen or cover;
- concise, specific copy with honest paths, commands, states, and consequences;
- factual product behavior, local identity, branding, and shortcuts;
- positive, respectful regional representation built from locally meaningful landmarks, imagery, culture, and color;
- accessible contrast, visible focus, and usable responsive behavior where interactive.

Do not reduce Omarchy to black plus neon green. Do not substitute generic SaaS, cyberpunk, glassmorphism, rounded-card, or marketing-copy conventions.

## Community cover defaults

For Luma-style event covers, default to a 1:1 square. Omit dates, times, venues, URLs, QR codes, and organizer details unless explicitly requested. Default cover text is the official wordmark plus `<CITY> MEETUP`.

For multi-city sets, keep wordmark scale, safe area, city-label baseline, logical pixel scale, and semantic palette structure consistent. Preserve the user's city labels. Create 1–3 genuinely different covers per city:

- one when references support one dominant idea;
- two by default, using different visual modes and compositions;
- three when multiple verified anchors support equally strong stories.

Different styles are not recolors or crops. Save approved demonstrations under `assets/examples/<city>/` or `assets/examples/<city>-<mode>.<ext>`.

Every delivered city concept must include a short **local rationale**: the verified anchor, supporting cultural cue, and source of its palette. Prefer affirmative civic, cultural, natural, architectural, scientific, or community narratives. Exclude poverty spectacle, danger, disorder, political conflict, ethnic caricature, stigmatizing neighborhoods, and other negative regional framing unless the user explicitly requests critical documentary work.

## Delivery check

Before declaring completion, verify the relevant checklist in the design system plus these invariants:

- official assets are exact and unobstructed;
- text, names, dates, behavior, and shortcuts are accurate;
- theme colors have semantic roles;
- local symbols and landmarks are verified;
- decorative effects do not weaken hierarchy or readability;
- examples demonstrate the Skill without becoming mandatory templates.
