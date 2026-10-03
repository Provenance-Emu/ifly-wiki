# Arcade & Naomi Rips

Naomi, Naomi 2, and Atomiswave rips arrive in several shapes. iFly detects each and routes it correctly — including formats stock Flycast can't open. You still need the matching arcade BIOS (see [BIOS Setup](bios.md)).

## Decrypted single-cart ROMs

Many archive.org rips are a single decrypted `.bin` named after the game, e.g. `VirtuaFighter4.zip` containing `VirtuaFighter4.bin` with no `.ic*` chip files. iFly detects the single-cart shape, routes it to the decrypted-ROM path, and Flycast peeks the board header (`NAOMI` / `Naomi2`) to auto-select the BIOS. Stock Flycast sends these to its MAME loader and fails.

## Multi-track GD-ROM dumps

Arcade GD-ROM games sometimes come as a `.cue` plus several `.bin` tracks (e.g. Slashout). iFly treats the `.cue` as a disc, extracts it like a Dreamcast multi-track set, and verifies every referenced track exists.

## Naomi GD-cartridge (zip + CHD)

Some Naomi games pair a MAME cart zip with a GD-ROM image in a subfolder: `senkosp.zip` alongside `senkosp/gdl-0030a.chd`. iFly carries the sibling CHD with the cart zip on import and warns if the CHD is missing before boot.

## MAME chip-set zips

Traditional MAME romsets (a `.zip` of `.ic*` chip files) are copied as-is and opened directly by the MAME loader.

> **If an arcade game won't boot.** Check that the arcade BIOS (`naomi.zip`, `naomi2.zip`, `awbios.zip`, or `segasp.zip`) is in `BIOS/`, and that a GD-cartridge game's companion `.chd` sits in its named subfolder.
