# Changelog

What changed in each Vibe Files release, newest first. Each section is also the release's notes.

## 0.1.53 (2026-11-23)

- New: an installer, `vibe-files-setup-x64.exe`. It asks whether to install for you only (no
  administrator rights needed) or for everyone on the PC (asks for an administrator), adds a
  Start menu entry and an entry in Settings › Apps to uninstall. Upgrades keep your choice.
- An installed copy keeps each Windows login's catalog and settings in
  `%LOCALAPPDATA%\Vibe Files\data`. Installing, upgrading and uninstalling never touch them or
  your cabinet.
- The portable zip is still available and works as before.

## 0.1.52 (2026-11-23)

- Downloads move to this page, <https://github.com/KisaesDevLab/vibe-files-releases>. The
  update check in the app looks here.
- From this version Vibe Files is licensed under the VibeMyFirm Community License 1.0
  (LICENSE.md) instead of the GNU AGPL: free for your own entities' documents and records; work
  for paying clients needs a Pro License Key, which is not sold yet, so Kisaes permits it without
  a key in the 0.x test versions. The download includes `LICENSE.txt`, `NOTICE.txt` and
  `THIRD-PARTY-NOTICES.txt` for the components it contains.
- The footer shows the build identifier beside the version number. Please quote both when you
  report a problem.
- Security: a deliberately malformed PDF (thousands of nested arrays) could crash the app; it is
  now refused or read safely. The bundled SQLite and other components were updated for published
  security advisories.
- PDFs with an owner password (they open without one but restrict editing) are still refused by
  annotate, compress, flatten, OCR text layer, merge and split, as before. Filling forms still
  works on them.
- A client's date of birth given as only a year (for example 1990) is now reported as unreadable
  instead of being read as a 1905 date.

## 0.1.51 (2026-11-20)

- B2 sync is no longer tied to one computer. Whichever server holds the sync lease pushes and
  pulls the whole cabinet, and Admin › Devices names the one holding it.
- Copy and paste in Browse: Ctrl+C and Ctrl+V, or right-click › Copy and the Paste button.
  Files copied in Explorer can be pasted into a client folder.
