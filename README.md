# mbox reader

A single-file, zero-dependency browser tool for reading `.mbox` email archive files. Drop it in a browser, open a file, read your emails. Nothing is uploaded anywhere — all parsing happens locally on your machine.

## Usage

1. Download `mbox-extractor.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Click **Open .mbox** and select your archive file
4. Browse, search, and read

No server. No install. No data leaves your computer.

## Features

**Reading**
- Parses standard mbox format (RFC 4155) entirely in the browser
- Renders plain-text email bodies in a clean, readable view
- Handles multipart MIME messages, including nested parts
- Strips HTML emails to readable plain text automatically
- If a body can't be displayed cleanly, shows a clear explanation instead of garbled output

**Encoding support**
- UTF-8 (default)
- Windows-1255 / ISO-8859-8 (Hebrew)
- ISO-8859-1 / Windows-1252 (Latin)
- Decodes MIME encoded-words (`=?charset?B/Q?...?=`) in headers and subjects
- Decodes quoted-printable and base64 transfer encodings

**Navigation**
- Collapsible tree sidebar grouping emails by **Sender** or **Date**
- Live filter search across sender names and subjects
- Keyboard navigation: `↑` / `↓` or `j` / `k` to move between emails

**Attachments**
- Detects and lists attachments for each email
- Download any attachment as a real file directly from the browser
- Shows MIME type and file size for each attachment

## Limitations

- Very large mbox files (hundreds of MB) may be slow to parse — all work happens on the main thread
- HTML emails are converted to plain text; rich HTML rendering is intentionally not supported
- `message/rfc822` deeply nested messages may not fully surface all inner parts

## File format

Expects standard mbox format where each message begins with a `From ` envelope line. Compatible with exports from Gmail (Google Takeout), Thunderbird, Apple Mail, Outlook, and most Unix mail clients.

## License

MIT
