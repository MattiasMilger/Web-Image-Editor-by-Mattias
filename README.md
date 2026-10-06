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
- **Text** - Place text directly on the image. Click, type, drag to move, drag a corner handle to resize, then click outside it to place it.
- **Blank image** - Start from a blank canvas (pick a size or a preset, and a colour (white by default) or transparent background) instead of opening a picture, then draw, insert images and add text on it.
- **Transparent colour** - The checkerboard swatch erases to transparency with any tool (paint, shapes, text). Download PNG to keep the transparency; JPG fills it with white.
- **Insert image** - Drop, paste (Ctrl+V) or pick another image to add it on top of the current one. Drag to move, drag the corner / edge handles to resize freely (Shift on a corner keeps proportions), then click outside it (or press Enter) to lock it in. Esc cancels.
- **Colour & Size** - Shared colour picker, swatches, and size slider for all tools except Text, which is resized with its corner handles.
- **Undo / Clear** - Undo last annotation or clear everything (with confirmation).
- **Download** - Export as PNG or high-quality JPG.
- **Copy** - Copy the annotated image to the clipboard (supported browsers).
- **Dark / Light Theme** - Toggle between dark and light modes with the ◐ button (dark by default, choice is remembered).
- **Privacy** - Everything stays in your browser. Nothing is uploaded.

## Project Structure
Web Image Editor by Mattias/
├── index.html              # Main HTML structure, tools, and application logic
├── style.css               # Styling, theming (CSS variables), responsive design
└── README.md               # This file

### Module Responsibilities

| Module | Purpose |
|---|---|
| `index.html` | UI layout, tool handling, canvas drawing, image loading (file / paste / drop), image insertion overlay, text placement, theme toggle, export |
| `style.css` | Dark theme by default (light via `body.light-mode`), button/toolbar styles, responsive layout, text editor panel |

## How It Works

1. Load an image by clicking the empty area, dragging a file, or pasting (Ctrl+V / Cmd+V) - or click **Blank image** to start with a blank canvas.
2. Select a tool (Paint, Arrow, Line, Box, Censor, or Text).
3. Draw or place annotations using the current colour and size.
4. To **insert an image**: drop, paste, or click **Insert image** while an image is open. Move and resize it, then click anywhere outside it (or press Enter) to place it.
5. For **Text**: click on the image, type, drag the text to move it and a corner handle to resize it, then click anywhere outside it (or press Enter) to place it.
6. Undo individual steps or clear all annotations.
7. Download as PNG or JPG, or copy to clipboard.

## Technical Notes

- **No external dependencies** - pure vanilla HTML, CSS, and JavaScript.
- **Client-side only** - No data is transmitted to any server. Images and annotations exist only in the browser.
- **Canvas-based** - Annotations are drawn on an HTML5 canvas over the original image.
- **Pointer events** - Supports mouse, touch, and pen input.
- **Censor** - Uses large average-colour blocks so text under the censored area cannot be recovered.
- **Theme** - The selected theme is saved in `localStorage` and restored on the next visit.

## Browser Support

Works in all modern browsers (Chrome, Firefox, Edge, Safari).

## Credits

**Developer**: Mattias Milger
**Email**: mattias.r.milger@gmail.com
**GitHub**: [MattiasMilger](https://github.com/MattiasMilger)

## More Projects

Check out more of my work at [mattiasmilger.github.io](https://mattiasmilger.github.io/)