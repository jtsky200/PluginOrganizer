# Plugin Organizer

A Windows GUI tool for automatically scanning, categorizing, and organizing your FL Studio `.fst` preset files into standardized ALL-CAPS category folders, with backup, nesting, and auto-update support.

---

## 🚀 Features

- **Phase 1: Scan**  
  Recursively walks your selected plugin-presets root and locates every `.fst` file.

- **Phase 2: Categorize**  
  Uses keyword matching (folder names & file names) plus optional online DuckDuckGo lookups to assign each preset to one of your ALL-CAPS categories (e.g. `REVERB`, `EQ`, `SYNTH`, etc.).

- **Phase 3: Backup**  
  Moves any uncategorized folders into a `BACKUP` directory.

- **Phase 4: Nesting**  
  Within each category folder, further sorts presets into subcategories (e.g. `VOCAL/PITCH`, `SYNTH/FM`, etc.) based on keywords or online lookup.

- **Empty-Folder Cleanup**  
  Automatically removes any leftover empty directories in both your main root and `BACKUP`.

- **Real-Time Watch Mode**  
  Optionally watch your presets folder—newly added `.fst` files are processed immediately.

- **Category Editor**  
  GUI dialog to add, remove, or adjust keyword lists for both Effects and Generators categories.

- **Auto-Update**  
  Built-in “Check for Updates…” that fetches a public `update.json` and prompts you to download the latest installer.

---

## ⚙️ Installation

1. Download & run the latest [PluginOrganizerSetup-v2.15.exe](https://github.com/jtsky200/PluginOrganizer/releases/download/v2.15/PluginOrganizerSetup-v2.15.exe).  
2. Launch **Plugin Organizer** from your Start menu or desktop shortcut.
3. Use **Edit → Edit Categories…** to tweak any keyword mappings before your first run, if desired.

---

## 📋 Usage

1. **Choose Plugin Folder…**  
   Select your FL Studio Plugin Database root (e.g. `…\FL Studio\Presets\Plugin database\Effects` or `Generators`).

2. **Start Scan**  
   Runs Phases 1–4 in sequence, displaying progress, current folder, and log messages.

3. **Nest Only / Process Backup / Force Hunt**  
   Individual buttons to re-run only nesting, only backup cleanup, or a full Force Hunt (re-run all phases).

4. **Watch Mode**  
   Start/Stop a background watch that auto-processes any new `.fst` files as you add them.

5. **Show Counts / Verify**  
   Quickly view how many presets were moved per category, or verify that no stray `.fst` remain outside your category folders.

---

## 📖 Change Log

### v2.15 (2025-07-14)
- 🔄 **Auto-Update Integration**  
  • Connected to public `update.json` in **dist** repo  
  • “Check for Updates…” now reliably fetches and parses version 2.15 manifest  
  • Fixed 404 issues by aligning raw URL and release assets  

- 🧹 **Nested Cleanup Improvements**  
  • Enhanced Phase 4 to prevent duplicate sub-folders  
  • Better handling of existing nested presets (e.g. `VOCAL/pitch` → moved correctly)  
  • Fixed hanging on nested-cleanup step by adding UI updates in loop  

- 🔍 **Backup Processing**  
  • New “Process Backup” button to scan & categorize leftover `.fst` inside `BACKUP`  
  • Empty-folder cleanup now runs on both main root and `BACKUP`  

- ⚙️ **Installer & Inno Setup**  
  • Updated Inno Script (`PluginOrganizer.iss`) to omit `plugin_cache.json`  
  • Installer repackaged as `PluginOrganizerSetup-v2.15.exe`  
  • `update.json` now points to the public GitHub Releases URL  

- 🐛 **Bug Fixes**  
  • Ensured all sub-folders in `dist` are scanned, not just top-level  
  • Fixed watcher crash when `watchdog` not installed  
  • Improved thread-safety during scanning & moving  


