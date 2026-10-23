# DaveHub publishing specification — draft

**Status:** Planning only. No changes to DaveHub have been made.

## Responsibility split

**Ordinary Universe repository:** Canon, scripts, original art, web exports, approved content manifest.  
**DaveHub repository/site:** Website shell, reader UI, navigation, homepage discovery, caching and build/deployment workflow.

This separation allows strips to be authored without repeatedly editing site code.

## Suggested URLs

- `/ordinary-universe/` — introduction, latest strip, start-from-001 button.
- `/ordinary-universe/comics/` — archive, reading order.
- `/ordinary-universe/comics/001-the-origin-of-man-of-carbon/` — immutable comic permalink.
- `/ordinary-universe/characters/<slug>/` — optional later dossiers.

These are proposed URLs, **not live pages**.

## Content contract

At publication, each entry should include: stable `id`; `slug`; `title`; `status: published`; `sequence`; `published_at` (ISO date); `summary`; `characters`; **`layout: { type: "double-spread", spread_src: "..." }`**; ordered `panels` (8–12 normally) with `src`, `alt`, `transcript` and optional `page: left|right`; `cover`; creator/asset credits; optional continuity links. A special director's cut may deliberately exceed the normal count and must be labelled as a variant.

See [comic-manifest.schema.json](comic-manifest.schema.json) for a minimal schema. Draft scripts should **not** be mistaken for published content.

## Reader requirements

- Desktop/tablet landscape: preserve the **original two-page composed spread** with a zoom/full-screen option. Respect the gutter and readable lettering.
- Mobile/portrait: switch to **numbered panels in narrative order** (scroll or guided reader), not a microscopic full-spread image. Avoid cropping bubbles or breaking sequences.
- Next/previous comic controls, clear numbering and optional spoiler-safe related characters.
- Accessible HTML transcription independent of image text, in numbered panel order; screen-reader content must not depend on the composited spread image.
- Proper image dimensions, lazy loading except the first visible panel, responsive sources if available.
- Stable SEO metadata and social thumbnail per issue.
- Gracefully handle missing files and not-yet-approved comics.
- Keep the DaveHub visual identity distinct from the comics' own title treatments.

## Integration options to decide

1. DaveHub consumes a versioned public manifest and approved image URLs from this repo, pinned to releases (recommended initial model).
2. A CI process mirrors approved content into DaveHub during deployment.

Do **not** fetch arbitrary work-in-progress main-branch images and treat them as published. Publishing must be an explicit approval/release step.

## Implementation boundary

No web reader, pipeline, scheduled publishing, automated sync or deployed comic content has been implemented by this commit.
