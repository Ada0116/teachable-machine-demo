# Little Vision Lab

A browser-based image classification website powered by a trained Google Teachable Machine model. It recognizes **person**, **hand**, **candy**, and **phone**, with a different message for each class and live confidence bars.

## Run locally

1. Download or clone this repository.
2. Open the folder in Visual Studio Code and install the **Live Server** extension.
3. Right-click `index.html` and select **Open with Live Server**.
4. Click **Start camera** and allow camera access in your browser.

Alternatively, with Python 3 installed, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000`.

Use a local web server rather than opening the HTML file directly. An internet connection is required to load TensorFlow.js and the Teachable Machine image library from the CDN. Camera access requires localhost or HTTPS.

## Model files

The trained model is included in this repository:

- `model.json` — model architecture and weights manifest
- `metadata.json` — class labels and model metadata
- `weights.bin` — trained model weights

Keep these files next to `index.html`. The page loads them using `const URL = './';`.

## How it works

The model runs in the browser. Feedback changes when a class reaches at least 80% confidence for approximately 0.65 seconds. Show one subject at a time in good lighting for more stable results. Predictions can be incorrect.

Camera frames are processed locally by this page and are not uploaded or saved. Click **Stop** to turn off the camera.
