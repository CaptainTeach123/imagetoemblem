# Relief Forge

A zero-install browser app that converts ornamental 2D artwork into a watertight, printable relief and exports it as a binary STL.

## Use

Open `index.html` through GitHub Pages or any static web server. Upload an image, select a detection mode, adjust the preview, enter the desired dimensions, and choose **Export STL**.

For textured or colored backgrounds, choose **Remove sampled background** and click a representative background area in the uploaded image. The app samples the four corners automatically on upload.

## What it does

- Runs entirely in the browser; images are never uploaded.
- Automatically detects bilateral emblems and rejects unmatched background texture.
- Removes small disconnected noise with an adjustable component-size filter.
- Supports sampled-background, metallic, and light/dark detection modes.
- Traces the raster mask into sub-pixel vector contours at up to 900 px resolution.
- Smooths curves geometrically while preserving meaningful disconnected pieces, internal openings, and open-ended strokes.
- Uses continuous-field edge smoothing to remove pixel stair-steps without repeatedly rounding sharp ornamental tips.
- Builds exact-thickness front/back surfaces and a ten-segment bevel around outer edges and every internal cutout.
- Provides an interactive Three.js preview and binary STL export.

## Printing notes

The generated model is a flat-backed relief. Import it into your slicer in millimeters. A 2–4 mm thickness is a useful starting point for badges and decorative emblems. Source artwork with a clear silhouette produces the best result.

## Development

No build step is required. The viewer loads Three.js as an ES module from jsDelivr, so an internet connection is required for the 3D preview.

