# DaveHub publishing specification — draft

**Status:** Planning only. No changes to DaveHub have been made.

## Responsibility split

**Ordinary Universe repository:** Canon, scripts, original art, web exports, approved content manifest.  
**DaveHub repository/site:** Website shell, reader UI, navigation, homepage discovery, caching and build/deployment workflow.

This separation allows strips to be authored without repeatedly editing site code.

## Anthology and issue model

**The Ordinary Universe** is the shared world; **The Ordinary Verse** is the reader-facing comic anthology. Organise by a numbered issue with a cover, table of contents, ordered two-page stories and one continuous reading experience. Story production IDs like `OU-001` should remain internal, not appear in story title graphics.

**Issue #1 (initial slate):** pages 1–2 *The Origin of Man of Carbon* (approved coloured spread, binary upload pending); pages 3–4 *The Dark Night Rises* (script); pages 5–6 *The Call to Justin* (script). An issue is only marked published when its approved content and reader are actually available on DaveHub.

## Suggested URLs

- `/ordinary-verse/` — anthology landing page, latest issue and 'Start Reading'.
- `/ordinary-verse/issues/1/` — cover and Issue #1 reader/table of contents.
- `/ordinary-verse/issues/1/the-origin-of-man-of-carbon/` — optional deep link into one story while retaining in-issue navigation.
- `/ordinary-verse/archive/` — numbered issue archive.
- `/ordinary-universe/characters/<slug>/` — optional world/character dossiers.

These are proposed route shapes; they are not live URLs. Preserve issue and story IDs in metadata so routes can be changed without breaking reading order.

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
