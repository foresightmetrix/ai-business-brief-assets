# ai-business-brief-assets

Public image host for the communications in
[`foresightmetrix/mba-communications`](https://github.com/foresightmetrix/mba-communications).

Served over GitHub Pages at `https://foresightmetrix.github.io/ai-business-brief-assets/`.
Email HTML hot-links these files, so pasting a draft into Gmail brings the images
through automatically. Gmail fetches them via Google's image proxy, so a recipient's
network never contacts GitHub.

**Images only.** Never put drafts, notes, requirements, or anything else here — this
repository is public.

## Immutable paths

These URLs appear in email that has **already been delivered to inboxes**:

```
banner-dark-compact.jpg
sig-09c720b4cfe39108.png
2026-09/cowen-sana-ai-summit-still.jpg
```

Renaming, moving, re-pointing, or deleting any of them breaks images in mail people
have already received. There is no recovery — the message is in their inbox and it is
not going to be re-fetched from a corrected path.

**Do not touch them.** They stay exactly where they are, permanently, even though new
files follow a different convention. Add; never modify.

## Naming, for everything new

| What | Path |
|---|---|
| Banners | `banners/<registry-key>-<variant>-v<N>.jpg` |
| Per-send images (stills, headshots) | `stills/<YYYY-MM>/<slug>.jpg` |

Filenames are **versioned, never overwritten in place.** A redesigned banner is
`-v2`; `-v1` stays forever, because older email still points at it.

Registry keys are defined in `docs/BANNERS.md` in the communications repo. The
signature uses an unguessable filename so it is not trivially discoverable, even
though this repository is public.

## Adding an image

1. Commit the file under `banners/` or `stills/<YYYY-MM>/` and push.
2. Wait 10–60 seconds for GitHub Pages to rebuild.
3. Verify:
   ```
   curl -sI https://foresightmetrix.github.io/ai-business-brief-assets/<path> | head -1
   ```
   → `HTTP/2 200`
4. Record the URL and the verification date in `docs/BANNERS.md` in the
   communications repo.

Push this repository **before** sending any email that references a new image.
