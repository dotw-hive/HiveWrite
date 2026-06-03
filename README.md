# HiveWrite

A clean, lightweight browser-based Markdown editor for publishing posts directly to the [Hive blockchain](https://hive.io) via the [Hive Keychain](https://hive-keychain.com) extension.

![License: MIT](https://img.shields.io/badge/license-MIT-red.svg)

---

## Features

- **Markdown editor** with live toolbar — bold, italic, strikethrough, headings, blockquote, lists, links, images, code blocks
- **Write / Preview toggle** — renders your Markdown before you publish
- **Hive Keychain integration** — signs and broadcasts transactions without ever exposing your private key
- **Tag manager** — add up to 8 tags, press Enter or comma to confirm
- **Community support** — post to your blog or select a community (LeoFinance, OCD, Hive Gaming, and more)
- **Reward options** — 50/50 HBD+HP, 100% HP, or Decline rewards
- **Beneficiary support** — assign a percentage of post rewards to another account
- **Transaction confirmation** — shows a link to the transaction on Hive Explorer after a successful post
- **Dark mode** — automatically follows your system preference
- **No dependencies** — single self-contained HTML file, no build tools, no npm, no framework

---

## Requirements

- A Chromium or Firefox based browser (Brave, Chrome, Firefox, Edge)
- [Hive Keychain browser extension](https://hive-keychain.com)
- A Hive account

---

## Usage

Because Hive Keychain's content script does not inject into `file://` pages, you need to serve the file over HTTP rather than opening it directly.

**Option 1 — Python (quickest)**
```bash
python -m http.server 8080
```
Then open `http://localhost:8080/hivewrite.html` in your browser.

**Option 2 — XAMPP / WAMP / MAMP**
Copy `hivewrite.html` into your `htdocs` (or `www`) folder, start Apache, and open:
```
http://localhost/hivewrite.html
```

**Option 3 — Any static file server**
Place `hivewrite.html` on any web host or static hosting service (GitHub Pages, Netlify, Cloudflare Pages, etc.) and open the URL in your browser.

---

## Publishing a Post

1. Open the editor in your browser
2. Confirm the **Keychain connected** indicator is green in the top right
3. Enter your **Hive username** in the sidebar (without the `@`)
4. Write your post — use the toolbar or type Markdown directly
5. Add at least one **tag** (press Enter or comma to confirm each one)
6. Choose a **community** or leave it set to My Blog
7. Select your preferred **reward type**
8. Optionally add a **beneficiary** in the format `account:percent` (e.g. `alice:25` for 25%)
9. Click **Publish to Hive** — Keychain will prompt you to sign the transaction
10. After signing, a confirmation message and link to the transaction appear

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| Ctrl / Cmd + B | Bold |
| Ctrl / Cmd + I | Italic |
| Ctrl / Cmd + K | Insert link |

---

## Beneficiary Format

Enter beneficiaries as `accountname:percentage`, for example:

- `alice:25` — 25% of rewards go to alice
- `bob:10` — 10% of rewards go to bob

The percentage must be a whole number between 1 and 100.

---

## Troubleshooting

**Keychain not detected**
- Make sure the Hive Keychain extension is installed and enabled in your browser
- Ensure you are serving the file over `http://` or `https://`, not opening it as a `file://` URL
- In Brave, check that Shields are not blocking extension scripts on the page
- Try reloading the page — Keychain injects asynchronously and may take a moment

**Post published but beneficiary not applied**
- Check that the beneficiary field uses the correct format: `account:percent`
- Confirm the account name is spelled correctly and exists on Hive

---

## License

MIT — free to use, modify, and distribute.

---

## Contributing

Issues and pull requests are welcome. If you find a bug or have a feature request, please open an issue.
