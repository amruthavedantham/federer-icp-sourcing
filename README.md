# Company Discovery & Evaluation Workflow

## Objective

Identify high-potential Hyderabad-based manufacturing companies in:

- Custom synthesis & specialty chemicals
- Pharma/agrochemical intermediates
- Electronic chemicals
- Performance chemicals

The evaluation framework focused on:

- Manufacturing capability
- Strong R&D / technical differentiation
- Revenue fit (₹50–500 Cr)
- Non-acquired / independent status
- Technical leadership
- Sector tailwinds
- Active growth signals

---
# Excel Sheet: 
https://docs.google.com/spreadsheets/d/1mq8MlQqlfyynObQCXKN2OWlbP2G0wW1ChTLginCox5I/edit?usp=sharing

# Round 1 – Company Discovery

### Initial Sourcing Methods

Used multiple sources to create the initial company universe:

- Google Sheets + App Script with keyword-based filtering
- Manual company discovery through industry/manufacturing websites
- Telangana manufacturing units PDF
  - Initially processed using Gemini to identify relevant companies
  - Followed by manual validation and shortlisting

This created the first broad pool of companies.

---

# Round 2 – Manufacturer / R&D / Revenue Validation

### Initial Automation Attempt

Tried automating evaluation using:

- Gemini 1.5 Flash
- App Script pipeline

Issues faced:

- API errors due to invalid model naming
- Raw response inspection showed incorrect model usage
- Switched to Gemini 2.0
- Continued facing quota/rate-limit issues despite:
  - creating new API keys
  - changing accounts/projects
  - reducing prompt sizes
  - reducing batch sizes from 2 → 1

### Fallback Approach

Shifted to a semi-manual AI-assisted workflow:

- Batched companies in groups of 3
- Used structured prompts to evaluate:
  - manufacturer status
  - R&D capability
  - service/trader filtering
  - acquisition status
  - revenue fit

Completed evaluation of ~75 companies in ~30 minutes.

### Result

- 19/75 companies qualified as strong potential candidates.

---

# Round 3 – Founder / MD Technical Background (C4)

### Workflow

- Identified Founder / MD through Google and company websites
- Collected publicly available background information
- Used Gemini to:
  - interpret educational/technical background
  - score technical depth
  - generate reasoning

Evaluation factors included:

- Engineering/scientific education
- PhD/IIT/NIT/BITS/IISc pedigree
- Technical leadership experience
- R&D orientation

---

# Round 4 – Technical Differentiation (C3)

Built a structured AI-assisted evaluation pipeline.

### Retrieval Layer

Used Serper API to gather live evidence related to:

- patents
- DSIR recognition
- USFDA/EU-GMP approvals
- custom synthesis
- proprietary products/processes
- innovation/R&D claims

### AI Interpretation Layer

Used OpenAI API (via OpenRouter) to:

- interpret retrieved evidence
- classify differentiation signals as:
  - Strong
  - Weak
  - Absent

### Deterministic Scoring Layer

Built Python-based weighted scoring logic to:

- assign C3 score
- assign confidence level
- ensure consistency across companies

---

# Round 5 – Growing Sector Evaluation (C5)

### Initial Attempt

Initially attempted to automate sector classification using Gemini API.

However:

- Gemini continued showing quota-limit issues
- even after:
  - changing API keys
  - changing projects/accounts
  - reducing prompt sizes
  - lowering batch sizes

### Final Approach

Shifted to a more reliable deterministic workflow using:

- Serper API for live evidence retrieval
- Python-based rule/keyword classification

### Workflow

- Identified sector/category for each company
- Created a sector scoring map
- Assigned scores based on:
  - China+1 relevance
  - specialty manufacturing
  - export orientation
  - differentiated chemistry
  - Make-in-India / industrial tailwinds

### Tools Used

| Component | Tool |
|---|---|
| Notebook | Jupyter |
| Search enrichment | Serper API |
| Data handling | pandas |
| Classification | Python logic-based mapping |
| Output | CSV / Excel |
| Validation | Manual review only for low-confidence cases |

This improved consistency and reduced dependency on unstable API behavior for deterministic classification tasks.

---

# Round 6 – Growth Signal Detection (C6)

Built a retrieval + reasoning + scoring pipeline.

### Retrieval Layer

Used Serper API to gather live evidence related to:

- hiring activity
- facility expansion
- certifications
- active website/news updates
- export/revenue growth

### AI Interpretation Layer

Used OpenAI API to classify each signal as:

- Strong
- Weak
- Absent

based only on retrieved evidence.

### Deterministic Scoring Layer

Used Python logic to:

- weight signals
- calculate final C6 score
- assign confidence level

---

# Reliability & Scalability Improvements

To improve robustness and scalability, implemented:

### Rate-limit handling

- Controlled delays between API calls
- Reduced prompt/token size
- Smaller stable model usage

### JSON parsing safeguards

- Automatic markdown cleanup
- JSON recovery logic for malformed responses

### Fallback handling

- Graceful handling of:
  - missing search evidence
  - API failures
  - incomplete responses

### Validation Strategy

- Manual verification only for:
  - low-confidence cases
  - unexpectedly high-scoring companies

This significantly reduced manual workload while maintaining evaluation quality.

---

# Final Scoring & Consolidation

Final scoring and ranking were consolidated in Excel using:

- SUM formulas
- IFS logic
- weighted scoring aggregation

### Final Outcome

From the initial 75-company pool:

- 18 companies qualified as ICPs

Band classification:

- A Band: 7 companies
- B Band: 11 companies
- C Band: 1 company

This created a final shortlisted set of high-potential manufacturing companies aligned with the target ICP criteria.

---

# Scaling Estimate for 1000 ICP Companies

## Based on Current Observed Retention

Observed funnel:

- Initial Pool: 75
- Core Qualified: 19 (~25%)
- Final ICPs: 18 (~95% retention from core qualified stage, ~24% overall retention)

Projected scale:

| Stage | Estimated Companies |
|---|---|
| Initial searchable universe | ~4200 |
| Core qualified companies | ~1050 |
| Final ICPs | ~1000 |

---

## Conservative Retention Estimate (More Realistic at Large Scale)

At larger scale, retention after core qualification is expected to reduce due to noisier datasets and lower-quality companies.

Conservative assumptions:

- Initial → Core Qualified: 20–25%
- Core Qualified → Final ICP: 65–80%

Projected scale:

| Stage | Estimated Companies |
|---|---|
| Initial searchable universe | ~5000 |
| Core qualified companies | ~1100–1300 |
| Final ICPs | ~1000 |

Key observation:

The largest reduction occurs during the early qualification stage (manufacturer validation, R&D capability, acquisition filtering, and revenue fit). Once companies pass the core qualification layer, downstream evaluation becomes significantly more efficient.

---

# Deliverables

- Excel sheet containing:
  - Initial Companies List
  - C1
  - C2
  - C4
  - Final scoring and banding

- Jupyter notebooks containing code pipelines for:
  - C3 (Differentiation)
  - C5 (Growing Sector)
  - C6 (Growth Signals)
```
