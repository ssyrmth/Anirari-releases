# Anirari

Your anime folders as a library: covers, seasons and episode lists from AniList, what's next to watch, playback in mpv, and your AniList
list kept up to date as you watch. It runs on your own PC, in its own window.

**[Download the latest version](../../releases/latest)** · Windows 10 and 11 · free

This repository holds the releases; what changed in each version is in its [release notes](../../releases).

## What it does

- **Your library, matched on AniList.** Anirari finds the shows in your folders and matches them on AniList: covers, banners, seasons,
  split cours, movies, specials and airing times. A wrong match is one search away (**Fix match**).
- **What to watch next.** Continue watching (with how far you got), Up next (your own shortlist), new-episode and airing badges, a banner
  with the shows you are watching, grid or list view, filters and sorting, and a library overview (missing episodes, disk space per show).
- **Search everything with Ctrl+K**: shows, actions and settings, from anywhere.
- **Episode windows**: every episode with a thumbnail and its file details (resolution, audio and subtitle languages), the next one to
  watch highlighted, other versions of an episode grouped under it, and the episodes you don't have yet listed with when they air.
- **Plays in mpv**, resumes where you stopped, plays the next episode by itself if you like, skips openings and endings (it finds them by
  listening to the episodes), and marks the episode watched on AniList when you reach the credits.
- **Your AniList list in step**: progress, status and score. Changes made while you are offline are kept and sent once AniList can be
  reached, and every change can be undone.
- **Make it yours**: 10 themes, a theme builder (poster colours, ambient glow, background gradients), your own CSS, card sizes, Reduce
  motion, optional sound effects.
- Optional: **Discord** status, **Windows notifications** for new episodes, your **friends' activity** from AniList.
- **Backups** of everything that matters (settings, match fixes, resume points, watch history, Up next) - automatic, every week unless you
  choose otherwise - and a diagnostics page for when something is off.

## What you need

- **Windows 10 or 11.**
- **Microsoft Edge or Google Chrome** for the app's window (Edge comes with Windows). Without either, Anirari opens in your default browser.
- Recommended: **[mpv](https://mpv.io/installation/)** or **[mpv.net](https://github.com/mpvnet-player/mpv.net)** to play episodes. That is
  what lets Anirari follow how far you got, resume and mark episodes watched; without it, episodes open in your default video app.
- An **[AniList](https://anilist.co)** account to keep your list in step. Without one the library still works: covers and matching come
  from AniList's public data.
- ffmpeg comes with Anirari (thumbnails, file details, finding openings and endings).

## Install

- **Anirari-&lt;version&gt;-Setup.exe** (easiest) installs Anirari for you only - no administrator needed - into
  `%LOCALAPPDATA%\Programs\Anirari`, with a Start menu entry (a desktop shortcut and Start with Windows if you tick them) and an entry in
  **Settings › Apps** to uninstall it. Installing a new version over the old one keeps everything.
- **Anirari-&lt;version&gt;-portable.zip** is the same without installing: unzip it anywhere and run `Anirari.exe`.

Anirari is not code-signed, so Windows may warn about an unknown publisher the first time: **More info › Run anyway**.

On the first start, a short setup walks you through adding your anime folders, logging in with AniList and a few preferences, then scans
your library. Starting Anirari while it is already running brings its window to the front.

## Connecting AniList

Press **Log in with AniList** in the setup (or **Settings › Accounts & linking**), approve on AniList's page, and you come back logged in.
There is nothing to set up, as long as Anirari runs on its usual port, 8765.

On another port, or if you prefer, use an AniList API client of your own: create one at
[anilist.co/settings/developer](https://anilist.co/settings/developer) with the Redirect URL Anirari shows you
(`http://localhost:8765/callback` by default), paste its Client ID in **Settings › Accounts & linking** and press **Connect**.

Your login is stored encrypted for your Windows account.

## Everyday use

| | |
|---|---|
| **Ctrl+K** or **/** | Search shows, actions and settings |
| **?** | Every keyboard shortcut |
| **Refresh** | Look for new files and sync with AniList. Anirari never syncs by itself, unless you turn on **Sync with AniList when the app starts** |
| **Mark** / **Mark up to here** / **Unmark** | Change your AniList progress by hand (undo in the message that follows) |
| **Fix match** | When a show is matched to the wrong AniList entry |
| **Private mode** | Nothing is marked on AniList automatically, no Discord status, no watch history - until you turn it off |

While an opening or ending plays in mpv, press **Enter** to skip it - or let Anirari skip them by itself (**Settings › Playback**).

## Your data and privacy

Everything Anirari keeps is on your PC, in `%APPDATA%\Anirari` (**Settings › Data & storage › Data folder › Open**): settings, match fixes,
resume points, watch history, your encrypted AniList login, the library cache, thumbnails and covers, the log and backups.

What leaves your PC:

- **AniList**: searches to match your shows; your list, when you press Refresh (or at start, if you turned that on); the changes you make or
  Anirari makes for you (marks, status, score); friend activity, when you open it; covers and banners from AniList's image servers.
- **Discord**, only if you set it up: what you're watching, through the Discord app on your PC.
- **GitHub** (this page), only when you press **Check for updates** - or once a day, if you turn that on.
- Nothing else: no analytics, no telemetry.

Anirari's server listens only on your own PC (`127.0.0.1`), so websites you visit cannot use it. Backups and support bundles never contain
your AniList login, and a backup or settings file from someone else cannot change which programs Anirari runs unless you tick them.

## Updating

**Settings › About › Check for updates** looks here for a newer version and shows what is new, with a button to its download. Run the new
setup over the old one: everything you had stays.

## When something is wrong

| Problem | Try |
|---|---|
| AniList says the login expired | **Settings › Accounts & linking › Connect** again; **Diagnostics & logs › Check with AniList** tests it |
| A show is matched wrongly | **Fix match** in its episode window |
| No thumbnails or file details | **Settings › Data & storage › Diagnostics & logs** shows which ffmpeg is used; **ffmpeg program** sets another |
| Episodes open in the wrong player | **Settings › Playback › Play with** and **Player program** |
| Your own CSS hid something | **Ctrl+Alt+C** turns custom CSS off |
| "Another program is using port 8765" (Anki's AnkiConnect add-on uses it too) | Let Anirari use a free port when it asks, or pick one in **Settings › Data & storage › Port** |
| Anything else | **Settings › Data & storage › Diagnostics & logs**: the log, system details and **Download support bundle** (without your login) |

## Uninstalling

**Settings › Apps › Anirari › Uninstall** removes what the setup installed, its shortcuts and its Apps entry - and your settings and library
data in `%APPDATA%\Anirari` only if you choose to. The portable version: quit Anirari and delete its folder (and `%APPDATA%\Anirari` if you
won't come back).

## License notes

ffmpeg and ffprobe come with Anirari: FFmpeg 9.0.2, a build from [gyan.dev](https://www.gyan.dev/ffmpeg/builds/), licensed under the GNU
GPL v3 (`ffmpeg-LICENSE.txt` next to them). Its source code: <https://ffmpeg.org/releases/ffmpeg-9.0.2.tar.xz>.
