# Search Queries for Job Scraper

## Candidate
**Mahasweta Bordoloi** — Marburg, Deutschland
**Location scope:** All of Germany (remote, hybrid, or relocation possible)

## Search Sites

Primary (German job market):
- **stepstone.de** — Germany's largest commercial job board
- **arbeitsagentur.de/jobsuche** — Bundesagentur für Arbeit Jobbörse (government portal)
- **monster.de** — major German commercial job board
- **linkedin.com/jobs** — LinkedIn job listings (filter: Germany)
- **xing.com/jobs** — DACH professional network job board

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies
- `site:merck.de jobs`, `site:cslbehring.com careers`, `site:synlab.de karriere`, `site:biontech.de jobs`

## Query Categories

Queries are grouped by priority. Each query covers Germany-wide unless otherwise noted.

---

### Priority 1: Quality Assurance / Quality Control

These match the strongest and most direct career direction.

```
site:stepstone.de "QA Analyst" Biotechnologie Deutschland
site:stepstone.de "QC Analyst" Pharma Deutschland
site:stepstone.de "Qualitätssicherung" GMP Biotechnologie
site:stepstone.de "Quality Assurance Specialist" Deutschland
site:stepstone.de "Quality Control" Analyst Pharma Deutschland
site:arbeitsagentur.de "QA Analyst" Biotechnologie
site:arbeitsagentur.de "QC Analyst" Pharma
site:arbeitsagentur.de "Qualitätssicherung" GMP Molekularbiologie
site:linkedin.com/jobs "QA Analyst" Germany Biotechnology
site:linkedin.com/jobs "QC Analyst" Germany Pharmaceutical
site:linkedin.com/jobs "Quality Assurance" GMP Germany entry level
site:xing.com/jobs "QA Analyst" Deutschland
site:xing.com/jobs "Qualitätskontrolle" Pharma Deutschland
```

---

### Priority 2: Regulatory Affairs

Adjacent to QA/QC; strong fit given GMP/GLP certifications.

```
site:stepstone.de "Regulatory Affairs" Trainee Deutschland
site:stepstone.de "Regulatory Affairs" Berufseinsteiger Pharma
site:stepstone.de "Regulatory" Spezialist Biotechnologie Deutschland
site:arbeitsagentur.de "Regulatory Affairs" Pharma Deutschland
site:linkedin.com/jobs "Regulatory Affairs" Germany entry level Biotech
site:linkedin.com/jobs "Regulatory Affairs Associate" Germany
site:xing.com/jobs "Regulatory Affairs" Einsteiger Deutschland
```

---

### Priority 3: Food Safety

Supported by IFS Schulung and HACCP knowledge; fits OHLY-type roles.

```
site:stepstone.de "Lebensmittelsicherheit" QA Deutschland
site:stepstone.de "Food Safety" Analyst Deutschland
site:stepstone.de "Food Safety" Spezialist IFS Deutschland
site:stepstone.de "Qualitätssicherung" Lebensmittel Deutschland
site:arbeitsagentur.de "Lebensmittelsicherheit" Qualitätssicherung
site:arbeitsagentur.de "Food Safety" Analyst Deutschland
site:linkedin.com/jobs "Food Safety" Specialist Germany
site:linkedin.com/jobs "Lebensmittelsicherheit" QA Germany
site:xing.com/jobs "Food Safety" Deutschland
```

---

### Priority 4: Biotechnology / Molecular Biology roles

Broader net — lab analyst/scientist roles where the biotech/virology background is the primary asset.

```
site:stepstone.de "Biotechnologe" Laborant GMP Deutschland
site:stepstone.de "Biotechnologie" Analyst qPCR Deutschland
site:stepstone.de "Molekularbiologie" Laborant Pharma Deutschland
site:stepstone.de "Virologe" OR "Virologie" Laborant Deutschland
site:arbeitsagentur.de "Biotechnologe" GMP Pharma
site:arbeitsagentur.de "Molekularbiologie" Analyst
site:linkedin.com/jobs "Biotechnology" Analyst Germany entry level
site:linkedin.com/jobs "Molecular Biology" Lab Scientist Germany
site:xing.com/jobs "Biotechnologe" Pharma Deutschland
```

---

### Priority 5: Trainee / Entry-Level / Berufseinsteiger

Explicitly trainee-level across all target areas — important given transition from academia.

```
site:stepstone.de Trainee QA QC Pharma Deutschland
site:stepstone.de Berufseinsteiger Qualitätssicherung Biotechnologie
site:stepstone.de "Junior" QA Analyst Pharma Deutschland
site:stepstone.de Trainee Laborant Molekularbiologie Deutschland
site:arbeitsagentur.de Trainee Qualitätssicherung Pharma
site:arbeitsagentur.de Berufseinsteiger Biotechnologie Labor
site:linkedin.com/jobs Trainee Quality Assurance Germany
site:linkedin.com/jobs "Graduate" OR "Junior" QA QC Germany Biotech
site:xing.com/jobs Trainee Qualitätssicherung Pharma Deutschland
site:monster.de Trainee QA Pharma Deutschland
site:monster.de Berufseinsteiger Biotechnologie Labor
```

---

## Suggested Role Types Not Yet Searched (proactive suggestions)

Based on the skill profile, these are also worth monitoring:

- **Clinical Research Associate (CRA) — Trainee:** GMP/GLP knowledge + international lab background makes this a viable pivot
  ```
  site:stepstone.de "Clinical Research Associate" Trainee Deutschland
  site:linkedin.com/jobs "CRA" trainee Germany entry level
  ```
- **Medical Science Liaison (MSL) — Junior/Associate:** PhD background + virology knowledge; more business-facing than lab work
  ```
  site:linkedin.com/jobs "Medical Science Liaison" Junior Germany
  ```
- **Laborleiter-Assistenz / Lab Coordinator:** For roles that combine lab execution with coordination/documentation ownership
  ```
  site:stepstone.de "Laborkoordinator" OR "Lab Coordinator" Pharma Deutschland
  ```

---

## Location Filter

**Base:** Marburg, Hessen
**Scope:** All of Germany — remote, hybrid, or relocation accepted
- Hessen (Marburg, Frankfurt, Wiesbaden, Gießen, Darmstadt): IDEAL — no relocation needed
- Other German states with remote/hybrid option: PASS
- Full on-site relocation required: FLAG — include but note relocation needed; discuss with Mahasweta before applying
- Outside Germany: SKIP unless explicitly requested

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- `/scrape QA` → Priority 1 queries + 2-3 custom QA queries
- `/scrape food` → Priority 3 queries
- `/scrape trainee` → Priority 5 queries across all sectors
- `/scrape regulatory` → Priority 2 queries
- `/scrape remote` → all priorities filtered to "home office" or "remote" terms
