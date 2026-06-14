# CV Templates and Tailoring Guide

## Template: LaTeX moderncv (Banking Style)

All CVs use the moderncv LaTeX package with the "banking" style and "blue" color scheme.

**Output file:** `cv/main_<company>.tex`
**Compile with:** **lualatex** on MiKTeX/TeX Live. pdflatex often fails on modern MiKTeX installs with `fontawesome5` font-expansion errors; lualatex handles the same sources cleanly.
**Master reference:** `cv/main_example.tex` (comprehensive CV with all competencies, experience, and achievements - use as source when building targeted CVs)

### Compile command

```bash
cd cv && lualatex -interaction=nonstopmode main_<company>.tex
```

Expected output: `Output written on main_<company>.pdf (2 pages, ...)`. Any page count other than 2 is a failure that must be fixed before presenting to the user.

## Document Structure

```latex
\documentclass[11pt,a4paper,sans]{moderncv}
\moderncvstyle{banking}
\moderncvcolor{blue}

% Force both first and last name AND section headings to render in moderncv
% blue (color1). Default banking on lualatex+MiKTeX leaves these black, which
% looks inconsistent with the rest of the blue accent scheme.
\renewcommand*{\firstnamestyle}[1]{{\fontsize{34}{36}\bfseries\upshape\color{color1}#1}}
\renewcommand*{\lastnamestyle}[1]{{\fontsize{34}{36}\bfseries\upshape\color{color1}#1}}
\renewcommand*{\sectionstyle}[1]{{\sectionfont\color{color1}#1}}

\usepackage[utf8]{inputenc}
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    filecolor=magenta,
    urlcolor=blue,
    pdftitle={Mahasweta Bordoloi - CV},
    pdfpagemode=FullScreen,
}
\usepackage[scale=0.77]{geometry}
\usepackage{import}

% Personal data
\name{Mahasweta}{Bordoloi}
\address{Marburg, Deutschland}{}{}
\phone[mobile]{+49 17670700150}
\email{bordoloi.mahasweta02@gmail.com}
\extrainfo{\href{https://www.linkedin.com/in/bordoloi}{LinkedIn}}

\begin{document}
\makecvtitle

% 1. Profile statement (1-3 sentences, tailored per role)
% 2. Skills section
% 3. Professional Experience section
% 4. Education section
% 5. Certifications
% 6. Languages
% 7. References

\end{document}
```

### Color overrides

