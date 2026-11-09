# WSRTC V0.2.4

WonderSwan RTC chip emulator for ARM 32.

## This fork and integration

This repository is the GimoXagros fork of [FluBBaOfWard/WSRTC](https://github.com/FluBBaOfWard/WSRTC). `V0.2.4` is the core version in `Version.h`; this fork has no standalone GitHub Release binaries.

The custom [WSCart](https://github.com/GimoXagros/WSCart) repository includes WSRTC as a submodule, and [NitroSwan](https://github.com/GimoXagros/NitroSwan) pins WSCart as part of its own source tree. Initialize recursive submodules from the chosen emulator tag to obtain the matching RTC revision. This repository's latest branch is not a substitute for that pinned revision. Build and validation instructions belong to the [consuming emulator](https://github.com/GimoXagros/NitroSwan/blob/main/Docs/DevelopmentGuide.md).

### RTC protocol correction (2026-11-09)

[Upstream PR #2](https://github.com/FluBBaOfWard/WSRTC/pull/2) was withdrawn without merging: upstream already fixed the packed-BCD leap-year calculation, and invalid seconds must carry into minutes when corrected. This fork now uses the calendar and per-register command/data handling from upstream `dd7a8feb14174cb5a7d1dcc11f4facd9cb10a245`, replacing the earlier whole-date saturation helper. Writing seconds `E5` reads back `65` immediately, then becomes `00` with a minute carry on the next tick.

The fork retains `wsRtcUpdate(chip)` once per second, status-read readiness, its 20-byte ARM structure and 16-byte saved state. WSCart owns the clock divider; do not substitute upstream's two-argument update API or extra cycle field. Linked ARM regression coverage lives in NitroSwan's `tools/validate_rtc_runtime.py`. Alarm/IRQ accuracy and physical-cartridge validation remain outside this correction; existing release tags are unchanged.

## Projects that use this code

* <https://github.com/FluBBaOfWard/NitroSwan>
* <https://github.com/FluBBaOfWard/SwanGBA>

## Credits

Thanks to lidnariq for information about the WS RTC.
<https://forums.nesdev.org/viewtopic.php?p=262192>

Fredrik Ahlström

<https://bsky.app/profile/therealflubba.bsky.social>

<https://www.github.com/FluBBaOfWard>

X/Twitter @TheRealFluBBa
