# Job Application Assistant for Mahasweta Bordoloi

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Mahasweta Bordoloi, helping with:
1. **Job fit evaluation** - Assess job postings against her profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Mahasweta Bordoloi
- **Location:** Marburg, Deutschland
- **Phone:** +49 17670700150
- **Email:** bordoloi.mahasweta02@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/bordoloi
- **Languages:** German (very good), English (very good), Hindi (very good)
- **Status:** PhD candidate (Doktorandin, Pharmaceutical Chemistry), actively seeking industry transition
- **LinkedIn headline:** "Doktorand:in an der Philipps-Universität Marburg | Forschung in Virologie, Biotechnologie"

### Education
- **PhD (in progress) in Pharmaceutical Chemistry** (12/2020–present) — Philipps-Universität Marburg
  - Focus: Ebola virus promoters, RNA synthesis, minigenome systems, virology (BSL-2)
- **M.Sc. in Medical Biotechnology** (08/2015–08/2017) — School of Life Sciences, Manipal
  - Thesis: Fitness landscapes of Flaviviruses (Dengue virus model), conducted at IISc Bengaluru
- **B.Sc. in Biotechnology** (07/2012–06/2015) — School of Life Sciences, Manipal
  - Thesis: Methylation profiles in PBMCs and LCLs of mitochondrial biogenesis genes

### Professional Experience
- **Doktorandin** (12/2020–present) — **Philipps-Universität Marburg** (Marburg, Germany)
  - qRT-PCR, RNA analysis, molecular biology under GMP/GLP-adjacent conditions
  - Ebola virus RNA/minigenome research; BSL-2 sample handling
  - Equipment maintenance (QuantStudio, autoclaves, -80°C storage)
  - Deviation documentation and troubleshooting
- **Wissenschaftliche Mitarbeiterin** (01/2018–06/2019) — **National Center for Biological Sciences** (Bengaluru, India)
  - Dengue vaccine development; clinical sample processing (blood, plasma); NGS workflows; Dengue/HIV diagnostics
- **Wissenschaftliche Mitarbeiterin** (08/2019–11/2019) — **Tata Institute for Genetics and Society** (Bengaluru, India)
  - Genetic studies on Drosophila melanogaster nerve cells
- **Praktikum** (02/2017–12/2017) — **Indian Institute of Science (IISc)** (Bengaluru, India)
  - Master's thesis: Flavivirus fitness landscapes; mutant development; cell line passaging

### Technical Skills
- **Primary:** qRT-PCR/PCR, RNA analysis, DNA/RNA isolation, molecular cloning, transfection, Western Blot, ELISA, VLP assays, NGS/Nanopore sequencing
- **Secondary:** GMP/GLP documentation, deviation management, CAPA fundamentals, HACCP, risk analysis, SAP (basics), MS Office
- **Domain:** Virology (Dengue, Ebola — BSL-2), molecular biology, pharmaceutical analytics, clinical sample handling
- **Software:** MS Office (Excel, Word, PowerPoint), SAP (Life Sciences; Cell & Gene Therapy modules)

### Certifications
- **GMP, GLP und GCP — Fundamentals and Advanced Requirements** — MARA, Philipps-Universität Marburg — September 2024 (16h)
- **GMP Aufbaukurs (Advanced GMP)** — MARA, Philipps-Universität Marburg — November 2024 (16h)
- **SAP Life Sciences Industry Einführungstraining** — Online, SAP Portal
- **SAP Grundlagen der Zell- und Gentherapiekoordination** — Online, SAP Portal
- **CAPA Management for Regulated Industries**
- **IFS (International Food Standard) Schulung**

### Publications
- None identified.

### Awards
- None identified.

### Behavioral Profile
- **Structured and thorough** — consistently foregrounds documentation, standardization, and quality compliance across all documents
- **Highly adaptable** — rapid onboarding across 5 institutions in India and Germany; repeatedly frames this as a strength
- **Reliability-driven** — "verantwortungsbewusst und sorgfältig" is a recurring self-description; quality consciousness is central to her professional identity
- **Strengths:** Precision, cross-cultural teamwork, methodical approach, technical ownership of lab systems
- **Growth areas:** Direct industry QA experience still being built; leadership/supervision experience limited so far
- **Thrives in:** Structured environments with clear quality standards; international/multilingual teams; roles that reward documentation accuracy and technical depth

### What Excites Her
- Applying molecular biology and quality skills in a product-focused, regulated industry context
- Working in environments where accuracy and compliance directly affect product or patient outcomes
- Building a certified QM/GMP track record in the pharmaceutical or biotech industry

### Target Sectors
- **Pharma/Biotech:** QC Analyst, QA Specialist, GMP-related analytics (companies like Merck, CSL Behring, Biontech, regional pharma near Marburg/Frankfurt)
- **Medical Diagnostics:** MTL, BTA, Biologist in microbiology or molecular diagnostics (SYNLAB, Labor MVZ, Limbach)
- **Food Industry QA:** QA Specialist/Manager (IFS training supports this path — OHLY-type roles)

### Deal-breakers
- *(To be confirmed with Mahasweta — not specified in documents)*

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools
- `documents/` - Source documents (CV PDFs, LinkedIn export, diplomas, past applications)

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and her strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`
