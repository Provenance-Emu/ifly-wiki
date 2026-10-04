# Importing Games

iFly imports games four ways. All of them route through the same importer, so the file ends up in the right place no matter which you use.

## Files app / document picker

In iFly, add games from the Files app. Pick a single file (`.chd`, `.cdi`, `.gdi`) or a whole folder for multi-track dumps. This works on iOS, iPadOS, and tvOS.

## Drag-and-drop (iPad)

On iPad, drag files from Files, Safari downloads, or another app straight onto the iFly library grid.

## Wi-Fi upload (WebDAV / HTTP)

Start the built-in web server in iFly, then scan the QR code or open the shown URL in a desktop browser and drag files in. Works over WebDAV or plain HTTP on iOS, tvOS, and macOS — the easiest way to move large arcade sets onto Apple TV.

## URL scheme

Links using the `ifly://` scheme open a file and import it through the same policy.

## Where files go

Games land in `ROMs/`, BIOS in `BIOS/`, controller skins in `Skins/` (under Documents or Caches). Skins (`.deltaskin`, `.manicskin`) are routed to `Skins/` automatically.

> **What happens to archives.** Disc archives (a `.zip` or `.7z` containing a `.gdi` or `.cue`) are extracted on import. Arcade romsets are copied as-is so the MAME loader can open them in place. Extraction is all-or-nothing: a partial extract rolls back and leaves the source archive alone.
