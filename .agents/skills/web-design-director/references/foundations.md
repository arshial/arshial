# Web Design Foundations

## Contents

- Product and content hierarchy
- Layout and responsive systems
- Typography and color
- Navigation and interaction
- Forms and data-heavy interfaces
- Motion
- Accessibility
- Multilingual and RTL
- Mobile Safari
- Common anti-patterns

## Product and content hierarchy

Start from the user's job, not from visual effects. Identify the one action or understanding that makes the page successful. Put the strongest evidence, explanation, or interaction near that action.

Use this section sequence as a starting point, not a fixed template:

1. Clear promise or task entry.
2. Proof, context, or immediate utility.
3. Key capabilities or content.
4. Objection handling, details, or comparison.
5. Final action and trustworthy footer.

For applications, prioritize task state, current context, next action, and feedback over marketing-style decoration.

## Layout and responsive systems

- Use a small, documented spacing scale rather than arbitrary margins.
- Use fluid containers with readable maximum widths.
- Let typography and content determine breakpoints; do not design only around named devices.
- Prefer CSS Grid for two-dimensional page composition and Flexbox for one-dimensional alignment.
- Use container queries when a component's behavior depends on its own width.
- Reorder content only when the reading order remains correct in the DOM.
- Use progressive disclosure for secondary controls on small screens.
- Keep touch targets comfortably usable and separated.
- Test 320px, 375px, 768px, 1024px, and a wide desktop as checkpoints, then drag continuously between them.

## Typography and color

- Use one display family and one text family at most unless the brand requires more.
- Prefer variable fonts when they reduce files and improve optical control.
- Keep body copy at a comfortable line length, usually around 45–75 characters.
- Use a clear modular type scale and stable line heights.
- Do not rely on font weight alone to communicate state.
- Define colors by role: canvas, surface, text, muted text, border, primary action, accent, success, warning, danger, focus.
- Support dark mode through semantic tokens rather than inverting arbitrary values.
- Check contrast in every interaction state, including disabled and placeholder text.

## Navigation and interaction

- Keep global navigation predictable. Novelty belongs in transitions and storytelling, not in making users guess where links are.
- Preserve browser history and deep links for meaningful application states.
- Use buttons for actions and links for navigation.
- Menus, dialogs, popovers, tabs, comboboxes, and tooltips must follow established keyboard behavior.
- Never hide essential information behind hover alone.
- Keep focus inside modal dialogs, restore focus on close, and make escape behavior explicit.
- Use optimistic UI only when failure is reversible and clearly handled.

## Forms and data-heavy interfaces

- Keep labels persistent; placeholders are examples, not labels.
- Validate at useful moments. Do not punish users with errors before they have interacted.
- Put error messages near the field and provide an error summary for long forms.
- Preserve entered data after recoverable failures.
- Use the correct input type, autocomplete token, input mode, and accessible description.
- For tables, keep column meaning clear, allow horizontal scrolling when truly tabular, and provide mobile alternatives only when they preserve comparison.
- Show skeletons only when the approximate geometry is known. Otherwise use a compact progress state.
- Empty states should explain what happened and provide the next valid action.

## Motion

Use motion to explain causality, spatial relationship, hierarchy, and state change.

- Prefer transform and opacity for frequent animation.
- Keep micro-interactions fast and restrained.
- Use longer motion only for deliberate scene transitions or storytelling.
- Avoid animating every element on initial load.
- Do not make scrolling feel detached from user input.
- Provide reduced-motion behavior that removes parallax, large travel, looping motion, and scroll hijacking while preserving state feedback.
- Prevent layout shift by reserving space before animated media loads.

## Accessibility

- Start with semantic HTML.
- Use ARIA to complete a semantic interaction, not to replace correct elements.
- Ensure every function works with keyboard alone.
- Keep a visible `:focus-visible` style.
- Announce async status changes when sighted users receive equivalent feedback.
- Associate errors, hints, and units with their controls.
- Provide text alternatives for meaningful images; use empty alt text for decorative images.
- Captions and transcripts are required when media carries information.
- Avoid time limits, flashing content, and auto-playing audio.
- Zoom to 200% and confirm content remains usable.

## Multilingual and RTL

- Use `lang` and `dir` correctly at document or section level.
- Use logical properties such as `margin-inline`, `padding-block`, `inset-inline-start`, and `border-start-start-radius`.
- Mirror directional navigation and spatial icons when meaning depends on direction; do not mirror universal brand marks.
- Allow at least 30–40% text expansion for translated UI.
- Do not hard-code line breaks in headings that will be translated.
- Test Italian, English, and Persian content where those languages are expected.
- Use locale-aware dates, numbers, currency, pluralization, and collation.

## Mobile Safari

- Prefer `100dvh` or carefully chosen modern viewport units over unqualified `100vh` for full-height screens.
- Account for `env(safe-area-inset-*)` in fixed bottom bars and full-bleed layouts.
- Prevent accidental horizontal overflow from transforms, negative margins, long strings, and viewport-width sections.
- Avoid fixed backgrounds and excessive blur on performance-sensitive pages.
- Ensure inputs use a readable font size to avoid unwanted zoom.
- Test fixed elements while the keyboard is open.
- Use native scrolling and momentum unless a custom scroller is essential and fully tested.
- Test date, time, file, and camera inputs on actual iOS behavior.

## Common anti-patterns

- Every section inside a rounded card.
- Decorative statistics with no decision value.
- Five competing accent colors.
- Huge empty hero sections that push useful content below the fold.
- Low-contrast gray text used to appear refined.
- Icons without labels where meaning is ambiguous.
- Carousels for content users need to compare.
- Scroll-triggered text that disappears or becomes unreadable.
- Custom cursors that reduce precision or hide native affordances.
- Smooth scrolling applied globally without reduced-motion support.
- Glassmorphism over busy photography.
- 3D canvases receiving pointer events when the user is trying to scroll or select text.
- Replacing native controls with inaccessible imitations.
