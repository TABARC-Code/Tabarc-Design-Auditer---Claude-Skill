# Tabarc Design Auditor (TDA)

A Claude skill set for production-grade frontend design. Not a component library. Not a style guide. A structured system for getting from vague brief to shippable interface without the usual detours through three rounds of "can you make it pop more."

Seven files. Zero external dependencies. Installs in about ninety seconds.

---

## What It Actually Does

TDA gives Claude a consistent design brain. Instead of generating whatever aesthetic felt right at inference time, it follows a structured process: shape the brief, lock visual direction, build to a production quality bar, iterate in browser, ship.

The subskills handle the specialist knowledge. Motion design has its own physics-first philosophy and a catalogue of fourteen animation pitfalls that will save you hours of "why is my absolute-positioned element floating to the document root" debugging. Slide decks have a full format decision gate so you don't spend three hours building something beautiful and then discover the client needs an editable PowerPoint. Critique uses a five-dimension heuristic scoring system. Colour is OKLCH throughout, because hex in 2025 is just inflicting suffering on yourself.

It also has opinions. Some fairly firm ones. There's a banned pattern list. Gradient text is on it. So is glassmorphism-as-default and the hero-metric SaaS template (big number, label, gradient background, you know the one). If you want a tool that just agrees with you, this probably isn't it.

---

## File Structure

```
TDA/
├── SKILL.md              Main skill — command routing, design laws, craft workflow
├── TDA-motion.md         Motion design — physics-first animation, 14 pitfalls, easing library
├── TDA-critique-audit.md Heuristic critique (5-dimension), technical audit, AI slop test
├── TDA-slides.md         Slide deck design — format gate, grammar lock-in, PPTX constraints
├── TDA-typography.md     Type scale, weight contrast, measure, font pairing, loading
├── TDA-spatial.md        8px grid, spacing hierarchy, optical alignment, whitespace
└── TDA-color.md          OKLCH palette design, four strategy levels, theme architecture
```

The main SKILL.md routes everything. Subskills load when needed based on the command or task type. You don't have to think about which file does what.

---

## Commands

```
teach          Set up PRODUCT.md and initial DESIGN.md
shape [f]      Plan UX/UI before writing a line of code
craft [f]      Full shape → build → iterate → ship cycle
document [t]   Generate DESIGN.md from existing code
extract [t]    Pull tokens and components into a design system

critique [t]   5-dimension heuristic design review
audit [t]      Accessibility, performance, responsive, SEO

polish [t]     Final quality pass
bolder [t]     Amplify safe or bland designs
quieter [t]    Tone down aggressive or cluttered designs
distill [t]    Strip to essence
harden [t]     Errors, i18n, edge cases, production readiness
onboard [t]    First-run flows, empty states, activation

animate [t]    Purposeful motion — loads TDA-motion.md
colorize [t]   Strategic colour for monochromatic UIs
typeset [t]    Font hierarchy, measure, loading
layout [t]     Spacing, rhythm, visual hierarchy
delight [t]    Personality and memorable touches
overdrive [t]  Past conventional limits

clarify [t]    UX copy, labels, error messages
adapt [t]      Responsive and cross-device
optimize [t]   UI performance
live [t]       Visual variant mode
```

You can also just describe what you need and it figures out the right approach. The command structure is there when you want precision.

---

## Installation

Drop the TDA folder into your Claude skills directory.

```
.claude/
└── skills/
    └── TDA/
        ├── SKILL.md
        ├── TDA-motion.md
        ├── TDA-critique-audit.md
        ├── TDA-slides.md
        ├── TDA-typography.md
        ├── TDA-spatial.md
        └── TDA-color.md
```

That's it. Claude will pick it up. No npm install. No config files. No YAML with seventeen nested keys.

---

## Design Laws (The Short Version)

A few things TDA enforces consistently, regardless of command.

**Colour is OKLCH.** Not hex. Not rgb(). OKLCH is perceptually uniform, works properly in dark mode, and means "slightly lighter" actually means slightly lighter across all hues. Pure `#ffffff` and `#000000` are banned. Every neutral gets tinted toward the brand hue.

