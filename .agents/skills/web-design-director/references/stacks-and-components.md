# Stack and Component Routing

## General rule

Use the repository's existing framework, package manager, styling strategy, and component conventions. Add a library only when it removes substantial risk or repeated work. Avoid running two overlapping design systems.

## Angular

Preferred for Arshia's greenfield full-stack work unless another stack is requested.

- Use standalone components, signals, OnPush, typed reactive forms, lazy routes, and modern template control flow supported by the installed Angular version.
- Use Angular CDK concepts for focus management, overlays, portals, drag and drop, bidirectionality, and accessibility.
- Use Angular Material when its product language fits; do not force the Material visual style onto a custom brand.
- Build brand-specific primitives with semantic HTML, CDK behavior, CSS variables, and component-level styles.
- Keep components focused and extract repeated visual or interaction contracts.
- Use `NgOptimizedImage` where compatible with the project.
- Avoid manual subscriptions when signals or lifecycle-safe operators are clearer.
- Keep animation state separate from business state.

## React and Next.js

- Preserve Server Component boundaries in Next.js.
- Use accessible primitives such as Radix or Headless UI when the repository already aligns with them.
- Treat shadcn/ui as source-owned components to customize, not a fixed visual theme.
- Keep state local until multiple distant consumers genuinely require shared state.
- For 3D, consider React Three Fiber, Drei, and React Postprocessing when the project is already React.
- Avoid turning every component into a client component merely for animation.

## Vanilla, Astro, and content sites

- Prefer semantic HTML, modern CSS, and minimal JavaScript.
- Use islands only for interactive regions.
- Keep content available without client-side rendering when SEO and reading are central.
- Use CSS scroll-driven animations only with robust support checks and fallbacks.
- Avoid installing a full component framework for a small marketing site.

## Styling strategy

- Centralize semantic tokens with CSS custom properties.
- Use cascade layers when the project benefits from clear reset, token, component, utility, and override ordering.
- Use scoped component styles without breaking theming.
- Tailwind is appropriate when already present or when utility composition improves delivery speed; avoid unreadable one-line class walls and arbitrary values everywhere.
- SCSS is appropriate for organization and authoring, but runtime theming should rely on CSS variables.
- Do not use inline styles for a complete design system.

## Component selection

Choose behavior-first primitives for:

- Dialogs and sheets
- Popovers and dropdown menus
- Tooltips
- Tabs
- Accordions
- Comboboxes and selects
- Toasts and live announcements
- Focus traps and roving tabindex
- Drag and drop
- Virtualized lists

Build custom presentation around tested interaction contracts. Do not recreate a complex combobox, dialog, or menu from scratch without a compelling reason and complete keyboard testing.

## Data visualization

- Select a chart only when it answers a real question.
- Label axes, units, time windows, and comparison baselines.
- Do not encode meaning by color alone.
- Provide accessible summaries or tables for important data.
- Avoid 3D charts; perspective distorts values.
- For dashboards, place status, change, cause, and next action together.

## Quality checks

Use the repository's scripts. Common checks include:

- Format
- Lint
- Type check
- Unit and interaction tests
- Production build
- End-to-end flows
- Accessibility scan
- Lighthouse or equivalent performance audit
- Bundle and asset inspection

Report what was actually run. Do not claim visual or device verification that did not happen.
