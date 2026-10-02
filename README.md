# Web Image Editor by Mattias

A browser-based image editor built with vanilla HTML, CSS, and JavaScript. Runs entirely client-side - no server or backend required. Designed for GitHub Pages.

## Try It Out

The live version is available at: **https://mattiasmilger.github.io/Web-Image-Editor-by-Mattias/**

### Run Locally

Open `index.html` in a modern browser. No build tools or dependencies required.

## Features

- **Paint** - Freehand drawing with adjustable size and colour.
- **Arrow** - Draw clean open arrowheads to point things out.
- **Line** - Free-direction lines for underlining or highlighting.
- **Box** - Draw rectangular outlines.
- **Censor** - Pixelate / block out sensitive areas with large average-colour blocks.
- **Text** - Place text directly on the image. Type, drag to reposition, then Place.
- **Colour & Size** - Shared colour picker, swatches, and size slider for all tools.
- **Undo / Clear** - Undo last annotation or clear everything (with confirmation).
- **Download** - Export as PNG or high-quality JPG.
- **Copy** - Copy the annotated image to the clipboard (supported browsers).
- **Privacy** - Everything stays in your browser. Nothing is uploaded.

## Project Structure
Web Image Editor by Mattias/
├── index.html              # Main HTML structure, tools, and application logic
├── style.css               # Styling, theming (CSS variables), responsive design
└── README.md               # This file

### Module Responsibilities

| Module | Purpose |
|---|---|
| `index.html` | UI layout, tool handling, canvas drawing, image loading (file / paste / drop), text placement, export |
| `style.css` | Dark theme by default, button/toolbar styles, responsive layout, text editor panel |

## How It Works

1. Load an image by clicking the empty area, dragging a file, or pasting (Ctrl+V / Cmd+V).
2. Select a tool (Paint, Arrow, Line, Box, Censor, or Text).
3. Draw or place annotations using the current colour and size.
4. For **Text**: click on the image, type, drag the text to move it, then click **Place** (or press Enter).
5. Undo individual steps or clear all annotations.
6. Download as PNG or JPG, or copy to clipboard.

## Technical Notes

- **No external dependencies** - pure vanilla HTML, CSS, and JavaScript.
- **Client-side only** - No data is transmitted to any server. Images and annotations exist only in the browser.
- **Canvas-based** - Annotations are drawn on an HTML5 canvas over the original image.
- **Pointer events** - Supports mouse, touch, and pen input.
- **Censor** - Uses large average-colour blocks so text under the censored area cannot be recovered.

## Browser Support

Works in all modern browsers (Chrome, Firefox, Edge, Safari). Requires JavaScript enabled. Clipboard copy requires a secure context (HTTPS or localhost).

---

## More Projects

Check out more of my work at [mattiasmilger.github.io](https://mattiasmilger.github.io/).