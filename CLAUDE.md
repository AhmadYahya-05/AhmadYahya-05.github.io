# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a single-file personal portfolio website — pure HTML/CSS/JavaScript with no build tools, no framework, and no package manager. Everything lives in `index.html`.

**Live site**: https://ahmadyahya-05.github.io/
**Repository**: https://github.com/AhmadYahya-05/AhmadYahya-05.github.io

## Development

**To run locally**: Open `index.html` in a browser, or use the VS Code Live Server extension on port 5501.

No build, lint, or test commands exist — there is no build step.

## Architecture

`index.html` is organized into three logical blocks:

1. **CSS (lines ~12–766)** — All styles inline in a `<style>` tag. Uses CSS custom properties for the dark theme (navy background `#0f172a`, blue accent `#3b82f6`). Responsive breakpoints at 768px and 1000px.

2. **HTML (lines ~768–1001)** — Five sections: `#home` (hero + terminal), `#projects` (card grid), `#contact` (Formspree form + social links), footer (QR code), and a video modal overlay.

3. **JavaScript (lines ~1004–1410)** — All scripts inline in a `<script>` tag at the bottom. Key subsystems:
   - **Projects array** — drives card rendering and modal video playback
   - **Terminal emulator** — accepts commands (`help`, `cd projects`, `cd contact`) with history and ANSI color support
   - **QR code** — generated client-side via `qrcode.min.js` with fallback to the QR Server API
   - **Logo easter egg** — emoji carousel on click

## External Dependencies (CDN only)

- FontAwesome 6.0.0 — icons
- Google Fonts (Inter)
- QRCode.js v1.5.3 — QR generation
- Formspree — contact form submissions

## Deployment

Pushing to `main` deploys automatically via GitHub Pages. No CI pipeline.
