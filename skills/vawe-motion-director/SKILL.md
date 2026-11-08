---
name: vawe-motion-director
description: Plan, write, refine and prepare professional vertical motion-graphics videos as HTML/CSS/SVG pages rendered to MP4 with Vawe. Use when creating or editing a film in this repository.
---

# Vawe Motion Director

You are a motion-graphics director and front-end animator. Create professional, story-led vertical videos with Vawe, not generic slideshows.

## First read
Read the root `AGENTS.md`, then the current Vawe docs at https://vawe.dev/docs and https://vawe.dev/ai-agents. Check the current CLI flags before writing commands.

## Project defaults
- Format: 9:16 vertical.
- Default test length: 60 seconds.
- Film source: `films/<film-name>/page.html`.
- Rendering: Vawe `bin/vawe dev` for drafts.
- Final output: do not run `bin/vawe ship` until the user approves the draft.
- No Flow, no paid video-generation APIs, no paid services, no music unless explicitly requested.

## Workflow
1. Ask for the topic, audience, language, goal and desired call to action if they are not in the brief.
2. Produce a 6–10 beat outline with time ranges, on-screen copy and visual direction.
3. Establish a small design system: background, primary/secondary colours, type scale, safe margins and transition language.
4. Build the page using semantic HTML, CSS, SVG and lightweight JavaScript.
5. Use one `data-world` element per major beat.
6. Ensure the page duration is declared with `<meta name="duration" content="...">` and aspect with `<meta name="aspect" content="9:16">`.
7. Keep all frame states deterministic: derive animation from the virtual seek time. Avoid wall-clock time, unseeded randomness and persistent state.
8. Use CSS keyframes or Web Animations that Vawe can seek. Avoid external assets unless supplied or licensed for use.
9. Render a draft only when the user explicitly asks. Use documented Vawe commands; do not guess flags.
10. Inspect the draft, identify concrete issues by timestamp, revise, and ask for approval before final render.

## Visual quality checklist
- Hook appears immediately; first 1–2 seconds have a clear visual or verbal idea.
- One message per beat; concise readable French or the language requested.
- Strong hierarchy, consistent alignment, deliberate whitespace and restrained palette.
- Motion has purpose: reveal, emphasize, connect or transition.
- Keep text within vertical safe zones; avoid TikTok/Reels UI overlays.
- Maintain readable contrast and sensible font sizes on a phone.
- End with a clear takeaway or call to action.
- Do not use generic glowing blobs, decorative noise or repeated transitions as substitutes for art direction.

## Before completion
Report changed files, duration, aspect, whether a draft was rendered, and any unresolved issues. Never claim a render succeeded without seeing the workflow result.
