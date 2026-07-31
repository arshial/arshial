# 3D and WebGL Experiences

## Contents

- Decide whether 3D is justified
- Architecture
- Asset pipeline
- Rendering and performance
- Interaction and scroll
- Accessibility and fallback
- Angular implementation
- React implementation
- Verification

## Decide whether 3D is justified

Use 3D when it demonstrates shape, material, space, configuration, sequence, or brand narrative better than 2D media. Prefer video, image sequences, CSS transforms, or static imagery when they achieve the same goal with less complexity.

Before implementation, define:

- What the scene communicates.
- What the user can do.
- What changes on mobile and low-power devices.
- What appears before the scene loads.
- What remains functional when WebGL fails.

## Architecture

- Keep the DOM responsible for primary content, navigation, forms, SEO, and accessibility.
- Treat the canvas as progressive enhancement unless the product itself is a 3D tool.
- Separate scene state, rendering state, and application state.
- Use a single render loop and a single resize strategy per canvas.
- Load scene modules dynamically when they are below the fold or optional.
- Keep debug controls out of production bundles.
- Dispose geometries, materials, textures, render targets, controls, listeners, observers, and animation frames during teardown.

## Asset pipeline

- Prefer glTF/GLB for web delivery.
- Remove hidden geometry, unused materials, unused animation tracks, and oversized texture channels before export.
- Merge or instance repeated meshes when it reduces draw calls without harming culling.
- Use physically plausible scale and origins.
- Compress geometry with Meshopt or Draco when measurements show a net benefit.
- Use KTX2/Basis textures where platform support and pipeline complexity are justified.
- Resize textures to the actual screen-space need; avoid unbounded 4K/8K assets.
- Generate LODs for large hero objects or product scenes.
- Bake lighting or ambient occlusion when dynamic lighting adds little value.
- Keep a poster image or lightweight video fallback derived from the same art direction.

Default delivery targets, adjustable by project:

- Do not put the full 3D payload on the critical path.
- Aim for a compressed initial model payload around 1–2 MB on mobile when feasible.
- Split optional environments, animations, and high-resolution textures.
- Show meaningful HTML immediately while assets stream.

## Rendering and performance

- Cap device pixel ratio; a practical starting point is 1–1.5 on mobile and at most 2 on desktop.
- Pause or reduce rendering when the tab is hidden, the canvas is offscreen, or the scene is static.
- Prefer on-demand rendering for product viewers and mostly static scenes.
- Minimize transparent layers, full-screen postprocessing, dynamic shadows, and high sample counts.
- Profile draw calls, triangles, shader cost, texture memory, overdraw, and main-thread work.
- Use instancing for repeated objects and spatial culling for large scenes.
- Avoid allocating vectors, arrays, or materials inside each frame.
- Use adaptive quality levels instead of one maximum-quality scene.
- Respect thermal limits on phones; a scene that starts at 60 fps but overheats is not successful.

## Interaction and scroll

- Keep camera movement restrained and oriented around a clear subject.
- Use raycasting only on interactive objects and provide equivalent DOM controls where the action matters.
- Do not trap scrolling or require precision gestures for basic navigation.
- If scroll drives a scene, map sections to explicit narrative states and keep readable DOM content synchronized.
- Clamp animation values and handle rapid scroll, reverse scroll, resize, orientation changes, and restored history positions.
- Make pointer capture and touch-action rules explicit.
- Provide visible affordances for rotation, zoom, hotspots, reset, and fullscreen.
- Include a reset view for product viewers.

## Accessibility and fallback

- Describe the scene's purpose in nearby HTML.
- Provide structured text, images, specifications, or controls for information otherwise conveyed only in 3D.
- Support keyboard-operated hotspots and controls.
- Stop continuous motion under `prefers-reduced-motion` and offer a static camera or poster.
- Avoid flashing shaders, rapid parallax, and forced camera motion.
- If WebGL or required features are unavailable, replace the canvas with a useful poster, video, or 2D control.
- Ensure the canvas does not steal focus or pointer events unnecessarily.

## Angular implementation

Use Angular-native architecture in Angular repositories:

- Keep the component standalone and OnPush.
- Dynamically import Three.js and heavy loaders in browser-only code.
- Run the render loop outside Angular change detection; re-enter only for meaningful UI state updates.
- Use signals for serializable UI state, not for per-frame object mutations.
- Create the renderer after the view exists and size it with `ResizeObserver`.
- Guard SSR access to `window`, `document`, WebGL, and canvas APIs.
- Cancel the animation frame and disconnect observers on destroy.
- Traverse loaded scenes and dispose owned GPU resources.
- Keep overlays and accessible controls in normal Angular templates above the canvas.
- Prefer GSAP timelines for authored DOM/camera sequences when they improve clarity; keep state ownership explicit.

Do not introduce React Three Fiber into an Angular project merely because examples are abundant. Translate Three.js concepts into Angular services and components.

## React implementation

In React repositories, React Three Fiber is a strong default when its declarative scene graph fits the codebase.

- Use Suspense and explicit HTML fallbacks.
- Use `frameloop="demand"` for static or event-driven scenes.
- Cache and preload shared assets carefully.
- Use Drei helpers selectively; understand the underlying Three.js behavior.
- Avoid global React state updates on every frame.
- Dispose custom resources and cancel external timelines.
- Use postprocessing only after measuring its cost.

## Verification

- Test on a real iPhone and a mid-range Android device, not only desktop emulation.
- Test WebGL failure and reduced motion.
- Test tab switching, route changes, back navigation, resize, orientation changes, and background/foreground transitions.
- Watch memory across repeated navigation to and from the scene.
- Confirm no render loop survives component teardown.
- Confirm content is usable before, during, and after asset loading.
- Check that the scene does not cause horizontal overflow, delayed taps, scroll jank, or inaccessible focus order.
