# Changelog

## 0.1.3

- Rebuilt and published the extension from the current PageWell renderer, including
  the Mermaid and KaTeX loading fixes introduced after the first packaged release.

## 0.1.2

- Mermaid and KaTeX actually draw now. 0.1.1 enabled them but shipped a reader that
  asked for the library under the filename the live site uses, which is content-addressed
  and therefore not the name inside the package — every diagram was a silent 404 behind
  the words "could not load".

## 0.1.1

- Mermaid and KaTeX now draw in the preview without the document opting in: the
  extension ships their bytes, so nothing is downloaded to draw them. The published
  page still shows the source until the document asks for the library, and the
  preview says so in a notice rather than letting the two drift apart silently.
- The preview button no longer borrows the icon VS Code uses for its own Markdown
  preview, so the two are told apart in the editor title bar.
- Interface in seven more languages: Italiano, 繁體中文, Русский, Türkçe, Polski,
  Čeština, Magyar — fifteen in all, matching the languages VS Code itself ships.

## 0.1.0

First release.

- Share the current Markdown or HTML file as a PageWell link, anonymously or signed in,
  from a dedicated bar in the Activity Bar — no preview needed.
- Update a link in place: the same address serves the new content.
- A tree of every link made from this workspace, with what is left of its life.
- A status-bar item that says whether the file in front of you already has a link.
- Preview beside the file with the same renderer as pagewell.ai (WebAssembly), including
  Mermaid and KaTeX; re-renders as you type and keeps your scroll position.
- Device-code sign-in through VS Code's own authentication provider, so the account and
  its sign-out sit in the Accounts menu.
- Interface in English, 简体中文, Deutsch, Español, Français, 日本語, 한국어, Português (BR).
