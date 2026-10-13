# ofx-rs

Ready-to-install OpenFX effects and a separate After Effects adapter. Product sources remain private; this repository
is the public destination for binary releases and user distribution documents.

## Download 0.1.0

| Product | Platforms | Release |
|---|---|---|
| 35 OpenFX effects in one bundle | Windows x64, Linux x64, macOS arm64 | [Effects 0.1.0](https://github.com/ssoj13/ofx-rs-pub/releases/tag/v0.1.0) |
| After Effects OpenFX adapter | Windows x64, macOS universal arm64/x86_64 | [AE adapter 0.1.0](https://github.com/ssoj13/ofx-rs-pub/releases/tag/ae-v0.1.0) |

Windows effects have a ZIP and optional unsigned MSI. Every archive contains INSTALL.md and BUILD.json with
compiled-deadline metadata and binary hashes; SHA256SUMS covers the release downloads. macOS AE is experimental,
ad-hoc signed and unnotarized.

Both evaluation products render through **December 31, 2026 inclusive (UTC)** and stop at
**January 1, 2027 00:00 UTC**. The cap is compiled into the effects and adapter; a build override can only shorten it.
This release includes continuous Matrix Rain motion and the corrected AE parameter UI definitions.

## Install

Close hosts that loaded the plug-ins. Extract the effects ZIP and copy the entire ofx-effects.ofx.bundle into the
standard folder, or put its parent folder on OFX_PLUGIN_PATH:

- Windows: C:\Program Files\Common Files\OFX\Plugins
- Linux: /usr/OFX/Plugins
- macOS: /Library/OFX/Plugins

Keep one copy on the search path. For AE, install the effects first and then follow the separate adapter archive's
scanner/installation commands as the same user who runs AE. Close AE for installation/rescan and preserve the
local parameter-ID ledger when updating saved projects. Default menus use categories such as ofx-rs Fractals;
scan with OFX_AE_MENU=single for one Ofx-rs submenu.

## Environment lighting

Both 3D fractal variants accept HDR/EXR or the embedded Venice Sunset panorama, with Environment Map enabled.
Browse opens an existing HDR/EXR file; cancel preserves the current map.

In AE, a separate Env Layer may provide an equirectangular panorama: use scene-linear Rec.709 in a linear 32-bpc
composition, enable Environment Map, set Environment Source to Env Layer and select the panorama layer.
Intensity/rotation apply to either source; Source remains the independent compositing plate. No color-space
transform is applied, and a missing selected Env Layer is an error.

The [user book](https://ssoj13.github.io/ofx-rs/) includes the effect gallery, 13 enabled-HDRI scene examples,
parameter reference and [AE instructions](https://ssoj13.github.io/ofx-rs/host/after-effects.html).
Live acceptance of the latest AE UI/picker/Env Layer behavior remains in progress.

## Release delivery

Completed native release builds automatically create or refresh the corresponding evaluation release here.
CI verifies the full platform inventory, compiled deadline, binary hashes, SHA256SUMS and uploaded server digests.
Old producer runs cannot overwrite newer builds. Product sources, per-user manifests, registration snapshots
and ID ledgers are not mirrored into this repository.
