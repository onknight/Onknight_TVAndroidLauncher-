# About Onknight Launcher

**Onknight Launcher** is a lightweight custom home screen for Android TV. I built it for my Sony Bravia X85J, which runs Android TV 12 and was slow and cluttered out of the box, though it is written to run on any Android TV. It displays weather with icons, live system stats, a clock, a row of favourite apps, and a full all-apps grid—all set over a custom wallpaper of your choice.

## Why I Built It

My TV was sluggish, and the stock home screen was filled with recommendations and ads. After debloating the TV, I wanted a home screen that was fast, clean, and personalized. Instead of tweaking an existing launcher, I decided to write a small native one from scratch. The goal was a lean application: **no ads, no accounts, no background services**, and minimal memory usage on a TV with only about 2.8 GB of RAM.

## Features

* **Your Own Wallpaper:** Use the built-in Onknight Studios artwork, or pick your own image using the built-in folder browser. It reads internal storage, USB drives, and SD cards, automatically scaling pictures down so they don't waste memory or storage.
* **Weather with Icons:** Automatically detects your location from your internet connection, with a manual *"Set my city"* option. Displays current conditions and a five-day forecast using icons drawn directly in code, showing Celsius or Fahrenheit depending on your country.
* **System Stats:** Displays live memory usage, free storage, and network speed directly on the home screen.
* **Clock and Date:** Automatically follows your TV's system time zone.
* **One Menu Button:** Opens a clean, scrolling list containing *All apps*, *Settings*, and *Add/Remove an app row*.
* **Up to Three App Rows:** Row 1 holds your favourites and the Menu button. Extra rows sit beneath it and automatically populate with your most-used apps.
* **Smart Ordering:** Favourites sort based on how often you launch them. Re-sorting only happens when you return to the launcher—never while you are actively navigating—so tiles never jump around under your remote cursor. You can disable this or reset launch counts at any time.
* **Customizable Tile Sizes:** Choose between *Auto-fit*, *Compact*, *Standard*, or *Large*. Tiles also scale dynamically based on the number of active rows and your screen width.
* **Focus Memory:** Remembers where you left off. Focus returns to your last selected tile even if the TV restarts the launcher, and pressing the **Home** button closes grids/menus and returns you straight to the home row.

## How It Was Built

The launcher is a native Android app written in Java inside a single `MainActivity.java` file of roughly 1,000 lines, using **zero third-party libraries**. The entire user interface is constructed programmatically in code rather than XML layout files, keeping the project footprint tiny and the APK lightweight. Weather data is fetched from the free [Open-Meteo](https://open-meteo.com/) API, and approximate location comes from an [ipapi.co](https://ipapi.co/) lookup—neither requires an API key.

I built it iteratively alongside Claude (Anthropic's AI assistant), working through each version step by step. I described the features I wanted and tested every build directly on my Sony TV while Claude wrote and revised the code. Along the way, I also made direct edits to the source code—including designing the layout where Row 1 remains anchored at the top with extra rows underneath, as well as the automatic tile scaling logic—assigning a new version number to each milestone.

## Version History

* **1.0** – First full release. Row 1 holds only favourites plus the Menu button, extra rows sit beneath it, and tiles scale dynamically by row count and screen width with a dedicated *Tile size* setting.
* **0.7** – Consolidated *All apps* and *Settings* into a single *Menu* button, adding options to add or remove an app row.
* **0.6** – Added support for one to three favourite rows and usage-based smart ordering.
* **0.5.1** – Added focus memory and improved **Home** button handling.
* **0.5** – Added custom app icon and Android TV home screen banner.
* **0.4** – Added code-drawn weather icons and the built-in folder browser.
* **0.3** – Added automatic location and temperature units, plus a manual city override.
* **0.2** – Added custom wallpaper picker and first-run setup prompt.
* **0.1** – Initial launcher release featuring the built-in default wallpaper.

## Installation

1. Download the latest APK from the **Releases** page and sideload it onto your Android TV.
2. Open the app once. A first-run prompt will ask whether you want to use the default wallpaper or choose your own.
3. Because Android does not allow an app to set itself as the default home screen, use a utility such as **TVBoxTools** (or ADB) to set **Onknight Launcher** as your default launcher and disable the stock home screen if pressing the **Home** button reverts to the stock UI.

## Building from Source

1. Open the project folder in **Android Studio**.
2. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)** from the top menu.
3. *(Optional)* To customize your default favourites before compiling, edit the app list at the top of `MainActivity.java`—apps are matched by the display name shown on your TV.

## Privacy

Onknight Launcher contains **no accounts, no ads, and no analytics**. The only network requests made by the app are the weather forecast lookup and a one-time IP location lookup. All launch counts, custom wallpapers, and settings are stored strictly locally on your TV.

## License

Released under the **MIT License**. See the `LICENSE` file in this repository for full details.

## Credits

* Built by **Tom** of **Onknight Studios**, with AI assistance on portions of the code.
* Weather data provided by [Open-Meteo](https://open-meteo.com/).
