# 🇯🇵 Japanese Studies Dashboard

A single-file, offline-first dashboard for tracking your Japanese reading and listening immersion. No accounts, no servers, no build step — just one HTML file you open in your browser. All your data lives locally in your browser; nothing ever leaves your machine.

> Open `japanese-studies.html`, start logging, and watch a pixel fox cheer you on as your streak grows.

---

## 📑 Table of Contents

- [Features](#-features)
  - [Reading](#reading)
  - [Listening & watching](#listening--watching)
  - [Habit tracking](#habit-tracking)
  - [Motivation](#motivation)
  - [Reflection](#reflection)
  - [WaniKani integration](#wanikani-integration)
  - [Layout & data](#layout--data)
- [Getting started](#-getting-started)
  - [Optional: WaniKani sync](#optional-wanikani-sync)
- [Using it inside Obsidian (Surfing plugin)](#-using-it-inside-obsidian-surfing-plugin)
- [How your data works](#-how-your-data-works)
- [Privacy](#-privacy)
- [Technical notes](#️-technical-notes)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### Reading
- **Currently reading shelf** with cover art, page progress bars, and per-book reading sessions. Suspend and resume books mid-read.
- **Optional session timing** — log how long you read and the dashboard calculates a weighted "equivalent pages per hour" that accounts for the relative difficulty of manga, light novels, novels, and so on.
- **Finished books ribbon** grouped by year, with the time each book took to finish.
- **Favourites** — tap the heart on any finished book to mark it a favourite.
- **Wishlist** with drag-to-reorder priority, on both desktop and touch.
- **Reading goals** — set a yearly target and watch a progress bar fill toward it.

### Listening & watching
- **Season-aware show tracking.** Finish a season and choose to start the next one, mark the show as waiting for a future season, or finish it entirely. Each completed season appears individually in the finished ribbon with its own tag.
- Stats correctly distinguish **shows finished** (fully complete) from **seasons watched**.

### Habit tracking
- **Combined reading + listening heatmap** — a GitHub-style calendar where amber marks reading days, indigo marks listening days, and green marks both. Hover any day for a rich tooltip showing what you read (with page ranges), whether you listened, and a preview of that day's diary entry. Hover a month label to highlight just that month.
- **Streak counters** for reading and listening, with all-time bests.
- **Milestone celebrations** at streak and book-count thresholds.

### Motivation
- **Road to Fluency bar** with a pixel fox that reacts to your streak:
  - 😴 **Sleeping** — nothing logged today
  - 🏃 **Running** — 1–6 day streak
  - ⭐ **Happy** — 7–29 day streak
  - 🔥 **On fire** — 30+ day streak
- **Reading Bingo** — a yearly 5×5 card with auto-detected and manually-ticked squares. Fully customisable: rename squares, hide ones you don't want, and add your own.

### Reflection
- **Study diary** — a notebook view of dated entries, newest first, grouped by month, with tags and full-text search.
- **Year in Review** — a generated, downloadable PNG poster summarising your year: books, pages, hours, reading and listening days, shows, seasons, your reading goal, your favourites, and a grid of every book you finished. Generate it for any year at any time. On **January 1st**, the previous year's review automatically pops up.

### WaniKani integration
- Optional sync with the [WaniKani](https://www.wanikani.com/) API to pull in your level, available reviews and lessons, SRS stage breakdown, and kanji progress.

### Layout & data
- **Modular panels** — every section is a draggable, hideable panel. Arrange your dashboard however you like; the layout persists.
- **Dark and light themes.**
- **Export / import** your data as a JSON backup, plus a recovery tool for restoring data from an older version of the file.

---

## 🚀 Getting started

1. Download `japanese-studies.html`.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. Start adding books, shows, and diary entries.

That's it. There's no installation, no dependencies to fetch, and no internet connection required (except for optional WaniKani sync and fetching cover images).

### Optional: WaniKani sync
1. Get a personal access token from your [WaniKani API settings](https://www.wanikani.com/settings/personal_access_tokens).
2. Paste it into the WaniKani panel and click sync.

---

## 📓 Using it inside Obsidian (Surfing plugin)

If you keep your study notes in [Obsidian](https://obsidian.md/), you can open the dashboard right inside your vault using the [Surfing](https://github.com/PKM-er/Obsidian-Surfing) community plugin, which adds a built-in web browser to Obsidian. This keeps your tracker and your notes in one place.

### One-time setup

1. **Install Surfing.** In Obsidian, go to **Settings → Community plugins → Browse**, search for **Surfing**, install it, and enable it. (You may need to turn off Restricted Mode first.)
2. **Put the dashboard in your vault.** Copy `japanese-studies.html` into a folder inside your Obsidian vault — for example `Japanese dashboard/japanese-studies.html`. Keeping it inside the vault means the file path stays stable, which matters for your data (see below).
3. **Open it in Surfing.** Open the Surfing browser (command palette → **Surfing: Open current URL with Surfing** or the ribbon icon), then navigate to the file using a `file://` URL pointing at the HTML, e.g.:
   ```
   file:///Users/you/Documents/MyVault/Japanese dashboard/japanese-studies.html
   ```
   On Windows the path looks like `file:///C:/Users/you/...`.
4. **Bookmark / pin it.** Use Surfing's bookmark feature, or pin the tab, so it's one click away each time you open Obsidian.

### Tips

- **Keep the file path stable.** Your data is stored by the browser against the exact file path. If you move or rename the file (or the vault folder), the dashboard will look empty because the browser treats the new path as a new site. Your data isn't lost — move the file back, or restore from an export. Decide on a location once and leave it there.
- **Back up before reorganising your vault.** Before moving folders around, use **Settings → Export** in the dashboard to save a JSON backup, then **Import** it after if needed.
- **Pin the tab** so an accidental close doesn't lose your place.
- The dashboard behaves the same inside Surfing as in a normal browser — themes, WaniKani sync, and all panels work identically.

> Plugin menus and option names can change between Surfing versions; if something is named slightly differently, look for the equivalent "open URL" or "bookmark" action.

---

## 💾 How your data works

All data is stored in your browser's `localStorage` under the key `jp-v10`. This means:

- **Your data never leaves your computer.** There is no server and no telemetry.
- **The HTML file itself contains no personal data** — you can safely share the file with others, and they'll get a clean, empty dashboard.
- **Data is tied to the file's exact location.** Because browsers scope `localStorage` for local files to the full file path, renaming or moving the file makes the browser treat it as a new origin, and your data will appear to be gone. It isn't deleted — keep the file at a stable path, or use **Settings → Recover** to restore it.
- **Back up regularly.** Use **Settings → Export** to save a JSON backup, especially before moving the file or switching devices.

---

## 🔒 Privacy

- No accounts, no tracking, no analytics.
- The only outbound network requests are:
  - WaniKani API calls, if you choose to sync (sends only your API token to WaniKani).
  - Loading book/show cover images from URLs you provide.
- Everything else is fully local.

---

## 🛠️ Technical notes

- **Single file.** All HTML, CSS, and JavaScript live in `japanese-studies.html`. No frameworks, no build tooling.
- **Vanilla JavaScript.** The only external dependency is Chart.js, loaded from a CDN for the optional yearly-review charts.
- **Canvas rendering** is used for the pixel fox and the Year in Review poster.
- Works offline once loaded.

---

## 🤝 Contributing

This is a personal-style project shared for others to use and adapt. Feel free to fork it, customise the bingo squares, tweak the fox, change the colour scheme, or add panels of your own. Because it's a single file with no build step, editing is as simple as opening the HTML in a text editor.

---

## 📄 License

Released under the MIT License — free to use, modify, and share.

---

*Happy reading! 📖 頑張って！*
