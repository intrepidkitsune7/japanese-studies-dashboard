# 🇯🇵 Japanese Studies Dashboard

A personal Japanese learning tracker built as a single HTML file. No account, no server, no tracking. Everything saves privately on your own device.

Track your WaniKani progress, reading and listening streaks, books, and study diary — all in one dark-themed dashboard.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [WaniKani Sync](#wanikani-sync)
3. [Reading & Listening Streaks](#reading--listening-streaks)
4. [Currently Reading](#currently-reading)
5. [Books Read](#books-read)
6. [Study Diary](#study-diary)
7. [WaniKani Stats](#wanikani-stats)
8. [Your Data](#your-data)
9. [Sharing with Others](#sharing-with-others)

---

## Getting Started

### Option A — Browser (simplest)

1. Download `index.html` from this repository
2. Double-click the file — it opens in Chrome, Safari, or Firefox
3. Bookmark it for easy access

Everything works immediately with no setup.

### Option B — Obsidian

1. Drop `index.html` into your Obsidian vault folder
2. In Obsidian go to **Settings → Community Plugins → Browse**
3. Search for **Surfing**, install it and enable it
4. Press **Cmd+P** (Mac) or **Ctrl+P** (Windows)
5. Type **Surfing open** and select **"Surfing: Open URL in new Surfing Tab"**
6. In the address bar type `file://` followed by the full path to the file, for example:
   ```
   file:///Users/yourname/Documents/MyVault/index.html
   ```
7. Press Enter — the dashboard opens as a tab inside Obsidian

**Finding your file path on Mac:** Hold **Option** and right-click the file in Finder → **Copy as Pathname**, then add `file://` at the start.

### Option C — GitHub Pages (shareable link)

1. Fork this repository
2. Go to **Settings → Pages**
3. Under **Branch**, select `main` and keep the folder as `/ (root)`
4. Click **Save** — your dashboard will be live at `https://yourusername.github.io/repository-name` within a minute

Each person who opens the link gets their own completely independent copy. Data never mixes between users.

---

## WaniKani Sync

The sync bar at the top connects the dashboard to your WaniKani account.

**To connect:**

1. Go to [wanikani.com](https://wanikani.com) and log in
2. Click your profile picture → **Settings → Personal Access Tokens**
3. Click **Generate a new token**, give it any name, read-only permissions are fine
4. Copy the token
5. Paste it into the **WaniKani API Key** field in the dashboard
6. Click **⚡ Sync WaniKani**

Your API key is saved locally and reloads automatically — you only need to paste it once. Sync takes 10–30 seconds. Click the button any time to refresh your stats.

---

## Reading & Listening Streaks

Two separate cards track your daily reading and listening habits across the full year.

### Logging a day

Click any cell in the heatmap to mark it as done — amber for reading, indigo for listening. Click again to unmark it. Today's cell has a white outline border.

### Yearly heatmap

Each card shows a full GitHub-style heatmap of the entire year, with month labels across the top and Mon / Wed / Fri labels on the left. Navigate to previous years using the **‹** and **›** arrows — only years with logged data appear.

### Yearly summary

Each card shows **X / Y days this year** — how many days you logged out of how many days have elapsed so far. For past years, Y is the full 365 (or 366 for leap years).

### Weekly goal

Set a target number of days per week using the **Goal** input on each card. A progress bar fills as you tick off days during the week and resets each Monday.

### Streak count

Your current streak and all-time best are shown at the top of each card. Missing a day resets the current streak to zero.

---

## Currently Reading

A horizontal scrollable shelf of books you are currently reading.

### Adding a book

Click **+ Add book** to open the modal.

- **Title** — type the title, or leave blank and use Look up to auto-fill it
- **Cover Image** — two options:
  - Type an ISBN (e.g. `9784088745466`) or ASIN (e.g. `B00FXZP3LA`) and click **Look up** — the title and total page count fill in automatically
  - Click **📁 Upload image from computer** to pick an image from your device — this is the most reliable method and stores the image locally so it always displays
- **Type** — Manga, Novel, Light Novel, Non-fiction, or Children's Book
- **Difficulty** — 1 (Very Easy) to 5 (Very Hard)
- **Progress** — current page and total pages (auto-filled on ISBN lookup)
- **Start Date** — defaults to today, change it to whenever you actually started

### Progress bar

If you enter a total page count, a purple progress bar appears along the bottom of the cover image with a percentage badge, plus a page counter and days-reading count below the title.

### Editing a book

Click anywhere on a book card (not the Finished button) to open the edit modal and update any field, including your current page to track progress.

### Finishing a book

Click **✓ Finished**. The book moves automatically to the Books Read ribbon with today's date recorded as the finish date, and the number of days it took is calculated from your start date.

### A note on covers

Obsidian blocks loading images from external websites. The most reliable method is:

1. Find the book on Amazon or the publisher's site
2. Right-click the cover image → **Save Image**
3. In the Add or Edit modal, click **📁 Upload image from computer**
4. Select the saved image

The image is stored locally and always displays correctly, even offline. ISBNs still auto-fill the title and page count even if the cover does not load.

---

## Books Read

A scrollable ribbon of all the books you have finished, organised by year.

Click the year tabs to switch between years. Each book shows its finish date and how many days it took to read. Books are added here automatically when you tap **✓ Finished**.

---

## Study Diary

A compact calendar sits next to the Currently Reading section. Dates with notes are highlighted in purple with a dot.

### Writing a note

Click any date to open the full-page note editor. Write freeform notes — what you studied, new vocabulary, grammar points, how the session felt.

To embed a YouTube video or image, paste a URL into the **Embed URL** field and click **+ Add**. YouTube links convert to embedded players automatically.

Click **Save** to save and return, **← Back** to go back without saving, or **Delete** to remove a note entirely. Press **Escape** at any time to close.

### Searching notes

Click the **🔍 Search** button on the diary card to search all your notes. Results appear instantly as you type, with highlighted matching snippets. Click any result to jump directly to that date.

---

## WaniKani Stats

Three cards at the bottom show your WaniKani data after syncing.

**WaniKani** — current level, reviews available right now, and lessons available right now. Last synced time shown at the bottom.

**SRS Breakdown** — items at each stage: Apprentice, Guru, Master, Enlightened, and Burned.

**WK Kanji Progress** — a circular ring showing what percentage of WaniKani's 2,027 kanji you have at Guru level or above. Shows known, remaining, and total counts with a progress bar.

---

## Your Data

**Where it is stored** — everything saves in your browser's local storage. It stays on your device and is never sent anywhere.

**Each person's data is independent** — anyone you share this with gets a blank dashboard. Your data and theirs never mix.

**Backup** — your data is tied to the browser and device you use. Clearing browser data or switching devices will lose your data. Use the dashboard consistently on the same device to avoid this.

**Resetting** — click the **✏️** button (bottom right) to open the manual override panel, scroll to the bottom, and click **⚠️ Reset All Data**. This cannot be undone.

**Manual override** — the ✏️ panel also lets you set WaniKani stats manually if you prefer not to use the API sync.

---

## Sharing with Others

Because all data is stored locally per device, you can share `index.html` freely. Anyone who opens it gets a blank dashboard with no connection to your data.

The easiest ways to share:

- **Send the file directly** via email or message
- **GitHub Pages** — fork this repo, enable Pages, and share the URL
- **Netlify Drop** — drag the file to [app.netlify.com/drop](https://app.netlify.com/drop) and share the instant URL

---

*Built as a single HTML file. No server, no account, no tracking.*
