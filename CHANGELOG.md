# Changelog

What changed in each Vibe Files release, newest first. Each section is also the release's notes.

## 0.1.55 (2026-11-24)

Most of this needs Vibe Portal 0.5.2 or later; **Admin › Portal** says when the portal is older.
Update the portal first, then every PC.

- New: **Portal contacts**. In **Import clients CSV…**, choose the columns with the taxpayer's
  and spouse's name, email and cell. They are kept in the cabinet, so the CSV is not needed
  after the import. Type or fix them in a client's panel (**PORTAL CONTACTS**): what you type is
  kept over later CSVs.
- Before a re-import changes anything, **Changes in this CSV** lists new, renamed and changed
  clients, the clients the CSV leaves out, and changed contacts.
- New: **Admin › Portal › Invite from client list**. Invite many clients at once. A joint couple
  gets two logins (one in both names when they share an email), a business contact is invited
  as Owner, and nobody who is already on the portal or invited is sent another invitation.
  Invitations go out 20 at a time with a minute's pause, so your email provider does not take
  them for spam (both can be changed), and **Stop** ends a run. **Search**, Show and Partner
  narrow the list; **What they receive** shows the message as it is sent.
- **Access requests** are now matched with the clients by the email or cell the person
  confirmed: approve them for every client they belong to in one click, each with its role
  (Spouse at the 1040, Owner at the LLC). A request that only matches by name, or whose date of
  birth differs, asks how you checked first. Approving can share chosen documents with them
  (Admin › Portal picks the doc types and years) and keep their confirmed contact. The footer
  says when requests are waiting, on every PC.
- **Share on portal**: someone invited who has not accepted can be given the documents and sent
  the invitation again in one Save; **Send invitation and share** invites and shares in one step;
  an email or cell that already has a portal login is recognised and added at once.
- Merging a duplicate client, or merging cabinets, brings the client's Portal contacts along.
- New: **Delete client…** for a client with no documents, in its panel and on right-click in
  the tree: its empty folder goes and it leaves the client list and the client CSV. **Undo
  delete** in Browse puts it back. The portal is not changed.
- The portal (0.5.2) can also send to-do notices and reminders by text: its Settings › To-do
  lists.

## 0.1.54 (2026-11-23)

- New: to-do lists for clients, through your Vibe Portal (needs Vibe Portal 0.5.0 or later).
  Send a client a list of documents to upload and questions to answer, from the client's
  **To-do lists…** button. The client answers on the portal: they upload a file, type an answer,
  or mark an item "does not apply".
- Every answer is recorded with its date and time, the person, their email and IP address, and,
  for a file, its SHA-256. Download the record as a PDF report, or file it into the client's
  folder.
- Files the client sends for an item arrive in the Portal inbox tagged with the item's document
  type, ready for Intake.
- Lists can remind the client by themselves every 3, 7 or 14 days, or with **Remind now**. Assign
  a staff member to be emailed when the client answers.
- **From last year's return…** reads the UltraTax return filed for the client and proposes an
  item for each W-2, 1099, K-1, 1098, interest and dividend payer, and more. Nothing leaves your
  PC until you send the list.
- **Admin › To-do templates**: save lists you send often and send one to many clients at once.
- A copy of each list is kept in the client's folder (`_Vibe/todo`), shown when the portal
  cannot be reached.
- To-do lists are off until an admin turns them on, in **Admin › Portal** here and in the
  portal's Settings.

## 0.1.53 (2026-11-23)

- New: an installer, `vibe-files-setup-x64.exe`. It asks whether to install for you only (no
  administrator rights needed) or for everyone on the PC (asks for an administrator), adds a
  Start menu entry and an entry in Settings › Apps to uninstall. Upgrades keep your choice.
- An installed copy keeps each Windows login's catalog and settings in
  `%LOCALAPPDATA%\Vibe Files\data`. Installing, upgrading and uninstalling never touch them or
  your cabinet.
- The portable zip is still available and works as before.
- Vibe Files has its own icon, in Explorer, the taskbar, the Start menu and the window.

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
