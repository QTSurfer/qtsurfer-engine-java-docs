# QTSurfer Engine — Java API docs

Published API reference for the QTSurfer trading engine: the types a strategy author or
an embedding application actually uses — strategy bases, the market-data model, the
indicator catalogue, backtesting fee/slippage/fill models — not everything that happens
to be `public` in the jars.

**Documentation:** https://www.qtsurfer.com/docs/developers/java-api

This repository holds the built static site at its root. The QTSurfer website serves it at
the address above, with a selector for the published versions; GitHub Pages is not used. The
engine's own repository documents how the surface is derived
and enforced (`docs/public-api/README.md` there) and a CI job there rebuilds and pushes
here. `README.md` and `LICENSE` are the only files not overwritten on rebuild; everything
else — including `versions.json` — is generated. Do not hand-edit any of it.

`main` always holds exactly one live snapshot: the most recently published engine
version. It is not per-version browsable — publishing overwrites it.

Every publish is tagged `vX.Y.Z` after the engine version it was built from. The tag is
**not immutable**: a docs-only fix against an already-released engine version (a typo in
`docs/public-api/overview.html`, a scope correction like this repository's own history)
republishes under the same tag, and the tag is force-moved to the new commit. Diff two
tags to see what the public API surface changed between engine versions
(`git diff v0.99.65 v0.99.70`, or GitHub's compare view) — that comparison is always
against whatever a tag currently points at, not a fixed historical artifact.

`versions.json` is derived from the tag list on every publish, so it cannot drift from
what `git tag` actually reports:

```json
{
  "latest": "v0.99.70",
  "versions": ["v0.99.70", "v0.99.65"]
}
```

`versions` is newest first. It is what the version selector on the website reads to know
which engine versions have published docs and which is current; the website renders each
of those tags. A tag can also be browsed here:
`https://github.com/QTSurfer/qtsurfer-engine-java-docs/tree/v0.99.65`.
