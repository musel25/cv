# CV Template — Documentation

A modular LaTeX CV adapted for Machine Learning, Deep Learning, Computer Vision, NLP, and Optimisation profiles. It uses a clean header with icons, modern color accents, and section files you can edit independently.

## Quick Start
- Requirements: TeX Live 2022+ (or MiKTeX) with `latexmk`, `biblatex`, `fontawesome5`, `simpleicons`, `cochineal`, `cabin`, `zi4`.
- Recommended engine: XeLaTeX (for proper UTF-8 accents and modern fonts).
- Build:
  - `latexmk -xelatex cv-llt.tex`
  - If you later enable publications, `latexmk -xelatex -bibtex cv-llt.tex` or simply `latexmk -xelatex cv-llt.tex` (latexmk will run biber automatically when needed).

## Project Structure
- `cv-llt.tex`: Main file. Sets header, loads colors/styles, and includes sections.
- `settings.sty`: Visual theme (fonts, colors, icons, spacings).
- `photo.jpg`: Profile photo (shown when “fullonly” is enabled).
- Sections (modular; edit content here):
  - `about.tex`
  - `employment.tex`
  - `education.tex`
  - `projects.tex`
  - `skills.tex`
  - `languages.tex`
  - `volunteering.tex`
  - `referee.tex` (or `referee-full.tex`)
- Publications (optional):
  - `publications.tex`
  - `own-bib.bib`

## Edit Your Content
- Personal details: in `cv-llt.tex` within `\leftheader{...}`. Update email, phone, website, location, nationality, and DoB.
- About: `about.tex` (short professional profile).
- Experience: `employment.tex` (use concise action/impact bullets).
- Education: `education.tex` (program, institution, city/country, dates).
- Projects: `projects.tex` (title, one-line impact/tech, and a link via `\url{...}`).
- Skills: `skills.tex` (group by focus/tooling/platform).
- Languages: `languages.tex` (CEFR levels + mother tongue).
- Volunteering: `volunteering.tex`.
- References: `referee.tex` (short) or `referee-full.tex` (detailed grid).

## Add/Remove Sections
Sections are included via `\makerubric{<name>}` in `cv-llt.tex`.
- To add a new section:
  1) Create `<name>.tex` using `\begin{rubric}{Section Title} ... \end{rubric}`.
  2) Add `\makerubric{<name>}` in `cv-llt.tex` where you want it.
- To remove a section: comment out or delete the corresponding `\makerubric{...}` line.

## Publications (Optional)
- Keep `\addbibresource{own-bib.bib}` in `cv-llt.tex`.
- Include the section by adding `\input{publications}` in `cv-llt.tex`.
- Add entries to `own-bib.bib` and format author names to match your `\mynames{...}` for boldface.

## Styling & Theming
- Colors: edit `SwishLineColour` and `MarkerColour` in `settings.sty`.
- Fonts: XeLaTeX uses OpenType via `fontspec` (Cochineal, Cabin, Inconsolata/zi4). pdfLaTeX paths are also set.
- Icons: header fields use `fontawesome5` and `simpleicons` (for X/Twitter). Add fields with `\makefield{<icon>}{<content>}`.
- Photo: controlled by `fullonly` in `cv-llt.tex`.
  - Show photo: `\includecomment{fullonly}`
  - Hide photo: `\excludecomment{fullonly}`
  - Replace image: drop a new `photo.jpg`.

## Build Troubleshooting
- Accented characters render incorrectly: build with XeLaTeX (`latexmk -xelatex cv-llt.tex`).
- Missing icons (simpleicons/fontawesome5): ensure TeX Live is up to date and includes these packages.
- Bibliography doesn’t appear: ensure `biblatex` + `biber` are installed, `own-bib.bib` contains entries, and `publications.tex` is included.
- Line breaking in URLs: handled by `hyperref` and `url`; prefer `\url{...}` over raw text.

## Tips
- Keep bullets short and impact-focused; quantify results where possible.
- Prioritise recent and relevant projects to reduce length if needed.
- For ATS-friendly export, consider a one-column variant without icons or graphics; this template can be adapted if desired.

---

