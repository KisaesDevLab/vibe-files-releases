# Changelog

What changed in each Vibe Files release, newest first. Each section is also the release's notes.

## 0.1.59 (2026-11-26)

Update the portal to Vibe Portal 0.5.7 as well: with 0.5.6, sending a financial statements or
other document card failed ("A document could not be put on the card").

- Fixed: Admin › Portal › Deliveries said a card whose documents open only after the fee is paid
  was waiting on its locked documents; it now waits on the fee, can be ticked for Remind ticked,
  and is listed under Payment due.

## 0.1.58 (2026-11-26)

This needs Vibe Portal 0.5.6 or later for its new features. Update the portal first, then every
PC: an older Vibe Files lists only tax return cards and would file a statements card's PDFs as a
tax return's.

- New: **Deliver…** (was Deliver tax return…) sends more than a tax return. Choose the Kind:
  Tax return, Financial statements, or Other document (type its name). A card can carry several
  PDFs; each shows Opened once the client opens it, and the step is done when every one is.
  Financial statements' PDFs are filed in `Financials\<year>\Delivery`, other documents' in
  `Other\<year>\Delivery`.
- New: **Documents open only after the fee is paid**, a tick on the fee. The client sees the
  documents' names locked until they pay (a bank payment started opens them).
- New: **Hold the client's files until this is paid**, a tick on Balance owed. While the balance
  is due the client sees their files listed but cannot open, download or send them on; paying,
  Clear balance or the balance's removal releases them.
- New: **Remind ticked** on Admin › Portal › Deliveries: tick rows (or Tick all shown, Tick
  waiting too long) and each client is reminded, 20 at a time with a minute's pause.
- Admin › Portal › Agreements lists only clients with an agreement to renew.
- Fixed: the pricing plan add-on boxes were too narrow to read.

## 0.1.57 (2026-11-26)

This needs Vibe Portal 0.5.5 or later. Update the portal first, then every PC.

- New: **Service agreement…** in a client's details. The client signs an annual agreement on the
  portal without a tax return: a letter for each service (tax, bookkeeping, payroll, advisory),
  the firm's Terms and Conditions in each letter, signed by the right people for the client's
  entity type, the partner's name printed. Each service can have a one-time fee, a monthly
  charge, or both; the client pays once and the monthly charge runs until it is stopped.
  **End engagement…** sends the closure letter and stops the charge.
- New: **engagement letter templates** made from the AICPA Annual Tax Compliance Kit, and
  sample bookkeeping, payroll and advisory letters. They are samples: have your attorney review
  your wording before use. A letter with a [fill-in] left in it is not sent.
- New: **Admin › Portal › Agreements**. The firm's partners, and next year's agreements sent to
  many clients at once from their last ones, in groups with a pause and **Stop**.
- **Deliveries** now lists agreements too, with filters by the step waiting and by kind, a
  **Monthly charge** column, **Show finished**, and your own number of days for "waiting too
  long".
- New: **Admin › Portal › Organizers**. Import your online organizer app's export (Stanford Tax);
  each row is matched to a client and, once you confirm, the client's organizer link shows on
  their portal home page. Their people can be told by email or text, once.
- The portal can print a receipt at the office when a client pays online, through Vibe Print.
  It is set up on the portal's staff page, **Settings › Printing**.
- Signed agreement and delivery PDFs, and monthly receipts, are filed by Intake in the client's
  folders.

## 0.1.56 (2026-11-25)

This needs Vibe Portal 0.5.4 or later. Update the portal first, then every PC. Both new features
are off until you turn them on, on the portal and in **Admin › Portal**; the portal's
`docs/firm-setup.md` walks through setting up Stripe (in test mode first).

- New: **Balance owed**. Post an amount a client owes from the client's details; the client pays
  it on the portal by card or bank account, into the firm's own Stripe account. Reminders, a
  person told of each payment, a card fee if you charge one, and a **Payment receipt** PDF filed
  in the client's `Billing` folder. **Balances** lists them by month.
- New: **Deliver tax return…**. The client's portal home page gets a card for their return that
  walks them through up to five steps: sign the letters, review the return, choose a package,
  pay the fee, and sign Form 8879 (through UltraTax's eSignature link). Each finished step's PDF,
  with a log of who did what, when and from where, is filed in `Income Tax/<year>/Delivery`.
  Steps can wait for earlier ones; a revised return reopens its steps. **Deliveries** lists every
  open delivery and the step it waits on.
- New: **Admin › Portal › Letter templates**. Engagement letters, consents and package addenda,
  edited on the page as they print (headings, bold, lists, tables, fields, signature blocks),
  and signed on the portal by the taxpayer and spouse or an officer. The samples are a starting
  point only: have your own wording and your attorney's review in place before use. **Preview**
  with invented people or one of your clients. **New return type…** adds your own (990, 1041,
  a state return).
- New: **Admin › Portal › Pricing plans**. Packages compared side by side, with prices worked out
  from the client's return fee, and add-ons (drag to reorder). **Used by** lists the deliveries
  sent with a plan's prices.
- Faster with many deliveries: the Deliveries page draws only the rows on screen, and copies of
  deliveries into client folders no longer freeze the window.

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
