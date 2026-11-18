# Onknight Launcher

<img src="docs/icon-512.png" width="160" alt="Onknight Launcher icon">

A lightweight custom home screen for Android TV, built for a Sony Bravia but written to run on any Android TV. Weather with icons, system stats, clock, a favourites row and an all-apps grid over your own wallpaper.

## Features
- **Your wallpaper:** use the built-in artwork or pick your own with the built-in folder browser (internal storage, USB drives, SD cards).
- **Weather:** location detected automatically (or set your city), Celsius or Fahrenheit by country, 5-day forecast with drawn icons.
- **Your own favourites:** on first run you tick the apps you want, and they become Row 1. Change them any time from Menu > Choose my favourites (up to 9).
- **One Menu button:** All apps, Settings, and Add/Remove an app row.
- **Up to 3 app rows:** Row 1 holds your favourites and the Menu button. Extra rows sit beneath it and fill with the apps you use most.
- **Smart ordering:** favourites sort by how often you launch them, re-sorted only when you come back to the launcher. Can be turned off or reset.
- **Tile size:** Auto-fit, Compact, Standard or Large. Tiles also scale with the number of rows and your screen width.
- **Remembers where you were:** focus is restored to your last tile, and Home closes the grid and menus and returns you to the home row.

## Download
Grab the latest APK from the [Releases](../../releases) page and sideload it onto your Android TV.

## Setting it as your default home screen
Android does not let an app make itself the default launcher. If the Home button keeps opening the stock screen, use a tool such as TVBoxTools to set this launcher as the default and disable the others.

## Choosing a wallpaper
Menu > Settings > Wallpaper: choose my own. The first time, allow the storage permission. Pick internal storage or a USB drive, browse to a picture (jpg, png, webp, bmp) and select it. Back goes up one folder. The image is scaled down and saved inside the launcher, so the original can be removed afterwards.

## Location and units
On first run the launcher asks an IP lookup service (ipapi.co) for your rough city and country, then fetches weather from Open-Meteo. If it is wrong (a VPN, for example), open Settings and choose "Set my city". The clock follows the TV's own time zone.

## Version history
- **1.2** - Choose your own favourite apps for Row 1 (first-run picker, plus Menu and Settings entries). The built-in preset list is now only a fallback until you choose.
- **1.0** - First full release. Extra rows now go beneath Row 1, and Row 1 holds only your favourites plus Menu. Tile size setting (Auto-fit, Compact, Standard, Large) and automatic scaling by row count and screen width.
- **0.7** - One Menu button replaces All apps and Settings; Add/Remove an app row from the Menu.
- **0.6** - 1 to 3 favourite rows and usage-based ordering.
- **0.5.1** - Focus memory and Home button handling.
- **0.5** - Custom app icon and Android TV banner.
- **0.4** - Weather icons and built-in folder browser.
- **0.3** - Automatic location and units, manual city override.
- **0.2** - Wallpaper picker and first-run prompt.
- **0.1** - Original launcher.

## Editing
The preset favourites list at the top of MainActivity.java is only used until you choose your own on the TV. Build with Android Studio (Build > Build APK).
