# 20201213

- Support for zero-copy framebuffer in video threaded and 'oga' video driver
  (not yet upstreamed to RetroArch)
- New duckstation libretro core
- Updated ogainfo command that displays more information
- RetroArch updated to latest master, includes new Wi-Fi interface

# 20201212

- Overclock support for 1.4GHz and 1.5GHz (see wiki for instructions)

# 20201210

- pcsx_rearmed chd + RetroAchievments finally fixed
- retrorun32 pcsx_rearmed spring fixed
- new TIC-80 libretro core added

# 20201113

- Add ffmpeg (video playback) support to retroarch

# 20201024

- New retrorun with support for pause (F2+B), ffwd (F2+A), reset (F2+X), also
  added support for duckstation.
- New dark mode (global F5+TR2 to enable, F5+TL2 to disable) turns off sshd,
  chronyd, NetworkManager and rfkills wifi. Battery went from 305 -> 220 so it's
  a big savings and less background noise.
- CPU and RAM is set to performance by default, performance script only toggles
  GPU. This is because I showed that performance mode really helps with response
  times. Battery went from ~280 -> 305 so it's not that bad. Dark mode more than
  mitigates this anyway.
- ogage updated to control dark mode.
- Retroarch 'oga' driver updates
  https://github.com/libretro/RetroArch/pull/11481 and using latest master
  (still 1.9.0).
- rrvl-spring package now centralizes spring libretro files and installs them to
  ~/.config/retroarch/cores. Submit PR's to
  https://github.com/valadaa48/libretro-core-info.
- A lot of retrorun spring files for those that prefer retrorun over retroarch

# 20200913

- Optimized retroarch's input handler

# 20200911

- More odroid-go2-rrvl-kernel optimizations
- Added 26 cores to retroarch core downloader, might be the biggest collection
  now
- Added optimized tic80 core to core downloader

# 20200910

- Add wifi firmware to fix issues with recognizing certain wifi devices

# 20200909

- odroid-go2-rrvl-kernel is an alternative, experimental kernel with some
  optimizations. Install manually via `sudo xbps-install -Su
  odroid-go2-rrvl-kernel` and reboot.
- SDL2 mappings added for v10 (thanks npaladin2000)
- Further optimizations to odroid-go2-rrvl-kernel
- Fix SPK/HP detection in ogage thanks to MiniminiMinKim for reporting the issue

# 20200908

- SDL2 finally fixed with sane default mappings for v11 (v10 still WIP)
- ppsspp-odroigo2 updated with standalone launch script in `/roms/_rrvl`
- After upgrading, run `/roms/_rrvl/reset_ppsspp.sh` and you'll have a much
  better experience. It now has a built-in file browser.
- termwrap now sets the TERM var appropriately so it works with dialog(1)

# 20200905

- ogage (global events daemon) further optimized to use basically 0% CPU

# 20200904

- Fix SDL2 controller mappings (this doesn't mean you definitely don't need to
  remap in SDL apps!)
- ppsspp recompiled against SDL2-2.0.10 for compatibility
- New directory `/roms/_rrvl` for system managed scripts. This is where you'll
  find update.sh and standalone launchers like ppsspp.sh. Users should use
  another directory such as /roms/sh for their own scripts.
- Fixed libGLESv2 issue that prevented dreamcast from running.
- NOTE: You will *need* to remap PPSSPP controls. We can't force v11 or v10
  mapping by default for obvious reasons. You just need to do this once.
- Wifi powersave is disabled in NetworkManager. Thanks to @pyghast for testing.

# 20200903

- Port wifi disable power savings from RR
- ppsspp-odroidgo2 now replaces ppsspp-go2. You may have to run
  `sudo xbps-install -Su ppsspp-odroidgo2` to install it.

# 20200902

- ppsspp-odroidgo2 update to include speedup patch

# 20200901

- Switch to NetworkManager from wpa\_supplicant. You *must* reboot after this update
  and then reconfigure your network in retroarch (Settings-\>WiFi).
- Add WiFi configuration to retroarch
- Retroarch 1.9.0 64bit and 32bit
- Final image now includes flycast 32bit libretro core to fix issue with built-in spring
- SDL2 2.0.10 now global standard
- Turn off text on tty1 completely, use tty2 for console
- Add update.sh spring to run full system update within retroarch
- New kernel version
- Fix libGLESv2 ldconfig issue, this was caused by a bad update of the libmali drivers
- Add retrorun 64bit and 32bit package
- Add unzip, rar, 7z and xtools package by default
- RetroArch now defaults to glcore + ozone (thanks to Firebird\_WS6)
- RRVL 20200901 Final Image release!

# 20200715

- Retroarch oga driver last character in on-screen messages being cutoff fixed
- Retroarch add shutdown and reboot

# 20200714

- Downgrade SDL2 to 2.0.10 since 2.0.12 has issues

# 20200709

- kernel update with a boat load of more wifi drivers
- ppsspp-odroidgo2 updated to 1.10.2 from 1.9.4
- ppsspp-go2 removed

# 20200707

- update script updated to update xbps first
- Add openbor-odroidgo2. Launch with `openbor_direct <path to pak>`. Look at the script on how it works.
- update retroarch to use new core URL

# 20200706

- emulationstation-go2 with v10 and v11 compat es_input and es_systems.cfg from RR installed
  to ~/.emulationstation. To boot to ES instead of RA, run `sudo rm /var/service/retroarch`
  then `sudo ln -s /etc/sv/emulationstation /var/service/` and reboot.

# 20200703

- Integrate v10 and v11 joypad into SDL2-go2 and SDL2-2.0.10-g2
- New optimized snes9x_libretro core
- Ozone scaled by 1.5x

# 20200702

- Add spring_shell to launch .sh scripts from retroarch
- Retroarch default config points bios to `/roms/bios`
- New package: ppsspp-odroidgo2 from upstream with correct SDL2 mappings for both v10 and v11
- SDL-go2 library fixes
- drastic now is patchelf'd to point to SDL 2.0.10 explicitly

# 20200701

- retroarch: change save and states dir to ~/saves
- retroarch: add openal audio driver
- Add `update` command to update both 64bit and 32bit

# 20200629

- fixed spring-ppsspp (incorrect filename in command)
- added 32bit flycast_libretro (`sudo arm-xbps install -S flycast_libretro`)
- Added spring flycast_libretro 32bit to rr-base
- Fixed volume from going to 100% upon resume from sleep
- No more text on the screen
- ppsspp with FMV patch (thanks to EmuELEC's patch)


<!-- vim: set tw=80: -->
