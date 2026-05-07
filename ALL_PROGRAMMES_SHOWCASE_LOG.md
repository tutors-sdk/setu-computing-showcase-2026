# SETU All Programmes Showcase 2026 - Creation Log

## Date: 2026-05-07

## Overview

Created a comprehensive Tutors course showcase for **all SETU undergraduate and postgraduate programmes**, containing 104 student final year projects across 7 programmes.

## Structure

```
bsc-applied-computing-showcase-2026/
├── properties.yaml
├── course.md
├── topic-01-bsc/                          (BSc Applied Computing - 33 projects)
├── topic-02-bsc-forensics-security/       (BSc Forensics & Security - 8 projects)
├── topic-03-bsc-creative-computing/       (BSc Creative Computing - 6 projects)
├── topic-04-bsc-it-management/            (BSc IT Management - 5 projects)
├── topic-05-bsc-software-systems/         (BSc Software Systems - 19 projects)
├── topic-06-msc-enterprise-software/      (MSc Enterprise Software - 17 projects)
└── topic-07-msc-information-systems/      (MSc Information Systems - 16 projects)
```

## Programme Breakdown

### 1. BSc in Applied Computing (33 students)
**Topic:** topic-01-bsc

**Units:**
- unit-01-games (2 projects)
- unit-02-ai-ml (28 projects)
- unit-04-cloud-devops (1 project)
- unit-05-web-apps (2 projects)

### 2. BSc in Computer Forensics and Security (8 students)
**Topic:** topic-02-bsc-forensics-security

**Units:**
- unit-02-ai-ml (6 projects)
- unit-03-security (2 projects)

### 3. BSc in Creative Computing (6 students)
**Topic:** topic-03-bsc-creative-computing

**Units:**
- unit-02-ai-ml (6 projects)

### 4. BSc in Information Technology Management (5 students)
**Topic:** topic-04-bsc-it-management

**Units:**
- unit-02-ai-ml (4 projects)
- unit-05-web-apps (1 project)

### 5. BSc in Software Systems Development (19 students)
**Topic:** topic-05-bsc-software-systems

**Units:**
- unit-01-games (2 projects)
- unit-02-ai-ml (13 projects)
- unit-03-security (1 project)
- unit-05-web-apps (3 projects)

### 6. MSc in Enterprise Software Systems (17 students)
**Topic:** topic-06-msc-enterprise-software

**Units:**
- unit-02-ai-ml (14 projects)
- unit-03-security (1 project)
- unit-06-mobile (2 projects)

### 7. MSc in Information Systems Processes (16 students)
**Topic:** topic-07-msc-information-systems

**Units:**
- unit-02-ai-ml (14 projects)
- unit-06-mobile (1 project)
- unit-07-other (1 project)

## Hierarchy Structure

```
Programme Topic
└── Unit (themed category)
    └── Project Topic (individual student)
        ├── topic.md                    (Commercial title + summary)
        ├── topic.jpeg                  (Poster image)
        ├── side-01-repos/
        │   └── web-01-project-page/
        │       ├── project-page.md
        │       ├── project-page.jpeg   (Student profile)
        │       └── weburl
        ├── unit-0-summary/
        │   ├── topic.md
        │   └── panelnote/
        │       ├── node.md             (Abstract + details table)
        │       └── img/
        │           └── poster.jpeg
        └── unit-3-additional-resources/
            └── panelnote/              (Centered poster)
                ├── note.md
                └── img/
                    └── poster.jpeg
```

## Project Categorization

Projects were automatically categorized into thematic units based on keywords:

- **AI/ML**: ai, machine learning, ml, neural, deep learning, llm, classifier
- **Security**: security, malware, ids, vulnerability, attack, defense, forensic, cyber
- **Games**: game, unity, vr, virtual, roguelite, gameplay
- **Cloud/DevOps**: cloud, kubernetes, devops, docker, infrastructure, deployment
- **Web Apps**: web, react, frontend, backend, full stack, api
- **Mobile**: mobile, android, ios, app
- **Other**: Projects not matching above categories

## Summary Statistics

- **Total Programmes**: 7
- **Total Units**: 19
- **Total Projects**: 104
- **Total Images**: ~200+ (posters and profile images)
- **Total Files**: ~1,500+

## Data Sources

- **CSV**: `/Users/edeleastar/repos/hdip/2024/df_student_content.csv`
- **Images**: `/Users/edeleastar/repos/hdip/2024/posters-and-images/`
  - student_posters/
  - student_images/

## Features Implemented

### ✅ Hierarchical Organization
- Top-level programme topics
- Thematic units within each programme
- Individual project topics

### ✅ Complete Project Structure
- Commercial title format in topic.md
- Poster images in topic root
- Student profile images in sidebar
- Comprehensive panelnotes with abstracts and tables
- Centered poster displays in unit-3

### ✅ Consistent Pattern
- All 104 projects follow identical structure
- Automated categorization
- Professional formatting throughout

### ✅ Resource Links
- Project landing pages integrated
- Student profile images in web-01-project-page

## Excluded Elements

The following were **not** included (following BSc showcase pattern):
- ❌ NotebookLM/LLM links (web-00-llm folders removed)
- ❌ Video presentations (unit-1-video removed)
- ❌ Reports and slides (unit-2-reports removed)
- ❌ GitHub repositories

## Files Created

- **Programme Topics**: 7 top-level folders
- **Units**: 19 themed unit folders
- **Project Topics**: 104 individual project folders
- **Panelnotes**: 104 summary panelnotes with abstracts
- **Images**: ~200 poster and profile images
- **Total**: ~1,500+ files

## Scripts Created

1. `create_all_programmes_showcase.py` - Main automation script
   - Loads data from df_student_content.csv
   - Categorizes projects by theme
   - Creates complete structure for all programmes
   - Copies images and creates all content files

## Next Steps

### Testing
1. Generate Tutors course: `deno run -A jsr:@tutors/tutors`
2. Test all landing page links
3. Verify image display across all programmes
4. Check responsive layout

### Optional Enhancements
1. Add programme-specific course.png images
2. Create programme overview panelnotes
3. Add statistics dashboards
4. Consider renaming showcase directory to reflect all programmes

## Location

```
/Users/edeleastar/repos/hdip/2024/bsc-applied-computing-showcase-2026/
```

## Completion Status

✅ All 7 programmes created with complete structure
✅ All 104 projects have:
- Complete folder structure
- Professional panelnotes with abstracts
- Project images (where available)
- Landing page links
- Consistent formatting

The showcase is ready for Tutors course generation and deployment.
