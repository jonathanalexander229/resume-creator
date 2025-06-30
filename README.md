# Resume Creator

A modular resume generation system that creates professional resumes from YAML data files with configurable layouts and themes.

## Quick Start

Choose one of two approaches:

### Option 1: JavaScript Renderer (Live Preview)
```bash
python3 -m http.server 8000
```
Then open: http://localhost:8000/resume-viewer.html

**Features:**
- Live YAML loading and rendering
- Reload button to refresh changes
- Dynamic CSS generation from layout config
- No build step required

### Option 2: Python Generator (Static Files)
```bash
pip install -r requirements.txt
python3 build_resume.py
```
This creates `resume-output.html` - a self-contained file with embedded CSS.

**Features:**
- Static HTML generation
- Self-contained output file
- Programmatic customization
- Perfect for CI/CD or batch processing

## File Structure

- `resume-data.yml` - Your resume content (experience, skills, education)
- `layout-config.yml` - Layout configuration (colors, fonts, spacing, structure)
- `resume-viewer.html` - JavaScript client-side renderer
- `build_resume.py` - Python static generator
- `IMG_4428.jpeg` - Profile image

## Creating New Layouts

1. Copy `layout-config.yml` to `layout-modern.yml` (or any name)
2. Modify colors, typography, spacing as desired
3. Both renderers can use the new layout configuration

The YAML-based approach makes it easy to create multiple resume themes while keeping your content separate from presentation.