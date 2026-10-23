# Artwork asset specification

Use source control as the master for production files and reviewed exports, but be conscious of GitHub's large-file limits. Use Git LFS for large layered originals if needed, and do not invent empty final-art placeholders.

## Naming

- Character references: `artwork/characters/<character-slug>/model-sheet-v01.png`
- Spread storyboards: `artwork/comics/OU-001/spread-storyboard-v01.png`
- Lossless composed spread master: `artwork/comics/OU-001/spread-master-v01.png`
- Approved lettered spread export: `artwork/comics/OU-001/web/spread.webp`
- Clean / lettered panel images: `artwork/comics/OU-001/panel-01-v01.png`
- Approved web exports: `artwork/comics/OU-001/web/panel-01.webp`
- Thumbnails: `artwork/comics/OU-001/web/cover.webp`

These are **future paths**, not currently populated assets.

## Delivery requirements

- Build each regular comic as one composed **two-page, 8–12-panel spread** (10 default), separable art and lettering where practical.
- Respect the central gutter, safe speech bubble areas and panel reading order. Do not put essential words on a seam.
- Provide independent, numbered panel images for a responsive vertical mobile reader. Never rely on scaling down the whole double spread for dialogue readability.
- Preserve safe margins so captions and balloons cannot be cut off.
- Use reasonable compression and correct dimensions for efficient loading.
- Provide descriptive alt text and full accessible transcripts in metadata.
- Document source and use permissions; no unverified fonts or borrowed copyrighted costume art.
- Every recurring face, body shape, hairstyle and outfit requires consistency checks.

## Acceptance checklist

- [ ] Style locked
- [ ] Character references approved
- [ ] Two-page composition and central-gutter safety verified
- [ ] 8–12 numbered panels and reading order approved
- [ ] Storyboard approved
- [ ] Artwork checked for continuity and cropping
- [ ] Lettering mobile-legible
- [ ] Web exports responsive and optimised
- [ ] Transcript and alt text present
- [ ] Credits and asset rights recorded
- [ ] Final creative approval recorded

Do not publish assets until all checks pass.
