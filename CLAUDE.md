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

Currently no build system exists. Future development will likely include:
- YAML parsing and validation
- Template rendering system
- Static site generation or build process
- CSS/styling pipeline for multiple themes

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