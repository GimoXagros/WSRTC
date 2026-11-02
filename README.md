# WSRTC V0.2.4

WonderSwan RTC chip emulator for ARM 32.

## This fork and integration

This repository is the GimoXagros fork of [FluBBaOfWard/WSRTC](https://github.com/FluBBaOfWard/WSRTC). `V0.2.4` is the core version in `Version.h`; this fork has no standalone GitHub Release binaries.

The custom [WSCart](https://github.com/GimoXagros/WSCart) repository includes WSRTC as a submodule, and [NitroSwan](https://github.com/GimoXagros/NitroSwan) pins WSCart as part of its own source tree. Initialize recursive submodules from the chosen emulator tag to obtain the matching RTC revision. This repository's latest branch is not a substitute for that pinned revision. Build and validation instructions belong to the [consuming emulator](https://github.com/GimoXagros/NitroSwan/blob/main/Docs/DevelopmentGuide.md).

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
