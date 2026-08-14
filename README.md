# Copilot in SharePoint Demonstrations Gallery

A curated gallery showcasing practical AI-powered solutions built with Copilot capabilities in SharePoint. This project demonstrates real-world automation and intelligence scenarios that enhance document processing, project management, and business workflows.

## Overview

The Demo Gallery App is an interactive web-based gallery that displays four transformative Copilot in SharePoint demonstrations. Each demo includes step-by-step visual walkthroughs showing how AI can streamline complex business processes.

## Features

- **Interactive Gallery Interface** - Clean, modern dark-themed UI for browsing demonstrations
- **Collapsible Demo Sections** - Expand/collapse each demo to view detailed image sequences
- **Auto-Generated Manifest** - PowerShell script automatically generates gallery metadata from image files
- **Responsive Design** - Works seamlessly on desktop and mobile devices
- **No External Dependencies** - Pure HTML, CSS, and JavaScript implementation

## Demonstrations

### 1. Custom Image Tagger
**AI-powered image identification and categorization**

Automatically identify and tag images in your media library using computer vision AI. The solution:
- Analyzes images to extract meaningful tags and categories
- Updates SharePoint list columns with auto-generated metadata
- Enables advanced search and filtering based on visual content
- Supports background object detection for more intelligent categorization

**Use Case:** Organize large media libraries without manual tagging

---

### 2. Invoice-PO Reconciliation
**Intelligent invoice and purchase order matching**

Automates the reconciliation process between invoices and purchase orders to ensure financial accuracy. The solution:
- Extracts key data from purchase order documents (vendor, amount, line items)
- Extracts invoice details for comparison
- Identifies discrepancies and exceptions
- Provides a tracking dashboard view for reconciliation status
- Generates live HTML dashboards for real-time monitoring

**Use Case:** Streamline accounts payable processes and catch discrepancies early

---

### 3. Project Intelligence Engine
**Structured retrospective analysis for project documents**

Performs deep analysis on documents your delivery teams already produce to surface hidden insights. The solution includes three core AI skills:

- **Change Event Extraction** - Automatically identifies and logs all change events from project documentation
- **Root Cause Analysis** - Connects events to their underlying causes and contributing factors
- **Timeline Dashboard** - Visualizes the sequence of events, interventions, and causal chains

The system:
- Processes project status reports, meeting notes, and team documents
- Surfaces causal chains and dependencies between events
- Identifies intervention windows and early warning signals
- Provides governance gap analysis and recommendations

**Use Case:** Transform project documentation into actionable intelligence for better delivery outcomes

---

### 4. RFP Proposal Engine
**Intelligent Request for Proposal generation and review**

Automates the creation and review of RFP documents with AI assistance. The solution:
- Generates RFPs from predefined templates and project requirements
- Reviews RFP documents for completeness and clarity
- Tracks RFP status and responses
- Sources content intelligently based on organizational knowledge
- Cascades reviews through appropriate approval workflows
- Produces comprehensive RFP summaries

**Use Case:** Accelerate the RFP process from creation to response management

---

## Project Structure

```
demo-gallery-app/
├── README.md                      # This file
├── index.html                     # Main gallery interface
├── galleries.js                   # Auto-generated gallery manifest
├── manifest.json                  # Demo metadata and descriptions
├── generate-manifest.ps1          # PowerShell script to generate galleries.js
├── custom-image-tagger/           # Demo images (5 screenshots)
├── invoice-po-reconciliation/     # Demo images (10 screenshots)
├── project-intelligence-engine/   # Demo images (16 screenshots)
└── rfp-proposal-engine/           # Demo images (6 screenshots)
```

## Getting Started

### Prerequisites
- A modern web browser (Chrome, Edge, Firefox, Safari)
- No installation or server required

### Running the Gallery

1. **Local File Access**: Open `index.html` directly in your web browser
   ```bash
   # On Windows
   start index.html
   
   # On macOS
   open index.html
   
   # On Linux
   xdg-open index.html
   ```

2. **Via Local Server** (recommended for development):
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (with http-server)
   npx http-server
   ```
   Then navigate to `http://localhost:8000` in your browser.

