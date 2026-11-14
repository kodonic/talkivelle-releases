# Talkivelle 1.0.2

*Make room for conversation.* Notes, chat, file sharing and calls for people on the same local network. No internet, server or account needed.

This release adds search, folders, a Recycle Bin, backups, password protection, a Markdown preview and background (tray) mode. It also fixes several bugs and hardens the installed app.

## Download

| File | Platform | Size | SHA-256 |
|---|---|---|---|
| `Talkivelle-Setup-1.0.2.exe` | Windows 10/11 (64-bit) | 119.6 MB | `21de2802f8d76e8192ae8180f75ca6a9b197d440214346b98a534a1978bcd787` |
| `Talkivelle-1.0.2-silicon.dmg` | macOS, Apple silicon (M1 or later) | 122 MB | `14b746bb52193c2b7934a8b056b26067ae83f7d9ba6b1ca881cac73e173f446a` |
| `Talkivelle-1.0.2-intel.dmg` | macOS, Intel | 128.8 MB | `e351bf784e916273368ae36c5a97a3780cb7a771d351edde9b10d6f2a7bc6c0a` |

> The installers are not code-signed yet. On Windows, SmartScreen may show "Windows protected your PC": choose **More info → Run anyway**. On a Mac, the first time, right-click Talkivelle in Applications and choose **Open**.

## Upgrading

Run the new installer over your current version; there's no need to uninstall first.

- **Your data is kept.** Notes, chats, folders, settings and the Recycle Bin live in `%APPDATA%\Talkivelle`. Installing, upgrading and uninstalling never delete them.
- **Safety copy before any database change.** If a new version needs to change the database, it first saves a full copy to `%APPDATA%\Talkivelle\backups\` (the newest 3 are kept).
- **No downgrades onto newer data.** An older version won't open data from a newer one; it asks you to update instead.

## New

### Search
- **Find in a note (Ctrl+F / Ctrl+H):** a compact box floats over the editor. It has previous/next, a "3 of 12" count, and toggles for match case, whole word and regular expressions, plus an optional replace row.
- **Search box in the sidebar:** type to search note names and note text instantly.
- **Search in notes (Ctrl+Shift+F):** search the current note, all open notes, or all notes (or one folder), with results grouped by note. Click a result to jump to it.
- **Replace in notes (Ctrl+Shift+H):** previews every change, replaces them all at once, and offers **Undo**. With regular expressions, `$1`, `$2` etc. insert matched groups.

### Organising notes
- **Folders:** one level of folders in My notes. Move notes by dragging or with **Move to folder**.
- **Recycle Bin:** deleted notes and folders go to a full-page Recycle Bin, which you can search, filter and sort. Restore or delete items one at a time or in bulk. Items are deleted permanently after 90 days.
- **Backup and restore:**
  - Save all notes and folders as a `.zip` of plain text files, wherever you choose.
  - Restoring adds notes back without overwriting anything. Changed notes come back as "(from backup)" copies.

### Privacy and security
- **App lock:** an optional password every time Talkivelle opens. Ctrl+L locks it immediately. While locked, notifications don't show who wrote or what.
- **Password-protected notes:** stored encrypted (AES-256-GCM) and ask for their password each time they're opened.
- **No recovery:** forgotten passwords can't be recovered by anyone.

### Markdown preview
- For `.md` notes there are three views: **Edit**, **Split** (live preview beside the text) and **Preview**. Switch with the status bar control or Ctrl+Shift+V.
- Supports headings, lists, task lists, tables, quotes and code blocks.
- The preview is sanitised: scripts are removed, and only web and email links open (in your browser).

### Running in the background
- Closing the window keeps Talkivelle running in the system tray, so messages and calls still arrive.
- Click the tray icon to open the window. Right-click it for New note, Lock and Quit.
- Settings → Background has three options: keep running when closed, minimize to the tray, and start when you sign in to Windows.

### Look and feel
- New Talkivelle branding: logo, brand colours (violet, teal, ink), and the Inter and Manrope typefaces, in light and dark themes.
- A new **About** page with version and contact details.

## Fixes
- **Selections now show:** selected text in the editor is visibly highlighted again, including on the current line.
- **Readable dropdowns:** in dark mode, the language dropdown (bottom right) had light text on a white list.
- **No stray outline:** removed the dotted outline that appeared around the editor when clicked.
- **Old note text cleared from disk:** protecting a note with a password now also removes earlier unencrypted copies of its text from the database files.
- **Newer data refused cleanly:** opening data from a newer version is now refused without leaving the database file open.

## Security hardening (installed app)
- **Compiled core code:** the main process ships as compiled V8 bytecode, and the rest is minified, with no source maps.
- **Tamper check at startup:** a modified app package refuses to start.
- **No debugging:** the app can't be started with debugging or "run as Node" switches, and developer tools are disabled.
- **Release check:** the build fails if source code would be included in the installer.

## Known limitations
- **No internet pictures in the preview:** Markdown preview shows internet images as their description, since Talkivelle works offline.
- **Locked notes aren't searched:** open them with their password to include them.

---

Talkivelle is a product of Kodonic® · [kodonic.com](https://kodonic.com) · support@kodonic.com
© 2026 Kodonic Digitech Private Limited. All rights reserved.
