# Folder Sync – Local Browser App

A lightweight, privacy-first folder synchronization tool that runs entirely in your browser. No servers, no uploads — everything happens on your device using the File System Access API.

**Version:** FINAL (June 2026 build)  
**Author:** Custom build for Christopher Azeem  
**Tested on:** Chrome 125+, Edge 125+ (Windows 10/11 with LongPaths enabled)

---

## What it does

- Compare two local folders (A and B)
- Preview changes with a Dry Run
- Sync in multiple modes:
  - **A → B (copy)** – add/update only
  - **A → B (mirror)** – make B identical to A (deletes extras)
  - **B → A (copy / mirror)**
  - **Two-way Merge** – keep everything both ways
  - **Two-way Mirror** – keep only common files
- Handles 15,000+ files and 80+ subfolders without freezing
- Skips Windows long paths (>240 chars) safely
- Shows live progress: `847/15000 — COPY — …path/to/file.jpg`
- Pause, Resume, and Cancel mid-sync

---

## How to use

1. **Open the HTML file** in Chrome or Edge (double-click `Updating-script-template-FINAL.html`)
2. **Create a Relationship** (name it, pick mode, add excludes like `.DS_Store, Thumbs.db, *.tmp`)
3. **Pick Folder A and Folder B** – you must re-pick them each session (browser security). Chrome will remember the last location.
4. Click **Dry Run** – review the table
5. Click **Sync Now** – use Pause/Cancel if needed

Relationships are saved in your browser's localStorage only.

---

## Important notes

- **Folders must be re-picked each session — browser security.** This is a limitation of the File System Access API, not a bug.
- For large libraries, create relationships per batch of 15–20 subfolders for best UI speed.
- Enable Windows Long Paths if you work with deep folders:
  - Run `regedit` → `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem` → set `LongPathsEnabled` = 1

---

## Disclaimer – I have used this app myself. And I am delighted about it. 

This app is provided as-is. It has been tested and is working on the author's machine with large photo and ,edia libraries, but:

- Test on a small copy of your data before trusting it with important files.
Dry run is compulsary in the app befor eyou could sync. 

By using this tool, you accept full responsibility for your files.
//


---

## Features in this build

- Lazy file handles (low memory for 15k+ files)
- Long-path skip with console warning
- Per-file progress bar with action type
- Pause / Resume / Cancel controls
- Excludes support with wildcards (*.tmp)
- Local-only operation – nothing leaves your PC

Enjoy, and sync safely!
