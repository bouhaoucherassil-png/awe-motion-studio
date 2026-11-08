# Vawe Motion Studio

Private, iPhone-managed project for creating vertical motion-graphics videos with HTML/CSS and rendering them to MP4 using Vawe on GitHub Actions.

## Project settings

- Output: vertical 9:16
- Test film: 60 seconds
- Authoring: HTML, CSS, SVG and JavaScript
- Renderer: [Vawe](https://github.com/vawe-hq/vawe)
- Render mode: draft only by default
- Trigger: manual GitHub Actions run only

## Render the test film

1. Open the **Actions** tab.
2. Select **Render Vawe video**.
3. Tap **Run workflow**.
4. Keep the film name as `test`.
5. Wait for the workflow to finish.
6. Open the run and download the `vawe-draft-test` artifact.

The workflow renders a draft only. It does not run automatically on commits and does not create a final 60 fps export.

## Edit the film

Edit `films/test/page.html`. The film duration is set by:

```html
<meta name="duration" content="60">
```

Keep all animation deterministic: derive visual states from the page timeline; do not depend on wall-clock time, random values, or timers.

## Cost and safety

- No paid API or external AI service is called by the render workflow.
- The workflow uses the standard `ubuntu-latest` GitHub-hosted runner.
- It runs only when manually started.
- The job has a 30-minute timeout and limited concurrency.
- Draft rendering only; do not add `ship` or automatic triggers without reviewing usage and cost first.
- GitHub Actions usage still counts against the account's included quota. If no payment method is attached, exhausted quota can stop jobs rather than silently guaranteeing unlimited free execution.
