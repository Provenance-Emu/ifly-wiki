# BIOS Setup

> **Dreamcast needs no BIOS.** Almost every Dreamcast game runs on iFly's built-in HLE BIOS (Reios). You only need a real BIOS for the arcade systems (Naomi, Naomi 2, Atomiswave, System SP).

Put BIOS files in the `BIOS/` folder. Names are case-normalized to lowercase, and MAME romsets must keep their exact basename.

| System | File | Required | Notes |
| --- | --- | --- | --- |
| Dreamcast | `dc_boot.bin` | Optional | Boot animation only. HLE BIOS (Reios) is used by default. |
| Dreamcast | `dc_flash.bin` | Optional | Flash / NVRAM (clock, settings). Pair with dc_boot.bin for full accuracy. |
| Naomi | `naomi.zip` | Required | MAME romset. Basename must match exactly. |
| Naomi 2 | `naomi2.zip` | Required | MAME romset. |
| Atomiswave | `awbios.zip` | Required | MAME romset. |
| System SP | `segasp.zip` | Required | MAME romset. |
| House of the Dead 2 | `hod2bios.zip` | Optional | Game-specific board. |
| Ferrari F355 | `f355bios.zip` / `f355dlx.zip` | Optional | Challenge / Deluxe variants. |
| Airline Pilots | `airlbios.zip` | Optional | Also covers Sega Strike Fighter. |
