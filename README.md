# Ripple Effect — engine releases

Prebuilt builds of the **Ripple Effect engine**: the part of
[Ripple Effect](https://ripplefx.app) that compiles a project into a campaign
and plays it. This repository holds the releases and nothing else. The source
is private and lives elsewhere.

| I want to… | Go here |
| --- | --- |
| Use Ripple Effect | [Download the app](https://ripplefx.app/download) — it bundles the engine, and updates it |
| Report something broken | [Support](https://github.com/WilliamKarolDiCioccio/ripple_effect_support) |

Nobody needs to download anything from here by hand. The app bundles the
engine and can take a fix to it in the background; the build tooling for the
app's own packages downloads from here and checks every archive against a
digest pinned in its source tree.

## What a release contains

Each release is tagged `engine-v<version>` and carries, per platform:

| File | What it is |
| --- | --- |
| `ripple-engine-<version>-<target>.tar.gz` | `lib/` — the engine library; `bin/ripple` — the terminal player; `bin/compile` — the compiler; `NOTICE` |
| `engine-manifest.json` | The version, the campaign formats it reads and writes, and the SHA-256 of every archive and library |
| `engine-manifest.json.sig` | An Ed25519 signature over the manifest's exact bytes |
| `SHA256SUMS` | `sha256sum` output over the archives and the manifest |

The targets are `x86_64` and `aarch64` for Linux (glibc 2.35 or newer), macOS
(12 or newer) and Windows.

## Versions

`MAJOR.MINOR` names a **version contract**: a milestone of Ripple Effect —
1.5 *Multiclassing*, 1.6 *Grammar Lich* — and the campaign formats, file
formats and engine interface that come with it. Every engine with the same
`MAJOR.MINOR` is interchangeable; a `PATCH` release only fixes, speeds up or
tidies. An engine plays campaigns made under its own contract and under the
earlier ones its manifest lists in `reads`.

A published release is never replaced. A release candidate (`-rc.N`) is
marked as a pre-release and is never offered to an installed app.

## Licence

The engine is proprietary, like the application it is part of, and governed by
the [End-User Licence Agreement](LICENSE) — the authoritative copy is at
[legal.ripplefx.app](https://legal.ripplefx.app/eula/). Questions about it:
legal@ripplefx.app.

© 2026 ConnectingTheDots — a trade name of William Karol Di Cioccio, VAT
IT02224180667. All rights reserved.
