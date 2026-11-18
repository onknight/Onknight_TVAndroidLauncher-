# About Onknight Launcher

Onknight Launcher is a lightweight custom home screen for Android TV. I built it for my Sony Bravia X85J, which runs Android TV 12 and was slow and cluttered out of the box, but it is written to run on any Android TV. It shows weather with icons, system stats, a clock, a row of favourite apps and a full all-apps grid, all over a wallpaper of your choice.

## Why I built it

My TV was sluggish and the stock home screen was full of recommendations and ads. I debloated the TV first, then wanted a home screen that was fast, clean and looked like mine. Instead of tweaking an existing launcher, I decided to write a small native one. The goal was a lean app: no ads, no accounts, no background services, and as little memory use as possible on a TV with only about 2.8 GB of RAM.

## Features

- **Your own wallpaper.** Use the built-in Onknight Studios artwork, or pick your own with the built-in folder browser. It reads internal storage, USB drives and SD cards, and scales the picture down so it does not waste memory or storage.
- **Weather with icons.** The location is detected automatically from your internet connection, with a manual "Set my city" option. It shows current conditions and a five-day forecast, using icons drawn in code, in Celsius or Fahrenheit depending on your country.
- **System stats.** Live memory use, free storage and network speed on the home screen.
- **Clock and date** that follow the TV's own time zone.
- **One Menu button.** It opens a scrolling list with All apps, Settings, and Add or Remove an app row.
- **Up to three app rows.** Row 1 holds your favourites and the Menu button. Extra rows sit beneath it and fill with the apps you use most.
- **Smart ordering.** Favourites sort by how often you launch them. They are re-sorted only when you come back to the launcher, never while you are navigating, so tiles do not jump around under your remote. You can turn this off or reset the counts.
- **Tile size.** Auto-fit, Compact, Standard or Large. Tiles also scale automatically with the number of rows and your screen width.
- **Remembers where you were.** Focus returns to your last tile, even if the TV restarts the launcher, and pressing Home closes the grid and menus and returns you to the home row.

## How it was built

The launcher is a native Android app written in Java, in a single MainActivity file of roughly a thousand lines. It uses no third-party libraries. The interface is built in code instead of layout files, which keeps the project tiny and the APK small. Weather comes from the free Open-Meteo service, the approximate location from the ipapi.co lookup, and neither needs an API key.

I built it iteratively with Claude, Anthropic's AI assistant, working through the versions one at a time. I described what I wanted and tested every build on my own TV, and Claude wrote and revised the code. I also made my own edits to the code along the way, including the layout where Row 1 stays on top and extra rows go beneath it, and the automatic tile scaling. Each change got a version number.

## Version history

- **1.0** - First full release. Row 1 holds only your favourites plus Menu, extra rows go beneath it, and tiles scale by row count and screen width, with a Tile size setting.
- **0.7** - One Menu button replaces All apps and Settings, with Add and Remove an app row.
- **0.6** - One to three favourite rows and usage-based ordering.
- **0.5.1** - Focus memory and Home button handling.
- **0.5** - Custom app icon and Android TV banner.
- **0.4** - Weather icons and the built-in folder browser.
- **0.3** - Automatic location and units, with a manual city override.
- **0.2** - Wallpaper picker and a first-run prompt.
- **0.1** - The original launcher with the built-in wallpaper.

## Installing it

1. Download the latest APK from the Releases page and sideload it onto your Android TV.
2. Open it once. The first-run prompt asks whether to use the default wallpaper or choose your own.
3. Android does not let an app make itself the default home screen. If the Home button keeps opening the stock screen, use a tool such as TVBoxTools to set Onknight Launcher as the default and disable the others.

## Building it yourself

Open the project folder in Android Studio and choose Build, then Build APK. Your favourite apps are listed at the top of MainActivity.java, and they are matched by the name shown on your TV.

## Privacy

The launcher has no accounts, no ads and no analytics. The only network requests are the weather lookup and the one-time location lookup. Launch counts, your wallpaper and your settings are stored only on the TV.

## License

Released under the MIT license. See the LICENSE file in the repository.

## Credits

Built by Tom of Onknight Studios, with Claude from Anthropic. Weather data from Open-Meteo.
