---
name: web-design-director
description: Design, redesign, audit, and implement polished web interfaces and immersive 3D/WebGL experiences. Use for websites, landing pages, portfolios, dashboards, ecommerce, booking flows, design systems, responsive layouts, UI/UX reviews, accessibility, motion, Three.js, WebGL, GSAP, Angular, React, or vanilla frontends. Do not use for backend-only work, native-only app screens, or tiny styling edits with no design decision.
---

# Web Design Director

Create distinctive, usable, production-ready web experiences. Treat visual design, interaction, accessibility, responsive behavior, performance, and implementation quality as one system.

## Operating workflow

1. Inspect the repository before proposing a stack change.
   - Read package manifests, routing, global styles, design tokens, shared components, image assets, and existing UI conventions.
   - Preserve the existing framework unless a rewrite is explicitly requested and justified.
   - Identify the target users, primary task, primary CTA, content hierarchy, supported languages, and device constraints from available context.

2. Define the experience before writing components.
   - State the page goal in one sentence.
   - Choose one coherent visual direction, not a collage of trends.
   - Establish type scale, spacing scale, color roles, radii, elevation, container widths, breakpoints, and motion rules as tokens.
   - Sketch the information architecture and responsive section order.

3. Build from primitives to pages.
   - Start with semantic structure and accessible interaction contracts.
   - Create reusable primitives only when repetition is real.
   - Compose sections and pages from those primitives.
   - Include loading, empty, error, disabled, success, validation, hover, focus, active, and reduced-motion states.

4. Add motion and 3D only when they improve comprehension, storytelling, navigation, or brand character.
   - Keep the main task usable without animation or WebGL.
   - Load heavy experiences progressively and provide a static fallback.
   - Never trade readable content, input latency, keyboard access, or mobile stability for spectacle.

5. Verify the result in code.
   - Run the existing formatter, linter, type checker, tests, and production build.
   - Inspect mobile, tablet, desktop, keyboard-only, reduced-motion, dark mode, slow-network, empty-data, and error states.
   - Fix horizontal overflow, layout shift, focus loss, poor contrast, inaccessible names, and oversized assets before considering the work complete.

## Decision rules

- Prefer content hierarchy over decoration.
- Use one dominant visual idea per page.
- Use cards only for genuinely discrete objects; avoid card soup.
- Use gradients, glass, glow, blur, noise, and 3D as accents, not as substitutes for layout.
- Avoid generic AI-looking hero sections, random floating shapes, excessive pill buttons, and meaningless dashboard charts.
- Keep one obvious primary action per view. Secondary actions must be visually quieter.
- Use real content or realistic content shapes. Do not hide weak hierarchy behind lorem ipsum.
- Reuse the project's icon system. Do not mix icon families or use emoji as production UI icons unless the product language calls for it.
- Use CSS logical properties for multilingual and RTL-safe layouts.
- Respect browser-native behavior unless a custom interaction clearly improves it.

## Framework routing

Read [references/stacks-and-components.md](references/stacks-and-components.md) when selecting implementation patterns or component libraries.

For Arshia's greenfield full-stack projects, prefer Angular with standalone components, signals, OnPush change detection, typed forms, CSS variables, and accessible CDK-style primitives. Keep Spring Boot and PostgreSQL concerns separate from the visual layer. Use React-specific tools only in React repositories.

## UX and visual foundation

Read [references/foundations.md](references/foundations.md) for layout, typography, responsive behavior, forms, navigation, multilingual design, accessibility, mobile Safari, motion, and anti-patterns.

## 3D and immersive experiences

Read [references/three-d-webgl.md](references/three-d-webgl.md) whenever a request mentions 3D, Three.js, WebGL, WebGPU, shaders, GLB/glTF, scroll-driven scenes, product configurators, particles, spatial hero sections, or Awwwards-style interaction.

## GitHub source map

Read [references/github-sources.md](references/github-sources.md) when researching implementation approaches or choosing a library. Treat listed repositories as primary-source references. Inspect current documentation, maintenance status, package versions, and licenses before adopting code. Never copy a complete design or substantial implementation merely because it is public.

## Required output for design work

When the task is primarily design or redesign, communicate:

1. Experience goal and target user.
2. Chosen visual direction and why it fits.
3. Information architecture and responsive behavior.
4. Token and component decisions.
5. Accessibility, performance, and fallback decisions.
6. Implemented files and verification results.

When the user asks for implementation, make the changes instead of returning only a plan.

## Completion checklist

- The primary task is clear within the first viewport.
- Heading order and landmarks are semantic.
- Keyboard focus is visible and follows a logical order.
- Controls have accessible names and adequate target sizes.
- Text and controls meet contrast requirements.
- Layout works at 320px width without horizontal scrolling.
- Dynamic viewport units and safe-area insets are handled where needed.
- Images and models have dimensions, responsive sources, lazy loading, and meaningful alternatives.
- Animation respects `prefers-reduced-motion`.
- WebGL has a fallback and does not block core content.
- No unnecessary dependencies or duplicate component systems were introduced.
- Production build and repository checks pass, or failures are reported precisely.