The three `\renewcommand*` lines in the preamble are required on lualatex+MiKTeX. Without them the firstname, lastname, and section headings render in black even though `\moderncvcolor{blue}` is set, which looks inconsistent with the rest of the blue accent scheme (links, bullet markers, contact icons). The override forces all three to use `color1` (moderncv's accent colour, which becomes blue under `\moderncvcolor{blue}`). Both names render bold; if you prefer the firstname in regular weight, change the firstnamestyle override from `\bfseries` to `\mdseries`. Don't drop the override - on most modern installs the defaults render visibly wrong.

### Spacing inside itemize lists (important)

**Do not place `\vspace{...}` between `\item` entries in an `itemize` list.** Even though the source looks symmetric, this pattern occasionally produces a noticeably oversized gap before a single item: the inter-item `\vspace` creates a paragraph break that interacts unpredictably with the list's internal `\itemsep`, so LaTeX renders one of the gaps wider than the rest. Remove the inter-item `\vspace` and let `itemize` use its native uniform spacing.

```latex
% WRONG - intermittently produces an oversized gap before one bullet
\begin{itemize}
\item \textbf{Foo}: ...
\vspace{1pt}
\item \textbf{Bar}: ...
\vspace{1pt}
\item \textbf{Baz}: ...
\end{itemize}

% RIGHT - uniform spacing using the list's native itemsep
\begin{itemize}
\item \textbf{Foo}: ...
\item \textbf{Bar}: ...
\item \textbf{Baz}: ...
\end{itemize}
```

Two related patterns are fine and should be kept:
- `\vspace{1pt}` immediately after `\section{...}` (between section heading and first item) - this is between the heading and the list, not between list items.
- `\vspace{3pt}` between top-level `\cventry` blocks in Professional Experience or Education - this gives breathing room between roles and renders consistently.

## Section-by-Section Tailoring

### Profile Statement / Elevator Pitch (Best Practice)
This is the most important section to customize. It appears right after `\makecvtitle`.

Write 5-7 lines that function as an "elevator pitch": a concise, compelling introduction explaining why you're qualified for *this specific role*. Focus on what the employer gains from hiring you.

**For QA/QC/GMP roles in pharma/biotech:**
> Biotechnologin (M.Sc.) mit mehrjähriger praktischer Erfahrung in qualitätsrelevanten Labor- und Prozessumgebungen innerhalb der Molekularbiologie und Biotechnologie. Fundierte Kenntnisse in GMP-naher Dokumentation, Qualitätsmanagementsystemen, Abweichungsmanagement, CAPA-Grundlagen sowie Risiko- und Prozessbewertung. Erfahrung in der Durchführung, Dokumentation und Optimierung standardisierter Laborprozesse unter GMP-/GLP-nahen Bedingungen. Durch meine Tätigkeit in verschiedenen internationalen Forschungs- und Laborumgebungen in Deutschland und Indien habe ich eine hohe Anpassungsfähigkeit, schnelle Einarbeitung in neue Prozesse sowie ein starkes technisches Verständnis entwickelt.

*[Used for: OHLY QA Specialist]*

**For medical diagnostics / MTL / BTA / Biologist roles:**
> Naturwissenschaftlerin (M.Sc. Biotechnologie) mit praktischer Erfahrung in labormedizinischen Prozessen, Probenbearbeitung und qualitätsgesicherten Laborabläufen. Erfahrung in der Annahme, Verarbeitung und Analyse von Patientenproben (u. a. Dengue, HIV) unter standardisierten Bedingungen. Sehr verantwortungsbewusster und sorgfältiger Umgang mit Patientenproben, kombiniert mit einer selbständigen, zuverlässigen und serviceorientierten Arbeitsweise. Hohe Teamorientierung und Erfahrung in internationalen wissenschaftlichen Teams.

*[Used for: Synlab MTL/BTA/Biologist Microbiology]*

**For research-adjacent molecular biology roles (English-language):**
> Life scientist (M.Sc. Biotechnology, PhD candidate in Pharmaceutical Chemistry) with hands-on experience in virology, molecular biology, and RNA analytics across research institutions in Germany and India. Proficient in qRT-PCR, NGS, molecular cloning, transfection, Western Blot, ELISA, and VLP assays. Experienced in BSL-2 laboratory conditions and GMP/GLP-compliant documentation. Combines strong technical execution with a methodical, quality-conscious work approach developed across international research environments.

### Core Competencies / Skills Section (Best Practice)
Reorder and emphasize based on the role. Use bold category labels.

List **5-7 key competencies** in bullet format, tailored to the specific job. For each competency, briefly explain how it adds value to the position.

### Education
- Always include PhD (in progress) and M.Sc. at minimum
- For QA/industry roles: education section after experience — credentials support but don't lead
- For research/academic roles: education section before experience
- Include thesis topics when relevant to the target role

### Professional Experience
- Rewrite bullet points to emphasize aspects most relevant to the target role
- Use 4-6 bullets for PhD role, 3-4 for NCBS, 2-3 for Tata/IISc
- **Emphasize measurable or verifiable outcomes** where possible
- For QA roles: lead with GMP/GLP, deviation management, documentation bullets
- For diagnostics roles: lead with sample processing, virology diagnostics, quality bullets
- For molecular biology roles: lead with qRT-PCR, RNA analysis, BSL-2 experience

### Handling the PhD-to-Industry Transition
The PhD is not finished — this is a strength (current, ongoing experience) not a gap. Frame it as:
- Active research position, not "student"
- Lead with the applied/industry-relevant skills from the PhD
- The GMP/SAP certifications signal deliberate transition planning

### Certifications
- Always include the two MARA GMP certs with dates (verifiable, recent, directly relevant)
- Include SAP certs for QA/pharma roles
- Include IFS for food industry roles
- Include CAPA for regulatory/QA roles

### Languages
- One line: German (very good), English (very good), Hindi (very good)
- Note that all academic training was in English — relevant for international roles

### References
- "Available upon request." — do not list names until asked

## Compile-and-Inspect Loop (MANDATORY)

After writing the CV and before presenting to the user, always compile and visually inspect the PDF. Iterate until the layout is clean. Workflow:

1. Run `lualatex -interaction=nonstopmode main_<company>.tex`
2. Check the output page count: must be exactly 2
3. Read the PDF via the Read tool and visually inspect both pages
4. Check for **orphaned entries**: a `\cventry` title line must never sit alone at the bottom of page 1 with its bullets on page 2

### Fixing common page-break problems

**Problem: entry title on page 1, bullets orphaned to page 2**
Add `\needspace{5\baselineskip}` immediately before the problematic `\cventry`:
```latex
\needspace{5\baselineskip}
\item{\cventry{YEAR--YEAR}{Role Title}{Organization}{Location}{}{...}}
```
Include `\usepackage{needspace}` in the preamble.

**Problem: one trailing section spills to page 3 (e.g., References alone on page 3)**
Add `\enlargethispage{2-3\baselineskip}` before a late section (e.g., before `\section{Certifications}`) to stretch page 2 by a few lines. This is the standard LaTeX rescue for near-miss overflows.

**Problem: 3 pages with significant content on page 3**
Cut content — do not compress geometry or `\vspace`. See "Relevance-weighted cutting" below for the rule.

**Problem: content finishes early on page 2 (feels thin)**
Restore the highest-relevance item that was previously cut — a CV that ends mid-page 2 looks incomplete.

## Page Budget - Hard 2-Page Limit

The CV **must** fit on exactly 2 pages when compiled. Use these content limits as a guide:

| Section | Max budget |
|---------|-----------|
| Profile statement | 3-5 lines |
| Skills | 5-7 items, each 1-2 lines |
| PhD role | 5-6 bullets |
| NCBS role | 3-4 bullets |
| Tata / IISc roles | 2-3 bullets each |
| Education | 2-3 entries |
| Certifications | 4-6 entries, single line each |
| Languages | 1 line |
| References | "Available upon request." (single line) |

**If in doubt, cut rather than squeeze.** Reducing `\vspace` or geometry scale to force-fit content makes the CV look cramped.

## Relevance-weighted cutting (the right way to shrink a CV)

**Cut by signal, not by section.** Static priority lists ("remove oldest education first, then shorten the earliest role...") are wrong when a relevant "lower-priority" item is competing with an irrelevant "higher-priority" item. An older-role bullet that speaks directly to the posting is worth more than a recent-role bullet that does not.

For every candidate line, score three things:

1. **Relevance to THIS posting** — does the line hit a named tool, keyword, or stated responsibility in the job ad?
2. **Uniqueness** — is it the only place this claim appears, or is it duplicated elsewhere in the CV?
3. **Narrative load** — does the cover letter depend on it? If cutting the line would force you to rewrite a cover-letter paragraph, it is load-bearing.

Cut the lowest-total-score line first, regardless of which section it sits in.

### Practical order of cuts (easiest → last resort)

1. **Redundancy.** If an achievement appears in both Core Competencies AND a role bullet, the Core Competencies version is usually the cleaner cut.
2. **Profile-statement fluff.** A sentence that just restates what Skills or Certifications will show.
3. **Low-relevance experience bullets.** A bullet about work that does not touch posting keywords, wherever it sits.
4. **Low-relevance supporting content.** Tata Institute role (short, less relevant for most targets) can be reduced to 1-2 bullets or cut entirely.
5. **Last-resort structural cuts.** Collapsing IISc Praktikum to a single line; removing Abitur from Education; condensing Languages to one entry.

## Recommended Section Order

**For QA/QC/GMP pharma roles:**
1. Profile statement
2. Core competencies / Skills (QM & compliance first)
3. Professional Experience (reverse chronological)
4. Certifications
5. Education
6. Languages
7. References

**For medical diagnostics / MTL / BTA roles:**
1. Profile statement
2. Core competencies (diagnostics and lab methods first)
3. Professional Experience
4. Education
5. Certifications
6. Languages
7. References

**For molecular biology / research roles (English-language):**
1. Profile statement
2. Core competencies (molecular methods first)
3. Professional Experience
4. Education
5. Certifications
6. Languages
7. References
