# Rayman Legends — PS5 activation fix

PS4 game: CUSA00031 / 01.00. Tested on PS5 firmware 11.60 with the GronedWaffel etaHEN 11.00–13.60 experimental build and executable base 0x400000.

The original invincibility cheat failed to activate: the log stopped before writing the patch. This SHN adaptation resolves libkernel.sprx and uses absolute game addresses to bypass the failing eboot.bin lookup. The underlying lookup failure has not been independently diagnosed. After this fix, etaHEN reports successful activation and the invincibility patch reads back correctly.

Gameplay confirmed by the owner: Invincibility, Speed x3 and the corrected 9,999,999 Total Lums. Speed x2 and the remaining effects need individual testing. The pack has 13 entries with English descriptions, including Lums x10. Both Teensy bonus entries were removed because they inflated the total without completing level collectibles.

Credits: by douityourself for PS5 adaptation and packaging; Reddevil82, hejran7 and d01v for original cheats. Distributed under the repository GPL-3.0 license.

## Manual installation for the tested configuration

Keep a backup of existing Rayman 01.00 trainers and remove their JSON/MC4/SHN entries from the active indexes. Copy only this CUSA00031_01.00.shn into /data/etaHEN/cheats/shn/ and register it in shn.txt. In etaHEN Toolbox → Cheats (WIP), select Cache And Reload Cheats List, then reopen the game cheats menu. Disable incompatible options before switching variants.

This directory is intentionally outside the indexed trainer directories. It preserves existing PS4 trainers and avoids loading two Rayman trainers together while maintainers review platform-specific packaging. Do not register this variant in the shared index until that packaging decision is made. Compatibility with other firmware, game versions and memory layouts is unverified.

Validation: 23 local tests passed; all generated patches match the catalogue; the deployed SHN was verified byte for byte over FTP.
