---
name: Azam Zuraiz
neptun: CNWOG5
id: 2026-LG-04
github: https://github.com/zuraizazam/project-course
github_project:
---
# SVG Optimizer Software for Laser Cutting

CNC laser cutting machines follow the paths of vector graphics, primarily SVG files. SVG files created in graphic software such as Illustrator or Inkscape rarely meet the strict requirements for cutting: they often contain unclosed lines, overlapping paths, and unnecessary nodes, which lead to poor cut quality, wasted material, or damaged parts. This project implements a dedicated web application that automatically corrects these geometric problems before cutting. The application is built with SvelteKit and uses geometry libraries such as paper.js or maker.js. By the end of the project, a user can upload an SVG file, receive a cleaned and color-coded production-ready SVG, see a visual preview with cut and etch lengths, and download the result.

## Objectives
- **Primary objective:** Deliver a working, version-controlled web application that cleans up SVG files for laser cutting (closing open curves, merging paths, removing duplicate and overlapping lines) and exports a color-coded, production-ready SVG.
- **Target users / stakeholders:** Makers and hobbyists with small laser cutters, small workshops, and CNC laser operators who receive customer-made SVG files.
- **Measurable success criteria:** A user can upload a defective SVG, see the optimized preview with cut and etch lengths, and download a cleaned file in which gaps within the chosen tolerance are closed, duplicate lines are removed, and cut and etch paths are color-coded. Invalid files produce a clear error message instead of a failure.
- **Constraints:** SvelteKit with JavaScript or TypeScript; geometry operations performed client-side or in the SvelteKit Node.js environment using external libraries (for example paper.js or maker.js); source code in a Git-based repository; no secret keys, access tokens, or personal or production data in the repository.

## Scope
### In scope
- Uploading, visually displaying, and downloading standard SVG files.
- Closing open curves by connecting endpoints that lie within a given tolerance.
- Merging adjacent, continuous line segments into single continuous paths.
- Detecting and removing duplicate and overlapping lines so the laser does not cut the same place twice.
- Color coding for machining operations (for example black = cut, red = engrave/etch).
- Calculating total cut and etch length, broken down by color, as a basis for estimating production time.
- A visual preview of the final optimized result in the user interface.
- Basic error handling, for example for invalid SVG files.

### Out of scope
- A full-featured vector graphics editor (not an Inkscape replacement).
- Machine control or G-code generation.
- Drawing or hand-editing shapes in the application.

## Notes
The first prototype will cover upload, preview, and download with a small set of sample SVG files that contain typical defects. The core cleanup pipeline (gap closing, path merging, duplicate removal, color coding, statistics) will be completed and tested before any extension is started. Possible extensions, to be considered only once the core is reliable, are common-line cutting, simple bounding-box nesting, tabs / microjoints, kerf compensation, and user registration with persistent storage of previous projects.
