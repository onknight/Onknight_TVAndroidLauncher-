# Onknight Launcher

A lean custom home screen for Android TV: weather with icons, system stats, clock, a favourites row and an all-apps grid over your own wallpaper.

## Version history
- **0.4** - Weather now uses drawn icons (current conditions and a 5-day forecast row). Built-in folder browser for choosing a wallpaper (internal storage, USB drives and SD cards), so no separate file manager app is needed.
- **0.3** - Automatic location and Celsius/Fahrenheit, manual "Set my city" override, wider weather panel, dock raised off the logo, Settings tile.
- **0.2** - First-run prompt (use default wallpaper or choose your own), wallpaper change/reset, picked images are scaled and compressed before saving.
- **0.1** - Original launcher with the built-in Onknight Studios wallpaper.

## Setting it as your default home screen
Android does not let an app make itself the default launcher. If the Home button keeps opening the stock screen, use a tool such as TVBoxTools to set this launcher as the default and disable the others.

## Choosing a wallpaper
Settings > Wallpaper: choose my own. The first time, allow the storage permission. Pick internal storage or a USB drive, browse to a picture (jpg, png, webp, bmp) and select it. Back goes up one folder. The image is scaled down and saved inside the launcher, so the original can be removed afterwards.

## Location and units
On first run the launcher asks an IP lookup service (ipapi.co) for your rough city and country, then fetches weather from Open-Meteo. If it is wrong (a VPN, for example), open Settings and choose "Set my city". The clock follows the TV's own time zone.

## Editing
Favourite apps are at the top of MainActivity.java. Build with Android Studio (Build > Build APK).
