# 🇯🇵 Japanese Studies Dashboard — User Guide

A personal Japanese learning tracker built as a single HTML file. Tracks your WaniKani progress, reading and listening streaks, books, and study diary. Everything saves privately on your own device.

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

---

## Getting Started

You have three options for opening the dashboard.

### Option A — Browser (simplest)

Double-click the `index.html` file. It opens in Chrome, Safari, or Firefox and works immediately. Bookmark it so you can find it easily.

### Option B — Obsidian

1. Drop `index.html` into your Obsidian vault folder
2. In Obsidian go to **Settings → Community Plugins → Browse**
3. Search for **Surfing**, install it and enable it
4. Press **Cmd+P** (Mac) or **Ctrl+P** (Windows), type **Surfing open**, and select **"Surfing: Open URL in new Surfing Tab"**
5. In the address bar type `file://` followed by the full path to the file, for example:
   ```
   file:///Users/yourname/Documents/MyVault/index.html
   ```
6. Press Enter — the dashboard opens as a tab inside Obsidian

To find your exact file path on Mac: hold **Option** and right-click the file in Finder → **Copy as Pathname**.

### Option C — GitHub Pages (shareable link)

If the file is hosted on GitHub Pages, simply open the URL you were given in any browser.

---

## WaniKani Sync

The sync bar sits at the top of the page. It pulls your level, reviews, lessons, SRS counts, and kanji progress directly from WaniKani.

**To connect WaniKani:**

1. Go to [wanikani.com](https://wanikani.com) and log in
2. Click your profile picture → **Settings → Personal Access Tokens**
3. Click **Generate a new token** — give it any name, read-only permissions are fine
4. Copy the token
5. Paste it into the **WaniKani API Key** field in the dashboard
6. Click **⚡ Sync WaniKani**

Your API key is saved locally on your device so you only need to paste it once. Sync takes 10–30 seconds as it fetches your full assignment history. Click the button again any time you want to refresh your stats.

---

## Reading & Listening Streaks

The two streak cards at the top track your daily reading and listening habits.

**To log a day:**

Click any square in the habit grid to mark it as done. The square turns amber (reading) or indigo (listening). Click again to unmark it. Today's square has a white border.

**Weekly goal:**

Each card has a small **Goal** input in the top right. Set your target number of days per week (default is 5). A progress bar below your streak count fills up as you tick off days during the week.

**What the grid shows:**

The grid displays the last 10 weeks. Lighter squares are days you haven't logged yet. Greyed-out squares at the end are future dates.

---

## Currently Reading

A horizontal scrollable shelf of books you are currently reading.

### Adding a book

Click the **+ Add book** card to open the add modal.

- **Title** — type the title, or leave it blank and use Look up to fill it automatically
- **Type** — Manga, Novel, Light Novel, Non-fiction, or Children's Book
- **Cover Image** — you have two options:
  - Type an ISBN (e.g. `9784088745466`) or ASIN (e.g. `B00FXZP3LA`) and click **Look up** — the title and page count will fill in automatically, and the dashboard will attempt to load a cover
  - Click **📁 Upload image from computer** to pick an image from your device — this is the most reliable method and stores the image locally so it always displays
- **Difficulty** — rate it from 1 (Very Easy) to 5 (Very Hard)
- **Progress** — enter your current page and the total pages. Total pages are fetched automatically if you use Look up with an ISBN
- **Start Date** — defaults to today, change it to whenever you actually started

### Editing a book

Click anywhere on a book card (except the Finished button) to open the edit modal. You can update any field including your current page count to track progress.

### Progress bar

If you have entered a total page count, a purple progress bar appears along the bottom of the cover image with a percentage badge. Your current page and total are shown below the title.

### Finishing a book

Click the green **✓ Finished** button at the bottom of a book card. The book is automatically moved to the **Books Read** ribbon with today's date as the finish date. The number of days it took to read is calculated from your start date.

---

## Books Read

A scrollable ribbon showing all the books you have finished, organised by year.

Click the year tabs to switch between years. Each book shows its finish date and how many days it took to read. Books appear in the order they were finished.

Books are added here automatically when you click **✓ Finished** on a currently reading card.

---

## Study Diary

A compact calendar next to the Currently Reading section. Dates with notes are highlighted in purple with a dot.

### Writing a note

Click any date to open the full-page note editor. You can:

- Write freeform notes about what you studied, new vocabulary, grammar points, how a session felt
- Embed YouTube videos or images by pasting a URL into the **Embed URL** field and clicking **+ Add**

Click **Save** to save and return to the dashboard, or **← Back** to go back without saving. Click **Delete** to remove a note entirely.

---

## WaniKani Stats

Three cards at the bottom show your WaniKani data after syncing.

**WaniKani card** — shows your current level, reviews available right now, and lessons available right now. The last synced time is shown at the bottom.

**SRS Breakdown** — shows how many items are at each SRS stage: Apprentice, Guru, Master, Enlightened, and Burned.

**WK Kanji Progress** — a circular progress ring showing what percentage of WaniKani's 2,027 kanji you have at Guru level or above. This means you have seen them enough times to have a solid grasp. Shows known, remaining, and total counts with a progress bar.

---

## Your Data

**Where it is stored:** All your data — streaks, notes, books, WaniKani stats — is saved in your browser's local storage. It stays on your device and is never uploaded anywhere.

**Each person's data is independent:** If you share this dashboard with someone else, they get a completely blank copy. Your data and theirs never mix.

**Backing up your data:** Your data is tied to the browser and device you use. If you clear your browser data or switch devices, your data will be lost. To avoid this, periodically export your browser's local storage — or simply use the dashboard consistently on the same device.

**Resetting everything:** Click the **✏️** button in the bottom right to open the manual override panel. Scroll to the bottom and click **⚠️ Reset All Data** to wipe everything and start fresh. This cannot be undone.

**Manual override:** The ✏️ panel also lets you set your WaniKani stats manually if you prefer not to use the API sync.

---

## Cover Images

Because this dashboard runs as a local file, it cannot load images from most external websites due to browser security restrictions.

The most reliable way to add a cover is:

1. Go to the book's Amazon or publisher page
2. Right-click the cover image → **Save Image**
3. In the Add or Edit book modal, click **📁 Upload image from computer**
4. Select the saved image

The image is converted and stored locally, so it always displays correctly regardless of your internet connection.

The **Look up** button will attempt to load a cover automatically from OpenBD (best for Japanese books), Google Books, or Open Library. If the cover appears in the preview, it will be saved. If it does not appear, use the upload method instead.

---

*Built as a single HTML file. No server, no account, no tracking.*
