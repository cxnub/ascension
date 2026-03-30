# Ascension

A browser-based tool for calculating your **facial width-to-height ratio (fWHR)** and **midface ratio** from a selfie. No uploads, no servers — everything runs locally in your browser using MediaPipe Face Mesh.

## Live Demo

[**cxnub.github.io/ascension**](https://cxnub.github.io/ascension)

## Measurements

### fWHR (Facial Width-to-Height Ratio)
Bizygomatic width divided by upper face height (eyelid or eyebrow to upper lip).
- **< 1.6** — Below average (narrow)
- **1.7 - 1.8** — Population average
- **> 2.0** — Above average (wide)

### Midface Ratio
Interpupillary distance (IPD) divided by the vertical distance from the pupil line to the upper lip.
- **< 0.85** — Long midface
- **~1.0** — Ideal / balanced
- **> 1.05** — Short / compact midface (currently favored in aesthetics)

## Features

- Drag-and-drop or browse to upload a face photo
- Real-time facial landmark detection via [MediaPipe Face Mesh](https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker)
- Overlay visualization: fWHR box (purple), IPD line (green), pupil-to-lip line (dashed)
- Configurable top line (eyelid vs eyebrow) and left/right averaging
- 100% client-side — no images leave your device

## Usage

Open `index.html` in any modern browser, or serve it locally:

```sh
python -m http.server 8080
```

Then visit `http://localhost:8080`.

## Tech Stack

Single HTML file. No build step, no dependencies to install.

- **MediaPipe Face Mesh** (468-point landmark model, loaded from CDN)
- **Canvas API** for drawing measurement overlays

## Tips for Accurate Results

- Use a front-facing photo with neutral expression
- Good, even lighting
- No sunglasses or heavy obstructions
- The app will warn you if the face appears angled
