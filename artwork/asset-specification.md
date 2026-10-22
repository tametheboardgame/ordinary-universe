# Artwork asset specification

Use source control as the master for production files and reviewed exports, but be conscious of GitHub's large-file limits. Use Git LFS for large layered originals if needed, and do not invent empty final-art placeholders.

## Naming

- Character references: `artwork/characters/<character-slug>/model-sheet-v01.png`
- Storyboards: `artwork/comics/OU-001/storyboard-v01.png`
- Clean / lettered panel images: `artwork/comics/OU-001/panel-01-v01.png`
- Approved web exports: `artwork/comics/OU-001/web/panel-01.webp`
- Thumbnails: `artwork/comics/OU-001/web/cover.webp`

These are **future paths**, not currently populated assets.

## Delivery requirements

- Keep a lossless master for each comic, separable art and lettering where practical.
- Provide independent panel images for a responsive vertical mobile reader.
- Preserve safe margins so captions and balloons cannot be cut off.
- Use reasonable compression and correct dimensions for efficient loading.
- Provide descriptive alt text and full accessible transcripts in metadata.
- Document source and use permissions; no unverified fonts or borrowed copyrighted costume art.
- Every recurring face, body shape, hairstyle and outfit requires consistency checks.

## Acceptance checklist

- [ ] Style locked
- [ ] Character references approved
- [ ] Storyboard approved
- [ ] Artwork checked for continuity and cropping
- [ ] Lettering mobile-legible
- [ ] Web exports responsive and optimised
- [ ] Transcript and alt text present
- [ ] Credits and asset rights recorded
- [ ] Final creative approval recorded

Do not publish assets until all checks pass.
