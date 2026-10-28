# Web Image Editor by Mattias

A browser-based image editor built with vanilla HTML, CSS, and JavaScript. Runs entirely client-side - no server or backend required. Designed for GitHub Pages.

## Try It Out

The live version is available at: **https://mattiasmilger.github.io/Web-Image-Editor-by-Mattias/**

### Run Locally

Open `index.html` in a modern browser. No build tools or dependencies required.

## Features

- **Paint** - Freehand drawing with adjustable size and colour.
- **Arrow** - Draw clean open-headed arrows to point things out. The tip lands exactly where you release, and the arrow is kept inside the image, so it never clips at the edge.
- **Line** - Free-direction lines for underlining or highlighting.
- **Box & Circle** - Draw rectangles and circles / ellipses. The **Shape** panel switches between outline and filled.
- **Censor** - Pixelate / block out sensitive areas with average-colour blocks. The Size setting sets the block size.
- **Text** - Place text directly on the image. Click and type; **Enter** starts a new line, so you can write several lines. Use the **Size** setting to make the text larger or smaller, drag to move, then click outside it (or press **Ctrl+Enter**) to place it. Esc cancels.
- **Text box** - Drag the handles on the left and right side to change the width of the text box (the text wraps to fit) and the handles on the top and bottom to stretch the text taller or flatter. The corner handles do both, so the box can be any rectangle or square. **Size** sets the font size.
- **Crop** - Pick the Crop tool and a box appears on the image. Drag the handles to choose the part to keep, drag inside the box to move it, or drag outside it to draw a new one. Everything outside the box is dimmed and a live pixel size is shown. Click **Crop** (or press **Enter**) to cut the image down to the box, **Cancel** (or **Esc**) to leave it as it is. Undo takes it back.
- **Canvas size** - In the **Image** menu. Like *Canvas Size* in GIMP: set a new width and height, choose where the current picture sits on the new canvas (3x3 grid) and what colour the new area gets (or transparent). A smaller size crops. Undo takes it back.
- **Blank image** - Start from a blank canvas (pick a size or a preset, and a colour (white by default) or transparent background) instead of opening a picture, then draw, insert images and add text on it.
- **Transparent colour** - The checkerboard swatch erases to transparency with any tool (paint, shapes, text). Download PNG to keep the transparency; JPG fills it with white.
- **Import image** - *(Image menu)* Open a picture from your computer, replacing the current image.
- **Insert image** - Drop, paste (Ctrl+V) or pick another image to add it on top of the current one. Drag to move, drag the corner / edge handles to resize freely (Shift on a corner keeps proportions), then click outside it (or press Enter) to lock it in. Esc cancels.
- **Zoom & pan** - Zoom buttons, Ctrl/Cmd + mouse wheel (or trackpad pinch), or the + / - / 0 keys. Pan by scrolling, Space + drag, or middle-mouse drag; on touch screens use two fingers to pan and pinch. All tools keep working while zoomed.
- **Colour & Size** - Shared colour picker, swatches, and size control for all tools. For Text, Size sets the font size. Size runs from 1 to 48 in whole numbers (standard is 6): drag the slider (finer steps at the small end) or type an exact number. Decimals and out-of-range values are flagged while typing and rounded / clamped when you confirm.
- **Undo / Clear** - Undo last annotation or clear everything (with confirmation).
- **Download** - The **Download** button next to the **Image** menu exports the image as PNG or high-quality JPG.
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

1. Load an image by clicking the empty area, dragging a file, or pasting (Ctrl+V / Cmd+V) - or use **Image > Blank image** to start with a blank canvas.
2. Select a tool (Paint, Arrow, Line, Box, Circle, Censor, Text, or Crop).
3. Draw or place annotations using the current colour and size.
4. To **insert an image**: drop, paste, or click **Insert image** while an image is open. Move and resize it, then click anywhere outside it (or press Enter) to place it.
5. For **Text**: click on the image and type (Enter = new line). Change the Size to make it larger or smaller, drag the text to move it, then click anywhere outside it (or press Ctrl+Enter) to place it. Drag the side handles to change the width of the text box (the text wraps).
6. Undo individual steps or clear all annotations.
7. Download as PNG or JPG, or copy to clipboard.

## Technical Notes

- **No external dependencies** - pure vanilla HTML, CSS, and JavaScript.
- **Client-side only** - No data is transmitted to any server. Images and annotations exist only in the browser.
- **Canvas-based** - Annotations are drawn on an HTML5 canvas over the original image.
- **Separate UI layer** - The text box, its handles, the caret, the censor selection and the insert-image frame are drawn on a second transparent canvas laid over the picture, so they never end up in Copy, Download or the browser's right-click *Copy image*.
- **Crop** - Stored as a canvas-size step with a negative offset, so it shares the same Undo / Clear handling. The dimmed overlay, handles and guides live on the separate UI canvas and never end up in Copy or Download.
- **Canvas size** - Stored as a step in the annotation list, so annotations drawn before it keep their place and Undo restores the old size. Limited to 8000 px per side.
- **Text wrapping** - Text is laid out line by line for the chosen box width and then stretched vertically by the box height; the caret and the selection are mapped onto the wrapped lines.
- **Pointer events** - Supports mouse, touch, and pen input.
- **Censor** - Uses average-colour blocks so text under the censored area cannot be recovered.
- **Theme** - The selected theme is saved in `localStorage` and restored on the next visit.

## Browser Support

Works in all modern browsers (Chrome, Firefox, Edge, Safari).

## Credits

**Developer**: Mattias Milger
**Email**: mattias.r.milger@gmail.com
**GitHub**: [MattiasMilger](https://github.com/MattiasMilger)

## More Projects

Check out more of my work at [mattiasmilger.github.io](https://mattiasmilger.github.io/)