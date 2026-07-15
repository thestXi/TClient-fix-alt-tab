# TClient Alt-Tab Fix

An unofficial Windows x64 build of TClient/DDNet for players who use a stretched 4:3 resolution on a 16:9 display and experience a long black screen when switching applications with Alt+Tab.

## What this build fixes

- Fullscreen mode no longer changes the Windows desktop resolution.
- The selected 4:3 resolution is preserved as the logical aspect ratio and stretched to fill the display.
- The physical display size is handled separately for the viewport, mouse coordinates, DPI scaling, and screenshots.
- Alt+Tab no longer requires the monitor to resynchronize with a different display mode.

## Installation and use

1. Download and extract the complete build.
2. Run `DDNet.exe`.
3. Open the graphics settings, select `Fullscreen`, and choose a 4:3 resolution such as `1280x960` or `1440x1080`.
4. Keep the `data` directory and all DLL files next to the executable.

## Who this build is for

This build is intended for Windows players using a 16:9 or 16:10 monitor with a stretched 4:3 resolution who experience a black screen, monitor flicker, or a delay when using Alt+Tab. If you use your monitor's native resolution and do not have this problem, you do not need this modification.

The game renders at the physical desktop resolution, so GPU usage may be higher than with a true exclusive `1280x960` display mode.

## Technical overview

On Windows, fullscreen mode 1 uses a desktop-sized borderless window instead of changing the system display mode. The configured 4:3 resolution is retained as a virtual aspect ratio while the real drawable size remains equal to the desktop resolution. This keeps rendering, clipping, mouse input, DPI scaling, and screenshots consistent while eliminating the display-mode transition during Alt+Tab.

## Origin and license

This is an unofficial modified build based on TClient/DDNet and is not an official release. Original copyright notices and distribution terms are preserved in `license.txt`. Notices for the bundled third-party libraries are included in the `licenses` directory.
