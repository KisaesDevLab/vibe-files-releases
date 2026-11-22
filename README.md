# Vibe Files

Document management for small CPA and tax firms, on Windows. Vibe Files works over a plain
client folder tree. Your files stay ordinary PDFs and Office files in ordinary Windows folders,
and Vibe Files adds browsing, intake and filing rules, scanning, OCR, search, PDF tools
(annotate, fill forms, page tools), versions, an audit trail, retention and legal hold, and
optional two-way sync to your own Backblaze B2 bucket.

This repository holds the released program only: downloads, the changelog and the licence.

## Download

**[Download the latest release](https://github.com/KisaesDevLab/vibe-files-releases/releases/latest)**

Direct link to the newest version:
`https://github.com/KisaesDevLab/vibe-files-releases/releases/latest/download/vibe-files-windows-x64.zip`

Each release has:

| File | What it is |
|---|---|
| `vibe-files-windows-x64.zip` | The program: unzip and run `vibe-files.exe` |
| `SHA256SUMS.txt` | SHA-256 checksums of the download and of the programs inside it |
| `latest.json` | Version, date and checksums in a form scripts can read |

## System requirements

- Windows 10 or 11, 64-bit.
- Nothing else to install. PDF viewing (PDFium), TWAIN scanning and OCR (Tesseract, English)
  are included.
- For several PCs on one cabinet: a shared folder on the office network that every PC can
  reach.

## Install

1. Download `vibe-files-windows-x64.zip` and `SHA256SUMS.txt` from the
   [latest release](https://github.com/KisaesDevLab/vibe-files-releases/releases/latest).
2. Check the download (see below).
3. Unzip it into a folder of your choice, for example `C:\Vibe Files`, and run
   `vibe-files.exe`.

The data folder (`data\`) is created beside `vibe-files.exe`. To upgrade, replace everything in
the folder except `data\`. `OPERATIONS.md` in the zip covers setting up several PCs, backups and
sync.

### Check the download

In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\vibe-files-windows-x64.zip -Algorithm SHA256
```

The hash must match the `vibe-files-windows-x64.zip` line in `SHA256SUMS.txt`, ignoring
upper/lower case. If it doesn't match, delete the download and don't run it.

### Windows SmartScreen

Releases may not be code-signed yet. On the first start, Windows can show **"Windows protected
your PC"**. After checking the download as above, click **More info**, then **Run anyway**.
Windows asks only once per version.

## Privacy

- No telemetry. Vibe Files never sends your documents or usage to Kisaes.
- Network calls go only to your own B2 bucket (when you turn sync on), your firm's own portal
  (when one is set), and one check per start for a newer release on this page.
  `update_check = false` in `data\config.toml` turns that check off. Nothing is ever downloaded
  or installed automatically.
- Files sent to B2 are encrypted on your PC first, with a key only your firm holds.

## Support

- Bugs and feature requests: [open an issue](https://github.com/KisaesDevLab/vibe-files-releases/issues/new/choose).
  Never attach client documents or real client data. Describe the problem, or use made-up
  sample files.
- Security problems: see [SECURITY.md](SECURITY.md). Please don't report them in a public issue.

## Licence

Vibe Files is proprietary software of Kisaes LLC, licensed under the end user licence agreement
in [LICENSE.md](LICENSE.md). Third-party components it includes keep their own licences, listed
in `THIRD-PARTY-NOTICES.txt` in the download.

Versions 0.1.51 and earlier were published under the GNU Affero General Public License v3.0 or
later. Copies of those versions keep that licence.
