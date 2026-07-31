# Curated GitHub Source Map

Use these repositories as primary references for patterns, APIs, examples, and implementation tradeoffs. Check their current docs, releases, issues, and licenses before adoption. Do not copy complete visual designs or substantial code without license review and attribution requirements.

## Design systems and accessible primitives

- `shadcn-ui/ui` — source-owned, customizable component composition and registry patterns.
- `radix-ui/primitives` — accessible interaction primitives and design-system behavior contracts.
- `tailwindlabs/headlessui` — unstyled accessible components for Tailwind-oriented React and Vue projects.
- `angular/components` — Angular Material and CDK implementations for accessibility, overlays, focus, portals, drag-drop, and component architecture.
- `storybookjs/storybook` — isolated component development, interaction states, documentation, and visual review workflows.
- `w3c/aria-practices` — authoritative examples of ARIA patterns and keyboard interaction expectations.
- `lucide-icons/lucide` — consistent open icon system.
- `simple-icons/simple-icons` — brand icon data; verify brand usage rules separately.
- `amzn/style-dictionary` — design-token transformation across platforms and output formats.

## Web architecture, accessibility, and performance

- `patterns-dev/patterns.dev` — web application architecture and performance pattern explanations.
- `GoogleChrome/lighthouse` — performance, accessibility, best-practice, and SEO auditing implementation.
- `GoogleChrome/web-vitals` — measurement of user-centered web performance metrics.
- `web-platform-tests/wpt` — cross-browser platform behavior tests.
- `dequelabs/axe-core` — automated accessibility testing engine; automated checks do not replace manual review.
- `microsoft/playwright` — browser automation and cross-browser end-to-end testing.

## Motion and interaction

- `greensock/GSAP` — authored timelines, scroll-linked sequences, and high-control animation.
- `motiondivision/motion` — interaction and layout animation patterns for modern web apps.
- `darkroomengineering/lenis` — smooth-scroll implementation; use only when native scroll remains accessible and responsive.
- `formkit/auto-animate` — low-configuration layout-transition patterns.
- `theatre-js/theatre` — visual sequencing and authored animation state for complex scenes.

## 3D, WebGL, and asset pipelines

- `mrdoob/three.js` — foundational JavaScript 3D engine, examples, loaders, WebGL/WebGPU, materials, and scene architecture.
- `pmndrs/react-three-fiber` — React renderer for Three.js; use only in React stacks.
- `pmndrs/drei` — React Three Fiber helpers; understand the underlying Three.js cost and behavior.
- `pmndrs/react-postprocessing` — React-oriented postprocessing composition.
- `pmndrs/gltfjsx` — glTF-to-React component workflow for React Three Fiber projects.
- `pmndrs/leva` — development-time parameter controls for scenes and visual tuning.
- `donmccurdy/glTF-Transform` — inspect, optimize, compress, and transform glTF assets.
- `zeux/meshoptimizer` — geometry and mesh compression/optimization.
- `google/draco` — geometry compression for 3D meshes.
- `KhronosGroup/glTF` — glTF specification and ecosystem guidance.
- `KhronosGroup/KTX-Software` — KTX texture tooling and Basis Universal workflows.

## How to use this map

1. Start with the user's repository and problem.
2. Select only the relevant category.
3. Read the upstream README and current documentation.
4. Check maintenance status, releases, browser support, package size, and open migration issues.
5. Inspect the license before copying or adapting code.
6. Prefer principles and small, attributed implementation ideas over cloning an entire example.
7. Record why each new dependency is necessary.
