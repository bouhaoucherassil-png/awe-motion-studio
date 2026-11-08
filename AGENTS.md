# Instructions for AI coding agents

## Goal
Create polished, professional motion-graphics films for vertical social video. The project uses Vawe: one HTML page becomes one MP4.

## Non-negotiable project constraints
- Work inside `films/<film-name>/page.html`.
- Default aspect ratio: 9:16.
- Test film duration: 60 seconds unless the user explicitly changes it.
- Use HTML, CSS, SVG, Canvas or JavaScript; prefer lightweight vector and typography animation.
- Do not use Google Flow, external video-generation APIs, paid APIs, or services requiring a subscription.
- Do not add secrets, API keys, personal information, or payment information to the repository.
- Do not trigger a final `vawe ship` render unless the user explicitly approves it.
- The GitHub Actions workflow is manual-only and should remain so.

## Vawe page contract
- Read the current Vawe documentation and the installed repository's `AGENTS.md` before changing rendering logic.
- A film is a page at `films/<name>/page.html`.
- Set the duration with `<meta name="duration" content="60">`.
- Use `data-world` elements to identify the film's beats.
- The renderer seeks the page through time. The same time must always produce the same frame.
- Do not use wall-clock time, unseeded randomness, timers, or state that depends on the order frames were rendered.
- CSS keyframes and Web Animations are suitable when they obey Vawe's virtual clock.
- Check the current Vawe CLI documentation before inventing flags.

## Design quality
- Use a clear visual hierarchy, deliberate typography, controlled spacing, and coherent color system.
- Animate with purpose: entrances, exits, transitions, emphasis, and camera-like movement.
- Avoid slideshow-like sequences, excessive glow, random decorations, and unreadable small text.
- Keep important text inside safe margins for TikTok/Reels UI overlays.
- Build a strong opening hook, clear middle progression, and memorable ending.
- Prefer original graphics and user-provided assets. Do not copy copyrighted footage or music.
- Do not add music by default.

## Workflow
1. Clarify the subject, audience, language and key message.
2. Write a concise scene/beat plan for the requested duration.
3. Build the page in HTML/CSS/SVG.
4. Render a draft using `bin/vawe dev`.
5. Inspect the rendered MP4 and key-frame sheet.
6. Fix the largest visual or timing problems.
7. Ask the user before any final-quality `ship` render.

## Resource limits
- Use GitHub Actions standard `ubuntu-latest` only.
- Do not add larger runners, paid third-party actions, paid APIs, scheduled triggers, or push triggers.
- Keep workflow timeout and concurrency limits.
- Prefer draft renders while iterating.
