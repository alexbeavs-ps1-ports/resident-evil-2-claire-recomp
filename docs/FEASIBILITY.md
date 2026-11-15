# Resident Evil 2 Claire feasibility

## Current result

The `main` branch binds the owned USA Dual Shock Claire program `SLUS_007.56`
(disc 2, serial SLUS-00756) to PSXRecomp pin I 0.1.23 (`578bd3b`). Its entry
point is `0x800783C0` and its SHA-256 is
`1664E7C634F8CFD03E421F10A6D7E8E8E9FA9BC7982F7C649CC86D28A983FBEE`.

The Leon disc uses a different program and lives in
`alexbeavs-ps1-ports/resident-evil-2-recomp`. The stable framework does not combine these
programs into one setup host. This source tree contains no retail input or private path.

## Known boundary

Each program needs its own clean build, package, startup, save, scenario, media,
audio, controller, and gameplay evidence. A Leon pass does not qualify Claire,
and a Claire pass does not qualify Leon. Their package prefixes stay distinct.

Experimental decompilation and function overrides remain outside this source.

## Package source gates

The release workflow rejects a mismatch between the build, package, and
deferred-relaunch executable names. The package wrapper treats
`launcher_assets` as optional and stages it only when the clean source
contains a package asset.
