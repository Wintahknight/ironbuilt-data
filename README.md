# IRONBUILT community datasets

Community-derived game datasets consumed by the [IRONBUILT](https://github.com/Wintahknight/ironbuilt)
army builder. The app ships with **no game data** — on first run you add a dataset from here (the same
"bring your own data" model apps like BattleScribe and New Recruit use).

## What's here

- **`manifest.json`** — the index the app fetches. Lists available datasets (id, name, edition,
  version, provenance, download URL, sha256, size). The app reads this to offer datasets to add and to
  detect updates.
- **`datasets/*.json`** — the dataset bundles themselves. Each is a single self-contained JSON with
  every faction's datasheets, detachments, and the art map.
- **`maps/<id>/*.jpg`** — deployment-map imagery referenced by the map datasets (see below). Served
  over the same jsDelivr CDN.

### Dataset kinds

Most bundles are army-list data (factions/datasheets/detachments). Two companion bundles cover the
matched-play mission pack, so consumers other than the army builder (e.g. reference bots) can share the
same source of truth:

- **`wh40k-11e-missions`** — primary mission matrix (`primaries.matrix[yours][opponents]`) and the
  secondary mission cards (`secondaries.cards`).
- **`wh40k-11e-maps`** — the deployment layouts from the Event Companion. Each layout carries its
  disposition matchup, layout letter, and an `image` URL pointing at `maps/wh40k-11e/*.jpg` in this
  repo. Matchups are stored directionally (attacker/defender) but should be matched unordered.

Bundles are served to the app over the **jsDelivr** CDN, version-pinned by git tag, e.g.
`https://cdn.jsdelivr.net/gh/Wintahknight/ironbuilt-data@v2026.06.03-1324/datasets/wh40k-10e.json`.

## Provenance & legal

These datasets are **community-derived** — compiled, reformatted, and quality-checked by members of the
community and provided for personal use. Warhammer 40,000, and all unit and faction names, rules, and
points values, are the intellectual property of **Games Workshop**. This is an unofficial, fan-made
compilation. It is **not affiliated with, licensed by, or endorsed by Games Workshop**. Adding a dataset
to the app is the user's choice; the app itself distributes no game content.

## Adding a new dataset / version

1. Build the bundle (`build-dataset.ps1` in the app repo) → `datasets/<id>.json`.
2. Copy it here, add/update its entry in `manifest.json` (bump `version`, update `sha256`/`bytes`,
   point `url` at the new tag).
3. Commit, then tag the release (`git tag v<version> && git push --tags`) so jsDelivr pins it.
