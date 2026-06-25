# printing-pdf — Coloring Book PDF Maker

A simple, single-page tool to turn a batch of images into a **print-ready, single-sided PDF**
for a coloring book. Drop in your images, configure the print size, and download.

Everything runs **100% in your browser** — your images are never uploaded to any server.

## What it does

- **Drag & drop** any number of images (PNG, JPG, WebP, GIF).
- **Centers** each image on its page.
- Adds a configurable **border** around each image.
- Leaves **margin / bleed space** around the image.
- Picks the right page **scale** from a print size you choose (US Letter, A4, Legal, Tabloid, A3, A5, square).
- **Single-sided layout**: image on page 1, blank page 2, next image on page 3, blank page 4, … —
  so the backs stay empty (perfect for coloring books).
- **Preview** the PDF inline, then **Download** it.

## Use it

### Option A — just open the file
Double-click `index.html` (or open it in any modern browser). That's it. Needs an internet
connection the first time so it can load the PDF library from a CDN.

### Option B — run a local server (recommended for repeat use)
```bash
cd printing-pdf
python3 -m http.server 8000
# then open http://localhost:8000
```

## Settings

| Setting | What it controls |
|---|---|
| **Print size** | Page dimensions (US Letter, Legal, Tabloid, A3, A4, A5, Square). |
| **Orientation** | Portrait, Landscape, or Auto (match each image's shape). |
| **Units** | Inches or millimeters for the margin / border gap fields. |
| **Margin / bleed space** | Whitespace kept between the page edge and the image. |
| **Border** | Toggle, width (in points), and color of the frame around each image. |
| **Border gap** | Space between the image and the border line. |
| **Single-sided** | Inserts a blank page after each image (on by default). |
| **Image quality** | Downscales large images to a target DPI to keep the PDF small (300 DPI default). |
| **File name** | Name of the downloaded PDF. |

Tip: name your source files `01.png`, `02.png`, … and use **Sort by name** so pages land in
order. You can also drag thumbnails to reorder, or click **×** to remove one.

## Hosted on GitHub Pages

Live at **https://chloezql.github.io/printing-pdf/**

Pages is configured to **deploy from a branch** (`main`, root folder). To update the
live site, just push to `main` — GitHub rebuilds it automatically within a minute:

```bash
git add -A
git commit -m "Update tool"
git push
```

## Tech

Plain HTML/CSS/JS, no build step. PDF generation via
[jsPDF](https://github.com/parallax/jsPDF) (loaded from a CDN).
