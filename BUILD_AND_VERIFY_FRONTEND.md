# Build and Verify Frontend

Create, update, or reproduce a frontend interface with high visual fidelity and verify it in a local browser.

## Step 1 — Understand the task

Read the user request carefully and identify:

- The page or component to build
- Whether a visual reference was provided
- The intended audience and conversion goal
- Required text, sections, assets, interactions, and responsive behavior
- Constraints about framework, files, dependencies, or design direction

If the task is ambiguous in a way that changes the visible result, ask one concise clarifying question before implementation.

## Step 2 — Inspect the workspace

Before writing code:

1. Identify the framework, package manager, project scripts, entry points, and styling approach.
2. Read the workspace frontend rules.
3. Inspect `brand_assets/`, `public/`, `static/`, `src/assets/`, and existing design-system files if present.
4. Locate existing fonts, logos, color tokens, shared layout components, and relevant page routes.
5. If a reference image was supplied, inspect it closely and write down:
   - Page sections and order
   - Desktop and mobile structure
   - Container widths and gutters
   - Typography hierarchy
   - Approximate font sizes, weights, line heights, and tracking
   - Color values or closest observable values
   - Border radius, shadows, and image treatment
   - Interactions or states visible in the reference

## Step 3 — Plan before changes

For non-trivial work, provide a brief plan containing:

- Files to create or edit
- The design and layout approach
- Reusable components or tokens to use
- Any dependency or asset decisions
- The local verification commands to run

Do not make framework migrations or add dependencies without explicit user approval.

## Step 4 — Implement

Build the smallest coherent implementation that satisfies the request.

When a reference image is supplied:

- Match the reference rather than redesigning it.
- Do not add content, sections, or features not present in the reference.
- Use provided brand assets whenever available.
- Use placeholders only where real assets are unavailable or not permitted.

When no reference image is supplied:

- Create a deliberate visual system appropriate to the user's stated goal.
- Use semantic, accessible, responsive markup.
- Follow the workspace frontend standards.

## Step 5 — Run code verification

Use the project's existing scripts where available.

1. Install or restore dependencies only if needed and allowed.
2. Run the most relevant checks available:
   - Formatter
   - Linter
   - Type checker
   - Unit or integration tests
   - Production build
3. Fix errors caused by the changes.
4. Do not ignore build failures, browser-console errors, or broken imports.

## Step 6 — Start local preview

1. Identify the correct project command for starting the development server.
2. Use the existing server if it is already running.
3. Otherwise start the appropriate dev server.
4. Determine the actual local URL and port from the command output.
5. Open the implementation through localhost using the Antigravity browser capability.
6. Never use a `file:///` URL for visual verification.

## Step 7 — Browser inspection

Inspect the running page at these approximate viewport widths:

- Mobile: 375px wide
- Tablet: 768px wide
- Desktop: 1440px wide

Check:

- No horizontal overflow or clipped content
- Correct section order and responsive stacking
- Container widths, gutters, alignment, and spacing
- Typography sizing, wrapping, weight, and hierarchy
- Correct images, crops, aspect ratios, and loading behavior
- Correct colors, borders, radius, and surface depth
- Navigation, buttons, forms, menus, and dialogs where relevant
- Hover, focus-visible, active, and disabled states
- Browser console for errors or warnings caused by the change

Capture browser screenshots or artifacts for visual comparison when available.

## Step 8 — Visual comparison loop

If a reference image exists:

1. Compare the local implementation against the reference.
2. Record concrete mismatches, including approximate measurable differences.
   - Example: "Hero heading renders about 8px too large."
   - Example: "Desktop content container is roughly 80px too wide."
   - Example: "Cards use 12px gaps; reference appears closer to 24px."
   - Example: "Reference uses a warmer off-white background rather than pure white."
3. Make targeted corrections.
4. Re-inspect in the browser.
5. Complete at least two comparison-and-correction rounds.
6. Stop only when remaining differences are minor, caused by unavailable fonts/assets, or the user asks you to stop.

If there is no reference image, perform one complete visual-quality pass and correct any visible issues before completion.

## Step 9 — Final report

Respond with:

- A concise statement of completion
- Files changed
- Main implementation decisions
- Commands and browser checks completed
- Responsive widths inspected
- Any limitations, missing assets, or unresolved visual differences
