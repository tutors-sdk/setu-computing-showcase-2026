# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Tutors-based course** showcasing SETU (South East Technological University) Computer Science undergraduate and postgraduate final year projects for 2026. It contains approximately 283 student projects organized by academic program and project category.

Tutors is an open-source platform that converts folder-based learning content into interactive web experiences. The content is authored in Markdown with YAML metadata, and a generator transforms it into JSON for web presentation.

## Content Structure

The repository follows a strict four-level hierarchy:

```
course.md (root - "SETU Undergraduate & Postgraduate Projects 2026")
├── topic-XX-program-name/           # Level 1: Academic Programs
│   ├── topic.md
│   ├── topic.png
│   └── unit-YY-category/            # Level 2: Project Categories
│       ├── unit.md
│       └── topic-ZZ-project/        # Level 3: Individual Projects
│           ├── topic.md             # Project title, student name, tech stack
│           ├── topic.png            # Project poster/image
│           ├── side-01-repos/       # Repository links
│           ├── unit-0-summary/      # Project summary (panelnote)
│           ├── unit-1-video/        # Demo video (panelvideo)
│           ├── unit-2-reports/      # Final report PDF & slides (talk)
│           └── unit-3-additional-resources/  # GitHub repos, etc.
```

### Key Structural Elements

**Topics (Programs):**
- `topic-00-hdip-in-computer-science` - Higher Diploma
- `topic-01-bsc-in-applied-computing` - BSc Applied Computing
- `topic-02-bsc-forensics-security` - BSc Forensics & Security
- `topic-03-bsc-creative-computing` - BSc Creative Computing
- `topic-04-bsc-it-management` - BSc IT Management
- `topic-05-bsc-software-systems` - BSc Software Systems
- `topic-06-msc-enterprise-software` - MSc Enterprise Software
- `topic-07-msc-information-systems` - MSc Information Systems

**Units (Categories):**
- `unit-01-web-apps` - Web Applications
- `unit-02-ai-ml` - AI/ML Projects
- `unit-03-cloud-devops` - Cloud & DevOps
- `unit-04-IoT` - Internet of Things
- `unit-05-full-stack` - Full Stack Development
- `unit-06-automation` - Automation Projects

**Individual Project Structure:**
Each project folder follows the naming pattern: `topic-NN-project-title-student-name`

Standard content components:
- `topic.md` - Title, student name, description, technologies
- `topic.png` - Project poster (often portrait orientation, may be scrollable)
- `side-01-repos/side.md` - "Project Resources" section with repository links
- `unit-0-summary/` - Contains `panelnote/` with project summary
- `unit-1-video/` - Contains `panelvideo-01-demo/` with demonstration video
- `unit-2-reports/` - Contains `talk-01-final-report-pdf/` and `talk-02-presentation-slides/`
- `unit-3-additional-resources/` - Additional resources like GitHub links

## Source Data

**sources/df_student_content.csv** - Master CSV containing all student project metadata including:
- Student details (name, ID, programme)
- Project titles (commercial and academic)
- Summaries, technologies, URLs
- Supervisor information
- Poster dimensions and orientation
- Project area classifications

