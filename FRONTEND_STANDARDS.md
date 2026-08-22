# Frontend Website Standards

## Scope

Apply these rules whenever creating, editing, repairing, or reviewing user-facing frontend interfaces, including landing pages, websites, dashboards, forms, and marketing pages.

Follow the user's explicit instructions over this rule when they conflict.

## First Principles

Before editing code:

1. Inspect the existing repository structure and identify the app framework, package manager, entry point, styling system, and available scripts.
2. Inspect `brand_assets/` if it exists.
3. Inspect existing design tokens, components, fonts, global styles, and layout conventions before creating replacements.
4. If a reference image, screenshot, Figma export, or existing URL is supplied, treat it as the source of truth for the visual result.
5. State a concise implementation plan before making multi-file or structural changes. For small corrections, proceed directly.

Do not assume a React, Next.js, Vite, Tailwind, or static-HTML stack. Preserve the project's existing stack unless the user asks to change it.

## Brand Asset Policy

Before designing any page, check `brand_assets/` and all existing public/static asset directories.

- Use real logos, images, icons, colors, and typography files when available.
- If a brand palette or style guide exists, use its exact values.
- Do not replace a supplied logo with text.
- Do not use placeholder assets when appropriate real assets are present.
- Do not invent a visual identity that conflicts with supplied assets.
- If no usable brand assets exist, use a restrained original visual system appropriate to the project's audience and objective.

For placeholder imagery, prefer stable local placeholders or the user-approved image source. Do not depend on externally hosted placeholder images when local development or offline operation matters.

## Reference Fidelity Policy

When a visual reference is provided:

- Reproduce the visible layout, hierarchy, content density, spacing, typography scale, color relationships, borders, shadows, imagery treatment, and responsive behavior as closely as possible.
- Do not add sections, interactions, features, illustrations, decorative elements, or marketing claims not visible in the reference.
- Do not redesign or "improve" the reference unless the user specifically requests a redesign.
- Use generic placeholder copy only when the reference contains text that must not be reused, or when the user asks for replacement content.
- Preserve the reference's information architecture and ordering.

When no reference is provided:

- Design deliberately for the stated target audience, conversion goal, and brand.
- Establish a clear visual hierarchy before adding decorative treatment.
- Favor clarity, accessibility, and credible information design over trend-driven decoration.

## Visual Quality Standards

### Color

- Do not use default framework colors as the site's primary brand color.
- Define a small intentional palette: background, surface, elevated surface, text, muted text, primary action, and semantic states.
- Use accessible contrast for text, buttons, controls, and form errors.
- Use gradients only when they reinforce hierarchy or atmosphere. Avoid gratuitous gradients.

### Typography

- Use a deliberate type system with a readable body face and an appropriate display treatment where needed.
- Do not use a different font family merely to be decorative.
- Use a consistent scale for eyebrow text, headings, body copy, metadata, labels, and buttons.
- Large headlines may use tighter tracking when appropriate. Body text must remain highly readable with comfortable line height.
- Avoid extremely small body text and low-contrast labels.

### Spacing and Layout

- Use a consistent spacing scale rather than arbitrary values.
- Design mobile-first, then validate tablet and desktop layouts.
- Keep content width, gutters, section padding, card gaps, and vertical rhythm intentional and consistent.
- Avoid excessive rounded cards, excessive whitespace, or repetitive "section + card grid" layouts when they do not serve the content.
- Respect alignment lines. Elements that appear related should align intentionally.

### Depth and Surfaces

- Establish a clear layer system: page background, surface, elevated card, floating overlay, and modal if applicable.
- Avoid generic single-layer shadows.
- When shadows are needed, use subtle, layered, low-opacity shadows that fit the color system.
- Use borders, tonal contrast, blur, and shadow intentionally rather than applying all of them at once.

### Images and Media

- Use correct aspect ratios and `object-fit` behavior.
- Do not stretch, distort, crop unpredictably, or place illegible text over images.
- Apply overlays only when needed to preserve text legibility or match a supplied reference.
- Optimize image loading behavior when the project architecture supports it.
- Provide meaningful `alt` text for informative images; use empty alt text for purely decorative images.

### Motion and Interaction

- Animate only `transform` and `opacity` unless a different property is necessary and performance-safe.
- Never use `transition: all`.
- Use short, intentional transitions with an appropriate easing curve.
- Every interactive control must have visible hover, keyboard focus-visible, disabled where relevant, and active states.
- Respect `prefers-reduced-motion`.
- Do not add animation solely because animation is possible.

## Accessibility and UI Behavior

- Use semantic HTML first: headings in order, landmarks, buttons for actions, links for navigation, labels for form controls.
- Do not make clickable `div` elements when a button or link is appropriate.
- Ensure keyboard navigation works.
- Ensure focus indicators are visible and not removed.
- Use accessible names for icon-only buttons.
- Do not rely on color alone to communicate status or validation.
- Ensure responsive navigation, modals, menus, and dialogs remain usable with keyboard and screen readers.
- Avoid horizontal overflow at mobile widths.

## Engineering Standards

- Make the smallest set of changes needed to satisfy the request.
- Reuse existing utilities, tokens, and components before introducing duplicates.
- Do not install dependencies without explaining why they are necessary.
- Do not replace the project's framework, build system, CSS strategy, or component library without explicit user approval.
- Do not leave broken imports, dead code, placeholder event handlers, console errors, or unfinished TODOs.
- Keep components appropriately scoped; do not over-engineer simple static content.
- Keep user-visible copy factual and avoid invented testimonials, metrics, certifications, client names, legal claims, or medical claims.
- For healthcare or wellness websites, avoid unsupported efficacy claims, diagnoses, treatment guarantees, or HIPAA-compliance claims unless supplied and verified by the user.

## Verification Requirements

After implementation:

1. Run the project's relevant formatting, type-check, lint, test, and build commands when available.
2. Start or use the existing local development server. Do not use `file:///` for visual review.
3. Use the Antigravity browser capability to inspect the site running on localhost.
4. Verify at minimum:
   - Mobile width: approximately 375px
   - Tablet width: approximately 768px
   - Desktop width: approximately 1440px
5. Check for:
   - Broken layout or horizontal scrolling
   - Visual hierarchy and alignment
   - Typography scale and line wrapping
   - Spacing and container widths
   - Colors, borders, radius, and shadows
   - Image crop and loading behavior
   - Hover, focus-visible, active, and disabled states where applicable
   - Browser-console errors
6. When a reference is provided, conduct at least two visual comparison-and-correction rounds unless the user tells you to stop.
7. In the final response, report:
   - What changed
   - Which files changed
   - What verification was run
   - Any known limitations or decisions that require user input

## Stop Conditions

Do not claim the work is complete until the local implementation has been inspected in a browser and the relevant project verification has been run.

If browser access, server startup, required assets, or build commands are unavailable, say exactly what could not be verified and why.
