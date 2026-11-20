# CART3R.JAILBREAK — Face Geometry (mobile web prototype)

A free, mobile-friendly facial geometry demo using HTML, CSS, JavaScript, and MediaPipe Face Landmarker. It reports a small set of approximate normalized 2D ratios and draws a landmark overlay. It does not produce attractiveness scores, identify people, diagnose conditions, or upload selected photos to an app server.

## Run from an Android phone

### Recommended: publish as a static website
1. Download and extract `cart3r-face-geometry-web.zip` on your phone.
2. In a browser, create a repository on GitHub and upload `index.html` (or use another static HTTPS host that supports plain HTML files).
3. For GitHub Pages: open the repository's **Settings → Pages**, choose deployment from the main branch and root folder, and save. Wait for the published HTTPS URL.
4. Open that URL in Chrome on Android. Tap **Choose an image**, select a photo, then tap **Analyze geometry**.
5. The first analysis needs an internet connection to load the MediaPipe JavaScript/WASM assets and face-landmark model. The photo processing happens locally in the browser after assets load.

### Local file limitations
Opening the HTML directly as `file://` may fail because browser module imports and model assets are subject to origin/security restrictions. Use HTTPS hosting for the most reliable phone-only setup. No build step or paid service is required for the prototype.

## Measurements
- Face aspect ratio: 2D distance between forehead/chin landmarks divided by the width between side-face landmarks.
- Eye distance: distance between outer eye landmarks, normalized by face width.
- Nose width: distance between two selected nose landmarks, normalized by face width.
- Mouth width: distance between mouth-corner landmarks, normalized by face width.
- Landmark count: number of points returned for the detected face.

These are pixel-scale-independent ratios, not physical dimensions. Head pose, camera perspective, expression, occlusion, crop, and detector variation affect them. They should not be interpreted as beauty, health, identity, or demographic assessments.

## Privacy
- Selected image is processed in-browser and is not sent to an application server by this code.
- The MediaPipe JS package, WASM files, and model are fetched from public CDNs/storage on first use; network providers may see ordinary asset requests.
- No analytics, login, database, or photo upload endpoint is included.
- Use only images you have permission to process. Clear the preview when finished, especially on shared devices.

## Troubleshooting
- **Model failed to load:** check internet access and reload the page.
- **No face detected:** use a well-lit, front-facing image with the full face visible.
- **Blank preview or picker issue:** try Chrome on Android and select a common JPG or PNG image under 15 MB.
- **HTTPS/origin errors:** publish the file on a static HTTPS host instead of opening it directly from the file manager.

## Files
- `index.html` — complete app, styles, and JavaScript in one file.
