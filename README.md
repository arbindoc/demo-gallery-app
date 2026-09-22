# Copilot in SharePoint Demonstrations

This repository contains a lightweight gallery app that showcases multiple AI-powered SharePoint demo scenarios as an interactive image walkthrough. Each demo is represented by a folder containing screenshots that walk through the solution flow from setup to insights, automation, and reporting.

## Overview

The gallery is a static HTML application that reads each demo folder, finds the images inside it, and renders them as a thumbnail gallery and slideshow experience. It is designed to present business scenarios and product walkthroughs without requiring a framework or backend.

## Included demo scenarios

The current gallery includes the following scenarios:

- Custom Image Tagger
- Invoice-PO Reconciliation
- Project Intelligence Engine
- RFP Proposal Engine
- NDA Compliance Engine
- Medicaid Formulary Drug
- Banking Economic Indicator

## Demo summaries

### Custom Image Tagger
A media-library workflow for automatically identifying and tagging images so they are easier to discover, filter, and manage in SharePoint.

### Invoice-PO Reconciliation
A finance scenario that demonstrates reconciling purchase order data with invoice details, highlighting exceptions and providing a structured review workflow.

### Project Intelligence Engine
A project analytics scenario that surfaces change events, root-cause analysis, and timeline-based insight dashboards from existing project documentation.

### RFP Proposal Engine
A proposal-generation and review workflow that automates creation, sourcing, review routing, and summarization for RFP processes.

### NDA Compliance Engine
A compliance scenario focused on validating NDA-related requirements and ensuring correspondence and documentation align with policy guidance.

### Medicaid Formulary Drug
A formulary and compliance scenario for reviewing drug data, comparing formulations, and generating decision-support information through an agent-driven experience.

### Banking Economic Indicator
A banking and market intelligence scenario for extracting key economic indicators, creating dashboards, and using an AI agent to generate client-facing summaries and briefings.

## Project structure

```text
demo-gallery-app/
├── README.md
├── index.html
├── galleries.js
├── manifest.json
├── generate-manifest.ps1
├── custom-image-tagger/
├── invoice-po-reconciliation/
├── medicaid-formulary-drug/
├── nda-compliance-engine/
├── project-intelligence-engine/
├── banking-economic-indicator/
├── rfp-proposal-engine/
└── .git/
```

## How the app works

The gallery is driven by a simple static front-end and auto-generated metadata:

- index.html renders the home gallery and slideshow interface
- manifest.json stores the title and description for each demo section
- generate-manifest.ps1 scans each folder, locates image files, and writes galleries.js
- galleries.js is the generated data file consumed by the page at runtime

Features in the UI include:

- expandable demo sections
- thumbnail-based browsing
- slideshow mode with previous/next navigation
- keyboard navigation with arrow keys
- Escape key to return to the gallery home
- expand/collapse all controls

## Run locally

This project does not require a build step.

### Option 1: open directly in a browser

```text
index.html
```

### Option 2: use a local web server

```bash
cd demo-gallery-app
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Update the gallery

When new demo content is added or existing screenshots are changed:

1. Add or replace image files inside the corresponding demo folder.
2. Update the metadata in manifest.json if the title or description needs to change.
3. Regenerate the gallery data with the PowerShell script.

```powershell
.\generate-manifest.ps1
```

This script scans all subfolders for supported image files and rebuilds galleries.js.

## Notes

- The app is intentionally lightweight and dependency-free.
- It is meant to showcase demos via screenshots and walkthrough visuals.
- Demo order is driven by the generated gallery data and folder names.

## License

This repository currently does not include a dedicated license file, so the project is being treated as an internal/demo artifact unless otherwise specified by the repository owner.
