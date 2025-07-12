# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a resume generation project that transforms Jonathan Crissey's resume from a static HTML file into a modular, data-driven system. The goal is to create a backend that generates resumes from YAML content definitions and supports multiple layouts/designs.

## Architecture

The project is evolving from a single static HTML file (`jc_resume.html`) into a modular system with these planned components:

- **Data Layer**: YAML files defining resume content (personal info, experience, skills, education)
- **Template Engine**: System to process YAML data and generate HTML/CSS output
- **Layout System**: Multiple design templates that can be applied to the same content
- **Build Process**: Automation to generate different resume versions

## Current State

The project has been successfully modularized into a YAML-based system:

- **Data Layer**: `resume-data.yml` contains all resume content in structured format
- **Layout System**: `layout-config.yml` defines styling, colors, typography, and layout structure
- **Two Generation Approaches**:
  - `js-render/`: Client-side JavaScript that loads YAML dynamically
  - `python-build/`: Static site generator that creates self-contained HTML
- **Profile Image**: Properly integrated with relative paths in both systems

## Key Design Elements

- **Profile image**: Referenced via local path, needs to be handled in modular system
- **Color scheme**: Dark slate sidebar with professional contrast
- **Typography**: Helvetica Neue font stack with precise sizing for print layout
- **Structure**: 35% sidebar / 65% main content split
- **Print optimization**: Specific media queries for clean printing

## Development Commands

### JavaScript Renderer
```bash
python3 -m http.server 8000
# Open http://localhost:8000/resume-viewer.html
```

### Python Generator
```bash
pip install -r requirements.txt
python3 build_resume.py
# Creates resume-output.html
```

## Planned Features

### Additional Layout Themes (TODO)
- `layout-modern.yml` - Clean, minimalist design with larger typography
- `layout-creative.yml` - Bold colors and asymmetric layout
- `layout-minimal.yml` - Ultra-clean single column or sparse two-column

### Web-Based Editor (TODO)
- Create `resume-editor.html` for updating resume data via web form
- Form should load existing `resume-data.yml` and allow editing
- On save, create backup of existing file (e.g., `resume-data-2025-06-30.yml`)
- Real-time preview of changes using existing JavaScript renderer
- Validation of YAML structure before saving

### AI-Powered Resume Builder Pipeline (FUTURE)
**Vision:** Transform resume creation from a tedious manual process into an intelligent, guided experience that extracts and organizes professional information automatically.

#### Core AI Pipeline Components
- **Document Intelligence Engine**: Upload and parse PDFs, images, certificates, project documentation
- **Skills & Experience Extraction**: AI analysis of uploaded documents to automatically populate resume sections
- **Intelligent Content Generation**: AI-assisted writing for profile summaries, job descriptions, and achievement bullets
- **Conversational Resume Builder**: Chat-based interface that guides users through structured questions
- **Text-to-Speech Integration**: Voice-enabled interaction for accessibility and hands-free resume building

#### Technical Architecture
- **Frontend**: React-based web interface with drag-and-drop upload zones
- **Backend**: Node.js/Python API with AI model integration (OpenAI, Claude, or local models)
- **Document Processing**: OCR and NLP pipelines for text extraction and analysis
- **Voice Interface**: Web Speech API integration for text-to-speech capabilities
- **Data Pipeline**: Automated YAML generation from extracted and user-provided information

#### User Experience Flow
1. **Upload Phase**: Users upload existing resumes, certificates, project screenshots, or documents
2. **AI Analysis**: System extracts skills, experiences, education, and achievements automatically
3. **Guided Interview**: Chat interface asks targeted questions to fill gaps and gather context
4. **Content Enhancement**: AI suggests improvements to descriptions and identifies missing elements
5. **Template Selection**: Choose from multiple layouts and styling options
6. **Real-time Preview**: Live preview with instant updates as information is refined
7. **Export Options**: Generate PDF, HTML, or share via GitHub Pages

#### Benefits
- **Removes Complexity**: Eliminates the intimidation factor of starting from a blank resume
- **Saves Time**: Automatic extraction reduces manual data entry by 80%
- **Improves Quality**: AI-suggested content improvements and professional phrasing
- **Accessibility**: Voice interface makes resume building accessible to users with different abilities
- **Continuous Updates**: Easy maintenance and updates as career progresses

## Content Structure

The resume includes standard sections:
- Contact information and profile image
- Education (B.S. Computer Science, UTSA 2007)
- Technical skills (categorized by domain)
- Professional experience (18 years, primarily IBM)
- Personal interests

Skills are organized by categories:
- Languages & Dev Tools
- Cloud & Automation  
- Mobile & Web Development
- Infrastructure & Systems