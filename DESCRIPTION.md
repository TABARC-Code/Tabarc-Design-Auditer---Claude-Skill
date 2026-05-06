# Tabarc Design Auditor

A Claude skill set for production-grade frontend design work. Seven structured files covering the full design cycle: shape, craft, critique, animate, polish, harden, ship.

---

## The Short Version

Most AI design output looks like AI design output. Same reflex palettes, same card grids, same gradient text that nobody should be producing in 2025, same hero layouts that every SaaS landing page has been recycling since approximately 2019.

TDA gives Claude a proper design framework instead of vibes. It enforces a process (brief before code, grammar lock before batch production, browser test before ship), a set of design laws (OKLCH colour, 8px spatial grid, physics-based motion, type hierarchy with actual ratios), and a list of banned patterns that exist because they're all genuine design failures dressed up as aesthetic choices.

There are seven files. The main skill routes commands. The subskills handle the specialist work: motion design with a physics-first philosophy and fourteen specific pitfalls, slide decks with a format decision gate and PPTX constraint handling, heuristic critique with five-dimension scoring, typography, spatial design, and colour strategy.

Zero external dependencies. Installs by putting a folder in the right place. Works with Claude's skill system.

---

## What's in the Box

```
SKILL.md              Core — commands, design laws, craft workflow, brand asset protocol
TDA-motion.md         Physics-first animation, 14 pitfalls, easing library, seekable loop architecture
TDA-critique-audit.md 5-dimension heuristic scoring, technical audit, the AI slop test
TDA-slides.md         Format gate, grammar lock-in, PPTX constraints, keyboard navigation
TDA-typography.md     Modular scale, weight contrast, measure, font loading, readability checklist
TDA-spatial.md        8px grid, spacing hierarchy, optical alignment, whitespace management
TDA-color.md          OKLCH-first, four strategy levels, neutral tinting, full theme architecture
```

---

## Commands

`teach` `shape` `craft` `document` `extract` `critique` `audit` `polish` `bolder` `quieter` `distill` `harden` `onboard` `animate` `colorize` `typeset` `layout` `delight` `overdrive` `clarify` `adapt` `optimize` `live`

Each routes to the appropriate specialist mode. Or just describe what you need and it works it out.

---

## The Banned List

Side-stripe borders. Gradient text. Glassmorphism by default. The hero-metric SaaS template. Identical card grids. Modals as a first instinct. Em dashes in UI copy.

Absolute. No exceptions.

---

## What It's For

It's for people who want Claude to behave like a competent senior designer with consistent principles, not a different aesthetic sensibility every session. It's not autonomous. It works with you. The judgment is still yours. TDA just makes sure the framework supporting that judgment is coherent and doesn't change on a whim.

---

**Author:** TABARC-Code  
**Version:** 1.0  
**Licence:** MIT
