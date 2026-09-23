# PageWell for VS Code

Share the file you are editing as a link, and preview Markdown and HTML the way
[PageWell](https://pagewell.ai/) renders them. No account needed to start.

![The side bar shares, the panel beside it reads, the status bar says whether this file has a link](https://raw.githubusercontent.com/pagewellai/pagewell-vscode-extension/main/store-assets/screenshot-1-share.png)

## Three places, one job each

- **The PageWell bar** in the Activity Bar turns the current file into a link, and lists
  every link made from this workspace with what is left of its life.
- **The preview** opens beside the file and leaves it open — the same model as VS Code's
  own Markdown preview. It only reads.
- **One status-bar item** says whether the file in front of you already has a link.
  Click it to copy that link.

Sharing never needs the preview: open the bar and press the button. The keyboard shortcut
`Ctrl+Alt+U` (`Cmd+Alt+U` on macOS) opens the bar with the focus already on it — nothing
leaves your machine until you press it.

## The preview is the published page

The preview runs the same renderer as pagewell.ai, compiled to WebAssembly and packaged
inside the extension, with the same stylesheet. Headings, tables, code highlighting,
Mermaid diagrams and KaTeX formulas look here exactly as they will for a reader. Typing
re-renders in place and keeps your scroll position.

HTML files are shown as-is inside a sandboxed frame — their own styling, no scripts.

## Share without an account, or sign in

![Anonymous and signed-in states of the PageWell bar](https://raw.githubusercontent.com/pagewellai/pagewell-vscode-extension/main/store-assets/screenshot-2-states.png)

**Anonymous** — no account, no sign-up. Up to 1 MiB per file, 5 new links per IP each UTC
day, and the link is removed 24 hours after its last update.

**Signed in** — files are saved to your Documents on PageWell, up to 5 MiB, and kept until
you delete them. Signing in goes through PageWell's device approval flow: the extension
shows a short code, you approve it in your browser. It never asks for a password.

Your account and its sign-out live in VS Code's own Accounts menu, next to your other
sign-ins.

## Update a link instead of making a new one

Share a file once and the extension remembers where it went. Press **Update link with this
file** and the same address serves the new content — anyone who already has the link sees
the new version without being sent a new one.

## Privacy

The file is read and uploaded only when you press Share or Update. Nothing is watched,
scanned or sent in the background. What goes up is the **source** — your Markdown or HTML
as written, not a rendered snapshot — because the server renders it with the same renderer
you just previewed with.

Sign-in tokens are kept in VS Code's SecretStorage. The link for each file, and the
one-time token that lets an anonymous link be updated, are kept in workspace state on this
machine.

## Commands

| Command | What it does |
| --- | --- |
| **Open Preview with PageWell** | Opens the preview beside the file |
| **Share as Link with PageWell…** | Opens the bar with the focus on the primary button |
| **Update Shared Link** | Same address, new content |
| **Copy Link** / **Open Link in Browser** | For a file you already shared |
| **Open in PageWell** | Manage the document on the website |
| **Sign In** / **Sign Out** | Device-code sign-in; signing out only clears this machine |

Right-click a `.md` or `.html` file in the editor or the Explorer for the first two.

## Settings

| Setting | Default |
| --- | --- |
| `pagewell.endpoint` | `https://pagewell.ai` — change it when self-hosting or debugging locally |

---

[PageWell](https://pagewell.ai/) · [Report an issue](https://github.com/pagewellai/pagewell-vscode-extension/issues) · Apache-2.0

---

## This repository

Install it from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=pagewellai.pagewell), or from the `.vsix` below.

It holds the **built extension only** — the source lives in the PageWell monorepo, and
every release here comes from one build there (see `MANIFEST`).

```bash
# download pagewell-0.1.0.vsix from the release for v0.1.0, then
code --install-extension pagewell-0.1.0.vsix
```
