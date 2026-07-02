# Video Watermark Remover (Web)

AI-powered video watermark removal, runs entirely in your browser. No uploads, no server needed.

## Features

- **Privacy-first**: All processing happens locally in your browser
- **LaMa AI**: Uses Large Mask Inpainting for high-quality watermark removal
- **Pure static**: Single HTML file + ONNX model, deploy anywhere

## How to Use

1. Open `index.html` in a modern browser (Chrome/Edge recommended)
2. Click "Load LaMa Model" to load the AI model (~88MB, cached after first load)
3. Open a video file (drag & drop or click)
4. Drag on the video to select the watermark area
5. Click "Start Processing"
6. Download the cleaned video

## Deploy to GitHub Pages

1. Push this repo to GitHub:
```bash
git init
git lfs install
git lfs track "model/*.onnx"
git add .
git commit -m "Video watermark remover web app"
git remote add origin https://github.com/YOUR_USERNAME/video-dewatermark-web.git
git push -u origin main
```

2. Enable GitHub Pages:
   - Go to repo **Settings** > **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **root**
   - Save

3. Your app will be available at:
   `https://YOUR_USERNAME.github.io/video-dewatermark-web/`

## Tech Stack

- **ONNX Runtime Web**: In-browser ML inference (WebGPU / WebAssembly)
- **Canvas API**: Video frame extraction and display
- **MediaRecorder API**: Output video encoding
- **LaMa Model**: Deep learning inpainting (ONNX format, 88MB)

## Browser Compatibility

- Chrome/Edge 113+ (WebGPU, best performance)
- Firefox 120+
- Safari 17+

Falls back to WebAssembly (WASM) on browsers without WebGPU support.

## Limitations

- Large videos (>1080p) may be slow in browser
- First load downloads the model (~88MB), then cached
- Processing speed depends on device GPU/CPU