**Themes require a scene.** Not "dark mode looks professional." Write one physical sentence: who uses this, where, under what light, in what mood. If the sentence doesn't force the answer, the answer isn't concrete enough.

**Spacing uses the 8px grid.** All of it. Margins, padding, gaps, border-radius. Everything is a multiple of eight. This sounds constraining. It isn't. It's just consistent.

**Typography has hierarchy.** At minimum 1.25 ratio between scale steps, weight and size both signalling levels, body measure capped at 65 characters. These aren't suggestions.

**Motion is physics.** Easing choices answer questions about weight and friction. Timing matters more than curve shape. There is always a pause before the key result. If it looks like it was generated by an AI with no sense of rhythm, it needs more work.

**The AI slop test.** If someone can look at the output and say "AI made that" without any doubt, it failed. There's a two-altitude check in TDA-critique-audit.md. Use it.

---

## The Banned Patterns

These are absolute. No exceptions, no "just this once."

- Side-stripe borders (border-left or border-right over 1px on cards or alerts)
- Gradient text (background-clip: text with a gradient)
- Glassmorphism as a default aesthetic
- The hero-metric template (large number, label, supporting stats, gradient)
- Identical card grids
- Modals as the first solution to anything
- Em dashes in UI copy

The list exists because all of these appear constantly, all of them signal "generated by an AI following a template," and most of them are genuine design failures masquerading as style choices.

---

## Motion Design

TDA-motion.md is the most substantial subskill. It covers:

- The physics-first philosophy (animation is weight and friction, not tween curves)
- Fourteen specific pitfalls with code fixes (floating-point accumulation, stacking context traps, font loading measurement, canvas transform state, the works)
- A full easing library with named curves and their physical meanings
- A seekable animation loop architecture so scrubbing always works
- Timing guidelines and reduced motion handling

The fourteen pitfalls came from actual bugs. They are the list of things that will catch you out at 11pm when the demo is in the morning.

---

## Slide Decks

TDA-slides.md handles presentations specifically because slides are not apps and most design systems treat them like they are. Key things it covers:

**Format decision gate.** HTML, HTML plus PDF, or HTML with PPTX export. These have very different constraints and you need to know which you're building before you start. PPTX export means: 960pt by 540pt canvas, all text in `<p>` or heading tags, no gradients, no background-image. If the client wants full visual complexity and editable PowerPoint, they need to choose. TDA will tell them so.

**Grammar lock-in.** Build two showcase slides first. Polish them to completion. User approves. Then batch-produce the rest using that grammar. The alternative is building thirteen slides in the wrong direction, which everyone has done at least once.

**Keyboard navigation.** Arrow keys, spacebar, number-plus-enter to jump. Every deck. Non-negotiable.

---

## Critique and Audit

The critique uses five dimensions: philosophy (does it match the brief), hierarchy (is information prioritised correctly), execution (are the craft details locked), function (does it actually work), and innovation (is there anything distinctive). Each scores one to five. Total out of twenty-five. Anything below fourteen needs major rework.

The technical audit covers accessibility, performance, responsive design, and basic SEO. It's a checklist, not a vibe check.

There's also the AI slop test, which is two questions. Can you guess the palette from the domain alone? Can you guess the aesthetic from the category plus its anti-references? If either answer is yes, the design is still in training-data-reflex territory.

---

## What This Is Not

It's not a replacement for design judgment. It's a structure for applying design judgment consistently.

It's also not a library you import, a framework you configure, or a tool that generates designs autonomously. It works with Claude. Claude does the work. TDA gives Claude a coherent framework for doing that work well instead of improvising a different aesthetic every session.

If you want autonomous design generation with no human in the loop, this won't suit you. If you want Claude to behave like a competent senior designer who knows what they're doing and why, this is the tool.

---

## Version

1.0. Author: TABARC-Code. (its actually V6.7) but the V1 is about the merge of ths as I rebuilt.

I Built this a fromseveral ideas previous design skill systems, absorbing the best of both and dropping the parts that didn't belong in a Claude skill, and work.

The command architecture and production quality bar came from a separate craft-focused system. The physics-first motion philosophy, OKLCH colour strategy, and banned patterns list were developed independently.

---

## Licence

MIT. Use it, fork it, adapt it. If you improve it, consider sharing the changes back.
