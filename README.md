# Face Geometry App — mobile update

A single-file HTML/CSS/JavaScript prototype for Android browsers.

## Features
- Black/crimson responsive interface
- Select a photo or capture a frame using the phone camera
- On-device MediaPipe Face Landmarker processing
- Approximate normalized geometry measurements
- Text report download and browser print / Save as PDF
- Clear button and no application photo-upload endpoint

## Publish from a phone using GitHub
1. Open your repository: https://github.com/sofamaroc55-lgtm/face-geometry-app
2. Tap `index.html`.
3. Tap the pencil/Edit icon.
4. Select all existing code and replace it with the contents of the new `index.html`.
5. Scroll down to **Commit changes**, enter a message such as `Upgrade mobile analyzer`, then commit to `main`.
6. Open **Settings → Pages**. Under Build and deployment, select **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
7. Wait for the Pages deployment, then open the published HTTPS URL in Chrome on Android.
8. Test photo selection first, then camera permission, analysis, report download, print, and Clear.

## Notes
- First analysis needs internet to download the MediaPipe runtime and model.
- Photo pixels are processed locally by the page; ordinary network requests still occur to download the public model/runtime.
- Camera access normally requires HTTPS or localhost.
- Measurements are approximate 2D ratios and are not physical measurements or a beauty/health rating.
