# QTSurfer Engine — Java API docs

Published API reference for the QTSurfer trading engine: the types a strategy author or
an embedding application actually uses — strategy bases, the market-data model, the
indicator catalogue, backtesting fee/slippage/fill models — not everything that happens
to be `public` in the jars.

**Live site:** https://qtsurfer.github.io/qtsurfer-engine-java-docs/

This repository holds the built static site at its root, published via GitHub Pages
(source: `main`, `/`). The engine's own repository documents how the surface is derived
and enforced (`docs/public-api/README.md` there) and a CI job there rebuilds and pushes
here. `README.md` and `LICENSE` are the only files not overwritten on rebuild; everything
else is generated — do not hand-edit it.
