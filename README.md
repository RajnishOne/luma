[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-EA4AAA?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sponsors/RajnishOne)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-F16061?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/rajnishone)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/bluematterdev?utm_medium=unknown&utm_source=join_link&utm_campaign=creatorshare_creator&utm_content=copyLink)
[![Downloads](https://img.shields.io/github/downloads/RajnishOne/luna/total?style=for-the-badge)](https://github.com/RajnishOne/luna/releases)
[![Package](https://img.shields.io/badge/Package-com.player.rjnsdev.luna-blue?style=for-the-badge)](https://github.com/RajnishOne/luna)

---

# Luna

**Luna** is a modern, open-source media library and video player for Android. It scans your local video files, fetches rich metadata (posters, descriptions, genres, ratings...) from [The Movie Database (TMDB)](https://www.themoviedb.org/), and organizes everything into a clean, beautiful browsable library. **Completely free, ad-free, and tracker-free.**

> **Platform status:** Luna currently runs on **Android**. The shared module is structured with Kotlin Multiplatform (KMP), with potential Desktop and iOS support in the roadmap.

---

## Features

- 📂 **Local library** - Browse your movies, TV shows, and anime in one place
- 🎬 **TMDB metadata sync** - Automatic posters, descriptions, genres, and ratings
- ▶️ **Built-in player** - Smooth playback with persistent progress history
- ▶️ **External player support** - Launch external players if preferred
- 🆓 **Truly free** - No ads, no trackers, no account required
- 📦 **F-Droid & Play Store ready** - Fully FOSS build with no proprietary dependencies

---

## Tech Stack

| Category | Library / Tool |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose · Material 3 Expressive |
| Architecture | MVI + Clean Architecture + KMP |
| Networking | Ktor · kotlinx.serialization |
| Dependency Injection | Koin |
| Database | Room · DataStore |
| Video Player | Media3 / ExoPlayer |
| Image Loading | Coil |
| Crash Reporting | ACRA (FOSS) · Firebase Crashlytics (Play Store) |
| Metadata API | TMDB |
| Testing | Kotest · MockK · Turbine |

---

## Build Flavors

Luna uses a `distribution` flavor dimension to produce two distinct variants:

| Flavor | Distribution | Crash Reporting |
|---|---|---|
| `foss` *(default)* | F-Droid | ACRA (open-source) |
| `playstore` | Google Play | Firebase Crashlytics + Analytics |

The `foss` flavor automatically disables all Google Services and Firebase tasks at build time, making it fully reproducible and compatible with F-Droid's build server requirements.

---

## File Naming Conventions

Luna uses your file names to identify and match content against TMDB. Follow the conventions below for best results.

### Movies

Include the title and, optionally, the release year:

```
Spider-Man (2002).mkv
Your Name.avi
Spider-Man.No.Way.Home.(2021).mp4
```

### TV Shows

Include the season and episode numbers in any of the supported formats:

```
show_name_s01e02.mkv
show_name_s01.e02.mkv
show_name_1x02.mkv
show_name (1995)_s01e02.mkv

# Folder-based naming is also supported:
show name/s01e02.mkv
show name/Season 1/02.mkv
```

---

## Configuration (`local.properties`)

To enable TMDB metadata synchronization in debug/local builds, add your TMDB API read access token in `local.properties`:

```properties
tmdb_token=YOUR_TMDB_ACCESS_TOKEN
```

---

## License

[![GPL-3.0-or-later](https://img.shields.io/badge/License-GPL--3.0--or--later-blue.svg)](https://spdx.org/licenses/GPL-3.0-or-later.html)

- Copyright (C) 2026 the-mskd-dev
- Copyright (C) 2026 Rajnish Sharma ([RajnishOne](https://github.com/RajnishOne))

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

See the full license in the [LICENSE](LICENSE) file.
