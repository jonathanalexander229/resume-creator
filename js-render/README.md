# JavaScript Resume Viewer

## Running the Resume Viewer

Due to browser security restrictions (CORS), you cannot open the HTML file directly. You need to serve it from a local HTTP server.

```bash
cd js-render
python3 -m http.server 8000
```

Then open: http://localhost:8000/resume-viewer.html

## Features
- Live YAML loading and rendering
- Reload button to refresh changes
- Print-optimized styling
- Dynamic CSS generation from layout config