# FAQ & Troubleshooting

The common failures and how to fix them. Still stuck? Ask in the [Discord](https://discord.gg/QF5ZjVT4Sa).

## My game won't boot. What's wrong?

For arcade games, confirm the arcade BIOS (`naomi.zip`, `naomi2.zip`, `awbios.zip`, `segasp.zip`) is in `BIOS/`. For a `.gdi` or `.cue`, confirm every referenced track (`.bin`/`.raw`/`.img`) is present. Prefer a single-file `.chd` or `.cdi` to avoid missing-track problems.

## An arcade rip fails to import or load.

Arcade rips come in several shapes. See [Arcade & Naomi Rips](arcade.md) for decrypted single-cart `.bin` dumps, multi-track GD-ROM dumps, and Naomi GD-cartridge `zip`+`.chd` layouts.

## How do I add a multi-disc game?

Import each disc, then use an `.m3u` playlist listing the disc images in order. iFly groups them as one multi-disc game. [Dumping Dreamcast Discs](dumping-dreamcast.md) shows how to build the playlist.

## What syncs over iCloud?

Saves, VMUs, and BIOS sync across your devices over iCloud. ROMs do not sync — import those on each device.

## Do auto-saves interrupt gameplay?

No. iFly serializes save states off the main thread, so timed auto-saves run without stalling emulation.

## How do I set up controllers?

See the [Controllers](https://ifly-emu.com/controllers/) page for MFi, DualShock, DualSense, Xbox, and Switch mappings, plus on-screen control options.

## How do I get better performance or higher resolution?

iFly runs JIT-less at full speed on Apple silicon and can upscale to `1440p` or `4K` on recent devices. Use per-game options to tune internal resolution, frame pacing, and ProMotion refresh.
