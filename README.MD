## CardGen.io — Instant Card Generator

A lightweight, single-page web app for creating and downloading professional image cards for social media. 100% client-side, no sign-up, no backend.

### Highlights
- **Instant previews**: Live WYSIWYG canvas with watermark.
- **Typography controls**: Font family, sizes, italics for author.
- **Color & background**: Solid colors, curated palettes, beautiful gradients.
- **Layouts**: Padding, line-height, text alignment.
- **Orientations**: One-click aspect ratios (1:1, 4:5, 3:4, 2:3, 9:11, 9:16, 16:9, 1.91:1, 5:4).
- **Export**: Hi‑res PNG via `html2canvas`.
- **Zero data collection**: Everything runs in your browser.

### Tech Stack
- **HTML5**: Single file app (`index.html`).
- **Tailwind CSS (CDN)**: Rapid, responsive UI styling.
- **Vanilla JavaScript**: All logic inline.
- **html2canvas**: Client-side rasterization to PNG.
- **Google Fonts**: Curated professional font set.

## Getting Started

### Prerequisites
- A modern web browser (Chrome, Edge, Firefox, Safari).
- Optional: A local HTTP server if loading locally with strict CORS policies (most browsers work by double‑clicking `index.html`).

### Installation
1. Clone or download this repository to your machine.
2. Ensure `index.html` and `cardgenio.png` (header logo) are in the project root.

### Run
- Double‑click `index.html` to open in your browser, or
- Serve the folder with any static server:

```bash
# Option 1: Python
python -m http.server 8080

# Option 2: Node (http-server)
npx http-server -p 8080
```

Open `http://localhost:8080` in your browser.

## Usage
1. Type your main text in the “Main text” area and the author/handle below.
2. Adjust fonts (family and sizes). Toggle italic for the author if desired.
3. Pick colors for text and author. Try a palette or gradient for quick aesthetics.
4. Fine‑tune layout with padding, line height, and alignment.
5. Choose an orientation below the preview (e.g., 4:5 for Instagram portrait, 1.91:1 for Twitter cards, 9:16 for stories).
6. Click “Download PNG (Hi‑Res)” to save a crisp image.

### Common Aspect Ratios
- 1:1 — Square (e.g., Instagram feed)
- 4:5 — Portrait (Instagram optimal portrait)
- 3:4, 2:3, 5:4 — Additional portrait options
- 9:11 — Tall portrait variant
- 9:16 — Stories/Reels/Shorts
- 16:9 — Landscape (YouTube, presentations)
- 1.91:1 — Twitter/X link cards and some ad placements

## Features Overview
- **Text Inputs**: Separate fields for main content and author/handle.
- **Live Preview**: WYSIWYG square/selected aspect canvas.
- **Fonts**: Curated list (Inter, Poppins, Montserrat, DM Sans, Work Sans, Lora, Playfair Display, Merriweather, Source Serif 4, Roboto Mono).
- **Colors**: Color pickers for text/author, invert button, and 5 preset palettes.
- **Backgrounds**: Solid color or gradient with multiple gradient swatches.
- **Layout**: Padding slider (%), line-height slider, and alignment buttons.
- **Branding**: Subtle “CardGen.io” watermark in the corner.
- **Ads Placeholder**: A reserved, non-intrusive area for future monetization.

## Project Structure
```
cardgenio/
├─ index.html        # Entire application (HTML, CSS via CDN, JS)
├─ cardgenio.png     # Small header logo (optional, referenced in header)
└─ README.MD         # This file
```

## Configuration & Customization
- To change default text, colors, or sizes, edit the defaults in `index.html` inputs and initial state.
- To add/remove fonts, update the Google Fonts `<link>` and the font `<select>` options.
- To modify palettes/gradients, update the swatch buttons’ `data-palette` / `data-gradient` attributes.
- To tweak export scale, adjust the `scale` option in the `html2canvas` call.

## Tips for Best Results
- Keep quotes short for readability, especially on mobile.
- Use high contrast between background and text.
- White or near-white text over gradients is often the most legible.
- For Instagram portrait posts use 4:5; for Stories/Reels use 9:16; for Twitter/X link card previews use 1.91:1.

## Troubleshooting
- **Fonts look wrong in exported PNG**: Wait a moment after changing fonts; the app waits for `document.fonts.ready` before capture.
- **CORS/tainted canvas error**: If embedding external images (not used by default), ensure they support CORS or host them locally.
- **Image looks soft on Retina/HiDPI**: The exporter uses an increased `scale`. You can increase it further in code (mind file size and performance).
- **Local file won’t load**: Try serving with a local static server (see Run section).

## Performance Notes
- The app avoids reflow-heavy operations and only re-renders on input changes.
- Export scale is capped for performance; raising it increases PNG size and render time.

## Accessibility
- Controls are keyboard-accessible; focus styles are present on swatches.
- Color choices are user-driven; prefer high-contrast combinations for legibility.

## Privacy
- All processing is done in-browser. No data leaves your device.

## Acknowledgements
- **Tailwind CSS** — Utility-first CSS via CDN.
- **html2canvas** — DOM to canvas rasterization.
- **Google Fonts** — High-quality, free font families.

## License
This project is released under the MIT License. You are free to use, modify, and distribute it with attribution.