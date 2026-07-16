# Contributing to the IRONBUILT community dataset

This dataset is **built and corrected by the people who use it**. It is not a publication of any
game publisher's material: it is a community-maintained, machine-readable record that players
compile, check against their own books, and correct when it is wrong.

Every accepted data correction is recorded in [`contributions/CONTRIBUTIONS.md`](contributions/CONTRIBUTIONS.md).

## Ways to contribute

**1. From inside the app (easiest, and how most corrections arrive)**

Use **Report Bug** in IRONBUILT and pick one of the *Game data* categories:

| Category | Use it for |
| --- | --- |
| Wargear / loadout | A unit's options, defaults or counts are wrong |
| Missing or wrong datasheet data | Stats, abilities, keywords, points |
| Detachment / stratagem text | Detachment rules, enhancements, stratagems |
| Rules / math accuracy | A rule the calculator models incorrectly |

Those categories file a **data suggestion** rather than an app bug. The app auto-attaches the
faction, detachment and unit you were looking at, so a one-line note is usually enough.

There are two optional fields:

- **Your email** — only used to reply to you. **Never published.**
- **Credit name** — an opt-in, **public** name for the contribution log. Leave it blank and the
  entry is logged as an anonymous community reporter.

**2. Open an issue or a pull request**

Edit the JSON directly if you prefer. Please cite the source you checked against (which book,
which FAQ/errata, which Munitorum Field Manual revision) so the next person can verify it.

## What makes a good data suggestion

- **Say what is wrong and what it should be.** "Shining Spears shouldn't have Aspect Shrine Token"
  beats "Aeldari data broken".
- **Name your source.** The faction pack, the MFM entry, the datasheet. Corrections are only
  applied when they can be checked against a source.
- **One thing per report.** Easier to verify, credit and apply.

## How a suggestion becomes a dataset change

1. It arrives as a data suggestion and is triaged.
2. It is **verified against a source** — a maintainer checks the claim independently. Reports that
   turn out to be correct-as-is are closed with an explanation, not applied.
3. If it holds up, the dataset is edited, audited, rebuilt and republished.
4. The suggestion is appended to `contributions/CONTRIBUTIONS.md`, crediting the reporter (by their
   chosen credit name, or as anonymous) and linking the commit that carried the change.

Not every suggestion is applied, and that is the point: the log records what the community actually
contributed and what came of it.

## Licence

By contributing you agree that your contribution is licensed under the same terms as this
repository (see [`LICENSE`](LICENSE)) and that your **credit name, if you supply one, is published**
in the contribution log. Please see [`NOTICE`](NOTICE) for the intellectual-property position.
