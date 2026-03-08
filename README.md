# STL Splitter

A single-file browser tool that separates multi-object STL files into individual objects for selective export.

## Overview

STL files often contain multiple disconnected 3D objects packed into a single file. STL Splitter automatically detects and separates these objects using vertex connectivity analysis (Union-Find), displays them with distinct colors in a 3D viewport, and lets you export selected objects as individual STL files.

- No server, no installation — just open the HTML file in a browser.
- [Start STL-Splitter](https://covao.github.io/STL-Splitter/stl-splitter.html)

## Usage

**Open a file** — Drag & drop an STL file onto the page, or click to browse. Both binary and ASCII STL formats are supported.

**Load via URL parameter** — Append `?file=` to auto-load an STL from a URL path:

```
stl-splitter.html?file=./models/part.stl
stl-splitter.html?file=https://example.com/model.stl
```

**Select objects** — Click items in the sidebar to toggle selection. Deselected objects become translucent in the viewport.

**Export** — Choose either:
- **Merge export** — Save all selected objects as a single STL file.
- **Separate export** — Download each selected object as its own STL file.

**Viewport controls:**
- Left drag: Rotate
- Shift + drag / Middle drag: Pan
- Scroll: Zoom

## Specification

| Item | Detail |
|---|---|
| Format | Single HTML file (HTML + CSS + JS) |
| Dependency | Three.js r128 (loaded from CDN) |
| STL input | Binary and ASCII |
| STL output | Binary |
| Separation method | Union-Find on spatial-hashed vertices |
| Tolerance | Configurable vertex merge distance (default `0.001`) |
| URL parameter | `?file=<path-or-url>` — fetch and load on startup |
| Browser support | Modern browsers (Chrome, Firefox, Edge, Safari) |
