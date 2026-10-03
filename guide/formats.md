# Supported Formats

iFly reads the same disc and arcade formats as Flycast, plus extra handling for odd arcade rips (see [Arcade & Naomi Rips](arcade.md)). To make your own Dreamcast dumps, see [Dumping Dreamcast Discs](dumping-dreamcast.md).

> **Prefer CHD or CDI over GDI.** A `.chd` or `.cdi` is a single file — nothing to lose. A `.gdi` references separate `.bin`/`.raw` tracks, and the game will not boot if any track is missing. `.chd` is also compressed, roughly halving disk use.

| Extension | Kind | Notes |
| --- | --- | --- |
| `.chd` | Standalone disc | Compressed, single file. Best storage (~700 MB → ~300 MB). Dreamcast + Naomi GD-ROM. |
| `.cdi` | Standalone disc | Single-file Dreamcast image. No tracks to lose. |
| `.iso` | Standalone disc | Single-file image. |
| `.gdi` | Index | GD-ROM index that points at .bin / .raw / .img tracks. All tracks must be present. |
| `.cue` | Index | CUE sheet that points at .bin tracks. |
| `.bin` / `.raw` / `.img` | Track | Payload tracks referenced by a .gdi or .cue. |
| `.dat` | Arcade payload | Decrypted single-cart arcade ROM (often inside a .zip). |
| `.lst` | Arcade list | Metadata for MAME-style arcade rips. |
| `.m3u` | Playlist | Groups multiple discs into an ordered multi-disc set. |
| `.elf` | Homebrew | Raw homebrew executable. |
| `.zip` / `.7z` | Archive | Disc archives are extracted; arcade romsets copied as-is. |
| `.deltaskin` / `.manicskin` / `.skin` / `.emuskin` | Controller skin | Routed to the Skins folder. |
