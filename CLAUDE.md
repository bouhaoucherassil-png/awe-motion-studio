# Claude project instructions

Read `AGENTS.md` before editing any film.

This repository creates vertical motion-graphics videos with Vawe. Work only in the requested `films/<name>/page.html` folder unless asked otherwise.

- Default format: 9:16.
- Test duration: 60 seconds.
- Use HTML, CSS, SVG and JavaScript.
- Keep every frame deterministic under Vawe's virtual clock.
- Do not use Google Flow, hosted video generation, paid APIs, external subscriptions or music by default.
- Do not start GitHub Actions runs or final `bin/vawe ship` renders without the user's explicit approval.
- Keep `.github/workflows/render.yml` manual-only. Never add push, pull_request or schedule triggers.
- Use the Vawe skills in `skills/vawe-motion-director/SKILL.md` when available.
