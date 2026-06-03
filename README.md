# IRONBUILT community datasets

Community-derived game datasets consumed by the [IRONBUILT](https://github.com/Wintahknight/ironbuilt)
army builder. The app ships with **no game data** — on first run you add a dataset from here (the same
"bring your own data" model BattleScribe/New Recruit use with [BSData](https://github.com/BSData)).

## What's here

- **`manifest.json`** — the index the app fetches. Lists available datasets (id, name, edition,
  version, provenance, download URL, sha256, size). The app reads this to offer datasets to add and to
  detect updates.
- **`datasets/*.json`** — the dataset bundles themselves. Each is a single self-contained JSON with
  every faction's datasheets, detachments, and the art map.

Bundles are served to the app over the **jsDelivr** CDN, version-pinned by git tag, e.g.
`https://cdn.jsdelivr.net/gh/Wintahknight/ironbuilt-data@v2026.06.03-1324/datasets/wh40k-10e.json`.

## Provenance & legal

These datasets are **community-derived**, compiled from the open [BSData](https://github.com/BSData/wh40k-10e)
catalogues. Warhammer 40,000, unit and faction names, rules, and points values are the intellectual
property of **Games Workshop**. This is an unofficial, fan-made compilation provided for personal use.
It is **not affiliated with, licensed by, or endorsed by Games Workshop**. Adding a dataset to the app
is the user's choice; the app itself distributes no game content.

## Adding a new dataset / version

1. Build the bundle (`build-dataset.ps1` in the app repo) → `datasets/<id>.json`.
2. Copy it here, add/update its entry in `manifest.json` (bump `version`, update `sha256`/`bytes`,
   point `url` at the new tag).
3. Commit, then tag the release (`git tag v<version> && git push --tags`) so jsDelivr pins it.