3. **Browse the Gallery**
   - Click on any demo section to expand it
   - Images load sequentially showing the demonstration flow
   - Use the action buttons in the header to navigate or reset

## Updating the Gallery

### Adding New Demonstrations

To add a new demo to the gallery:

1. **Create a Demo Folder**
   ```
   demo-gallery-app/[demo-name]/
   ```

2. **Add Screenshots**
   - Place numbered screenshots in the folder (e.g., `00 - Intro.png`, `01 - Step One.png`)
   - Use descriptive, zero-padded names for proper sorting

3. **Update manifest.json**
   ```json
   "[demo-folder-name]": {
     "title": "Your Demo Title",
     "description": "Clear description of what this demo shows."
   }
   ```

4. **Auto-Generate galleries.js**
   ```powershell
   .\generate-manifest.ps1
   ```
   The script will:
   - Scan all demo folders
   - Generate image file lists
   - Update `galleries.js` automatically

5. **Verify in Browser**
   - Refresh the gallery page
   - Your new demo should appear as a collapsible section

### Modifying Existing Demos

- **Update Title/Description**: Edit `manifest.json`
- **Replace/Add Images**: Add or replace PNG files in the demo folder with zero-padded names
- **Regenerate Manifest**: Run `generate-manifest.ps1`

## Technical Details

### Architecture

- **Frontend**: Vanilla HTML5, CSS3, and JavaScript (no frameworks)
- **Styling**: CSS Grid layout with flexbox for responsive design
- **Generation**: PowerShell script for automated manifest generation
- **Data Format**: JSON-based configuration (manifest.json → galleries.js)

### Key Files

| File | Purpose |
|------|---------|
| `index.html` | Main UI component - renders gallery interface and handles interactivity |
| `galleries.js` | Auto-generated manifest - contains all demo metadata and image paths |
| `manifest.json` | Source configuration - demo titles and descriptions |
| `generate-manifest.ps1` | Build script - generates galleries.js from folder structure |

### Browser Compatibility

- Modern browsers (2020+): Full support
- Internet Explorer: Not supported
- Mobile browsers: Responsive design supported

## Workflow

### Development Cycle

```
Create/modify images
         ↓
Update manifest.json (if adding new demo)
         ↓
Run generate-manifest.ps1
         ↓
Refresh browser to verify changes
         ↓
Commit changes to version control
```

## Customization

### Styling

Modify the `<style>` section in `index.html` to customize:
- Color scheme (currently dark theme)
- Typography and spacing
- Layout (grid columns, gap sizes)
- Animation and hover effects

### Image Handling

- Images are lazy-loaded for better performance
- Supported formats: PNG, JPG, GIF, WebP
- Recommended size: Optimize for web to keep file sizes reasonable

## Tips for Effective Demonstrations

1. **Screenshot Naming**: Use descriptive, numbered names (e.g., `00 - Overview`, `01 - Data Entry`, `02 - Results`)
2. **Image Quality**: Use high-quality screenshots (1920x1080 recommended) that are web-optimized
3. **Flow**: Arrange images sequentially to tell a clear story
4. **Description**: Write concise descriptions that explain the use case and value

## Version History

- **v1.0** - Initial release with four core demonstrations
  - Custom Image Tagger
  - Invoice-PO Reconciliation
  - Project Intelligence Engine
  - RFP Proposal Engine

## Contributing

To add or update demonstrations:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-demo`)
3. Add or modify demo content and images
4. Update `manifest.json` with metadata
5. Run `generate-manifest.ps1` to update `galleries.js`
6. Test in browser to verify functionality
7. Commit with clear messages: "Add [Demo Name] demonstration"
8. Push and open a pull request

## License

This project is proprietary. All demonstrations and content are confidential.

## Support

For issues, questions, or demo additions:
- Check the project structure matches the expected format
- Verify `generate-manifest.ps1` ran successfully
- Clear browser cache if images don't update
- Ensure image file names follow the `NN - Description` pattern

---

**Last Updated:** August 2026

**For Questions:** Contact the demo content maintainers
