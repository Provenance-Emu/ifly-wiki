# Dumping Dreamcast Discs

iFly plays Dreamcast disc images, so a game you own has to become a file first. This page covers how to make that file from a real disc, shrink it to one `.chd`, and get it into iFly.

iFly does not provide, link to, or endorse any source of pre-dumped games. Dump discs you own, from hardware you own.

## Why a PC drive isn't enough

Dreamcast retail games ship on GD-ROM, a proprietary disc that holds about 1 GB. A normal PC optical drive can read only the low-density area of one, and the game data sits in the high-density area. So the dump is done by the Dreamcast itself, which reads its own discs and hands the tracks to a computer.

A GD-ROM dump is a `.gdi` index plus separate track files (`.bin`, `.raw`, `.iso`). There are always at least three tracks, and iFly needs every one of them.

## What you need

* A working Dreamcast that can boot a burned CD-R.
* A Dreamcast SD card adapter (it plugs into the serial port, the one the link cable uses) and an SD card.
* **Dreamcast SD Rip** v1.1, burned to a CD-R. The [Hidden Palace page](https://hiddenpalace.org/Dreamcast_SD_Rip) names DiscJuggler for the burn.
* A computer with an SD card reader.

## Dump with SD Rip

1. Connect the SD adapter, with the card in it, to the Dreamcast.
2. Boot the Dreamcast SD Rip disc.
3. Swap in the disc you want to dump.
4. Choose `GD-ROM <bin> all track` from the menu.
5. Wait for it to finish, then copy the files from the SD card to your computer.

Budget about 40 minutes. One [write-up of the SD adapter](https://multimedia.cx/eggs/dreamcast-sd-adapter-and-dreamshell/) measured 38 to 40 minutes for a 900 to 1000 MB disc, using DreamShell, a second tool that works with the same adapter and has its own ripping interface. The SD Rip page also covers GD-R prototypes, which need System Disc 2. Retail discs don't.

## No SD adapter?

A Dreamcast with a Broadband Adapter can serve the disc over your network using an `httpd` boot disc (the [Provenance wiki](https://wiki.provenance-emu.com/installation-and-usage/roms/ripping-roms) walks through httpd-ism). It works, but it hands over one track at a time at roughly 40 KB/s, so a full disc takes hours. Use the SD adapter if you can.

## Check the files

Before you do anything else, open the `.gdi` in a text editor. It lists every track file by name. Each one has to exist next to it, and a track that is missing or empty means a bad dump. Run it again before converting.

## Convert to one CHD

A `.gdi` won't boot if a single track goes missing, and the track files add up to a lot of loose data. `.chd` is one compressed file, and the [formats table](https://ifly-emu.com/guide/formats/) puts it at roughly 700 MB down to 300 MB. It comes from `chdman`, part of the MAME tools. On a Mac:

```bash
brew install rom-tools
```

Then point it at the `.gdi`, with the track files in the same folder:

```bash
chdman createcd -i game.gdi -o game.chd
```

Keep the original tracks until you've booted the `.chd` once.

## Multi-disc games

Dump and convert each disc on its own. Then write an `.m3u` playlist next to the `.chd` files that lists them in order, one per line:

```
Game (Disc 1).chd
Game (Disc 2).chd
```

Import the discs and the playlist, and iFly groups them as one game. The [FAQ](https://ifly-emu.com/guide/faq/) has the same steps.

## Get it into iFly

Add the `.chd` from the Files app, drag it onto the library on iPad, or upload it over Wi-Fi. If you skipped the conversion and kept a `.gdi`, pick the whole folder so every track comes along. See [Importing Games](https://ifly-emu.com/guide/importing/) for all four ways.

## Arcade discs are a different job

Naomi, Naomi 2, and other arcade GD-ROM games come from arcade hardware, not a home Dreamcast. Their discs pair with a security chip and a DIMM board, so the steps on this page don't apply. The [Dumping Guide's Sega page](https://dumping.guide/discs/sega) points to the Redump team's documentation for those systems. For what iFly does with the files, see [Arcade & Naomi Rips](https://ifly-emu.com/guide/arcade/) and [BIOS Setup](https://ifly-emu.com/guide/bios/).
