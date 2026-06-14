# Job Evaluation Framework

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** qRT-PCR/qPCR, RNA analysis, DNA/RNA isolation, molecular cloning, Western Blot, ELISA, NGS/sequencing, molecular biology methods, GMP/GLP-compliant documentation, clinical/sensitive sample handling (BSL-2), virology (Dengue, Ebola), deviation management, CAPA fundamentals, data integrity, SOP documentation, lab equipment operation and maintenance

**Moderate match areas:** QMS systems (theoretical knowledge, no full industry QA role yet), HACCP, risk analysis, SAP basics, process optimization, IFS, audit preparation, cell & gene therapy workflows (SAP module only)

**Weak match areas:** Regulatory affairs (RA) strategy, clinical trial management, pure bioinformatics/computational roles, industrial scale-up/manufacturing, sales or commercial roles

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Molecular biology laboratory roles, virology research, analytical method execution, clinical/biological sample processing, BSL-2 laboratory work, GMP/GLP-adjacent documentation in research

**Moderate:** Quality control in pharmaceutical/biotech (research-adjacent, not direct industry QC), medical diagnostics laboratory work (Dengue/HIV diagnostics at NCBS is strong transfer signal), food industry QA (IFS training bridges)

**Entry-level / stretch:** Pure QA management roles (QMS ownership), regulatory submission writing, team leadership positions

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Highly unstructured or chaotic work environments; roles requiring heavy client-facing sales components; companies with poor Glassdoor reviews on management transparency; roles requiring significant travel away from Marburg.

### 4. Location & Logistics (Pass/Fail + Notes)
- Marburg and immediate surroundings: PASS
- Frankfurt/Rhine-Main area (commutable): PASS (check commute time)
- Remote / hybrid with occasional office: PASS
- Requires relocation: FLAG — not specified as a constraint in documents, ask Mahasweta
- International travel required: FLAG — discuss

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Transition from academic research into pharmaceutical/biotechnology industry
- Entry into QC, QA, or GMP-relevant analytics
- Alternatively: medical diagnostics laboratory roles (MTL/BTA/Biologist level)
- Food industry QA as an adjacent path (IFS training supports this)
- Build certified GMP/QM track record to grow into senior QA/RA roles over time

**Motivation filter:** Evaluate not just whether she *can* do the tasks, but whether the tasks will *energize* her. Consider:
- Tasks that energize: lab analytical work, molecular method execution, quality-relevant documentation, process standardization, international team collaboration
- Tasks that drain (inferred): pure administrative/desk roles with no lab component, highly repetitive routine testing without any optimization component
- Non-task factors: structured work environment, clear quality standards, collegial international team

**Life situation alignment:**
- **Security:** Actively job-seeking from PhD candidate position — stability and a concrete industry foothold are priorities
- **Flexibility:** No constraints specified; willing to work weekend shifts (stated in Synlab cover letter)
- **Professional development:** Actively investing in GMP/SAP certifications — roles offering further training or certification are a plus

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Calibration from Past Applications
- OHLY GmbH (QA Specialist): Applied — outcome unknown
- Synlab (MTL/BTA/Biologist Microbiology): Applied — outcome unknown
- Persoplan: Applied — outcome unknown

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether Mahasweta should call the contact person listed in the posting. **Only call if there are substantive questions** — never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second elevator pitch about the background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes — use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