**sources/posters-and-images/** - Original poster images and photos

## Building and Publishing

### Generate Tutors Course

```bash
deno run -A jsr:@tutors/tutors
```

This generates the `json/` folder containing the structured course data for the Tutors Reader.

### Generate Lightweight Static Version

```bash
deno run -A jsr:@tutors/tutors-lite
```

Generates `html/` folder for standalone deployment without the Tutors Reader application.

### Local Preview

After running tutors-lite, open `html/index.html` in a browser to preview the course locally.

## Tutors Platform Conventions

### Naming Conventions

Folder names encode resource types through **mandatory prefixes**:

- **topic-NN-name** - Top-level sections (programs or projects)
- **unit-NN-name** - Grouped resources within topics
- **side-NN-name** - Sidebar resources (not in main flow)
- **talk-NN-name** - PDF presentations/documents
- **book-NN-name** - Multi-step labs
- **note-NN-name** - Single web pages
- **panelvideo-NN-name** - Full-width embedded videos
- **panelnote-NN-name** - Full-width markdown content
- **paneltalk-NN-name** - Full-width PDF displays
- **github-NN-name** - GitHub repository links
- **web-NN-name** - External website links
- **archive-NN-name** - Downloadable ZIP files

**Always use hyphens, never spaces.** The NN prefix ensures proper sorting order.

### Required Files Per Resource Type

**Talk (PDF):**
- `name.md` - Title and description
- `name.pdf` - The PDF file
- `name.png` - Card image (optional if using icon in frontmatter)

**Panelvideo (Embedded Video):**
- `video.md` - Title
- `videoid` - File containing YouTube video ID or `heanet=ID`

**Panelnote (Full-width Markdown):**
- `note.md` - Markdown content
- `img/` - Optional images folder
- `archives/` - Optional downloadables

**GitHub Link:**
- `github.md` - Title and description
- `githubid` - File containing full GitHub repository URL
- `github.png` - Card image (optional)

**Side (Sidebar Resource):**
- `side.md` - Markdown content

### FrontMatter Configuration

Add YAML frontmatter to markdown files for custom styling:

```yaml
---
order: 1
icon:
  type: vscode-icons:file-type-pdf2
  color: green
---
```

Use Iconify icons instead of PNG images. Search at https://icon-sets.iconify.design/

### Video Integration

For YouTube videos, extract the video ID from the URL:
- URL: `https://www.youtube.com/watch?v=Hfw1lbErjws`
- ID: `Hfw1lbErjws`

Place the ID in a `videoid` file within the panelvideo resource folder.

For HEANet hosted videos (privacy-conscious):
```
heanet=7e4f1e9afedb40d5996d0703702eaaa4
```

## Configuration Files

**properties.yaml** (root level) - Course metadata:
```yaml
credits: SETU Computer Science Department
```

Optional properties that may be relevant:
- `icon` - SVG icon from Iconify
- `auth: 1` - Enable GitHub authentication
- `ignorepin: NNNN` - PIN-protect hidden topics
- `ignore: [topic-name]` - Hide topics from students
- `labStepsAutoNumber: true` - Auto-number lab steps
- `llm: 2` - Advertise LLM-friendly content routes
- `portfolio: true` - Hide breadcrumbs for portfolio view

**course.md** (root level) - Course title and description

## Working with This Repository

### Adding New Projects

When adding a new student project:

1. Create folder following naming pattern: `topic-NN-project-title-student-name/`
2. Create required structure:
   - `topic.md` with project title, student name, description, technologies
   - `topic.png` (poster image)
   - `side-01-repos/side.md` (repository links)
   - `unit-0-summary/panelnote/note.md` (project summary)
   - `unit-1-video/panelvideo-01-demo/` (demo video if available)
   - `unit-2-reports/talk-01-final-report-pdf/` (final report)
   - `unit-2-reports/talk-02-presentation-slides/` (presentation)
3. Update `sources/df_student_content.csv` if using automated generation

### Modifying Existing Projects

- Always maintain the naming conventions
- PDFs go in `talk-NN-name/` folders with corresponding `.md` file
- Videos require a `videoid` file with the YouTube or HEANet ID
- Images should be placed in resource-specific `img/` folders

### Image Optimization

Resize images appropriately before adding. Poster images are often portrait orientation (e.g., 1587x2245 pixels) and may use scroll functionality for tall posters.

Use https://nodeca.github.io/pica/demo for responsive image resizing.

## Git Workflow

The `json/` folder is git-ignored (generated output). Only commit source content:
- Markdown files (`.md`)
- Images (`.png`, `.jpg`)
- PDFs (`.pdf`)
- Metadata files (`videoid`, `githubid`, `properties.yaml`)

## Common Patterns in This Repository

### Project Topic Structure

Every project's `topic.md` follows this pattern:
```markdown
Project Title

**Student Name**: Brief description — Technologies used.
```

Example:
```markdown
DrillTek

**Joshua Smiles**: Borehole management for diamond drilling — Svelte, Django REST, PostgreSQL.
```

### Repository Links

The `side-01-repos/side.md` typically contains just:
```markdown
Project Resources

```

Actual repository links are in `unit-3-additional-resources/github-NN-name/` folders.

### Summary Pattern

Project summaries in `unit-0-summary/panelnote/note.md` are typically full-width markdown descriptions of the project goals, approach, and outcomes.

## Accessibility Notes

- Use descriptive alt text for images in markdown
- Ensure proper heading hierarchy (h1 → h2 → h3)
- Color choices should support colorblind users
- Tutors platform handles responsive design automatically

## Deployment Targets

This course can be deployed to:
- **Netlify** - Recommended for Tutors Reader
  - Build command: `deno run -A jsr:@tutors/tutors`
  - Publish directory: `json`
- **Vercel** - Requires public repository for free tier
- **GitHub Pages** - Use tutors-lite for static HTML
- **Any static host** - Use tutors-lite HTML output

## Resources

- **Tutors Documentation (LLM Friendly)**: https://tutors-reference-manual.netlify.app/llms/tutors-reference-manual-complete-llms.txt
- **Iconify Icon Sets**: https://icon-sets.iconify.design/
- **Image Resizer**: https://nodeca.github.io/pica/demo
