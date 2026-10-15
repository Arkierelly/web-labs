# WEB LAB — HTML Game Runner

A lightweight static HTML game playground designed for GitHub Pages and Chromebook browsers.

## Features
- Paste and run standalone HTML.
- Open a local `.html`/`.htm` file.
- Import ZIP archives containing HTML, CSS, JavaScript, images, audio, and other assets.
- Choose an entry HTML file when a ZIP contains several.
- Developer and minimal play layouts.
- Dark/light themes, preview zoom, editor font size, adjustable panel width.
- Sandboxed iframe preview, console bridge, fullscreen where supported.
- No backend, accounts, cloud saves, analytics, or required runtime CDN dependencies.

## Publish with GitHub Pages
1. Sign in to GitHub and create a **public** repository (for example, `web-lab`).
2. Upload `index.html` and `README.md` from this folder to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/(root)`, then Save.
6. Wait for GitHub Pages to publish, then open the URL shown in the Pages settings.

The source is public in a public repository. Do not upload personal information or copyrighted game files you do not have permission to publish. WEB LAB itself does not upload imported games anywhere.

## Important limitations
- This is a lightweight, dependency-free editor with line numbers, indentation support, tabs, and keyboard shortcuts. It does **not** bundle CodeMirror or provide full IDE syntax autocomplete.
- ZIP import uses the browser's `DecompressionStream('deflate-raw')` for standard deflated ZIP entries. This API is available in modern Chromium-based browsers, but support may differ in older or managed browsers. ZIP64, encrypted archives, and uncommon compression methods are unsupported.
- ZIP imports use a virtual file map and rewrite common static HTML/CSS asset references to object URLs. Complex games using dynamic `fetch()` calls with relative paths, ES module imports, service workers, server routes, or unusual loading mechanisms may not work.
- Browser sandbox restrictions can affect fullscreen, pointer lock, storage, popups, downloads, network requests, and other game features.
- The runner cannot bypass school network filters or browser policies.
- Large ZIPs use memory. The app caps ZIP files at 80 MB, each expanded file at 30 MB, total expanded data at 120 MB, and archive entries at 2,500, but performance still depends on the Chromebook.

## Keyboard shortcuts
- `Ctrl/⌘ + Enter`: Run
- `Tab`: Insert two spaces
- `Escape`: Close dialogs

## Privacy
The app has no backend and does not send code or imported files to a server. GitHub Pages serves the static site; execution occurs in your browser.
