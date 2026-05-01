# Federer ICP Sourcing System

A structured system to identify, evaluate, and scale high-quality ICP (Ideal Customer Profile) companies in the specialty chemicals domain using evidence-based filtering and Federer scoring.

---

## Overview

This project focuses on building a **repeatable sourcing and evaluation pipeline** for identifying high-quality companies.

- Initial dataset: **~100 companies**
- Final shortlisted: **25 ICP-qualified companies**
- Includes a **scale-up proposal to reach 1000 ICP companies**

The approach combines:
- Structured data sourcing
- Multi-layer filtering
- Evidence-based evaluation
- Hybrid automation + manual validation

---

## Repository Structure

### Main Files

- **Master List.xlsx**  
  Final consolidated list of evaluated companies

- **company_evaluations1-8 / 9-17 / 18-26**  
  Detailed evaluation sheets for each company

- **Methodology.pdf**  
  Complete explanation of research process, filtering logic, and evaluation approach

- **PART B.pdf**  
  Sourcing strategy + scale-up proposal for building 1000 ICP companies

- **1000 Company Plan.jpg**  
  Hand-drawn diagram showing the sourcing funnel and system design

---

### Filtering Logic

- **Filtering.ipynb**

This notebook contains the initial filtering pipeline:

1. **Filtering based on Manufacturing or not & Location Recheck**
   - Identifies true manufacturers
   - Verifies correct geographic presence

2. **Removing Service-based companies**
   - Filters out CRO/CDMO, traders, and non-manufacturing entities

---

### Work Folder

- **/work**

Contains all background work including:
- Source discovery
- Initial datasets
- Intermediate filtering outputs
- Data expansion and validation steps

This reflects the **full research process**, not just final results.

---

## Methodology Summary

The pipeline follows a **layered filtering approach**:

1. **Dataset Creation**
   - Structured sources (MCA, MSME, Chemexcil, export data, etc.)

2. **Layer 1 — Hard Filter**
   - Manufacturer check
   - Location validation

3. **Layer 2 — Sanity Filter**
   - Remove CRO / service-based companies
   - Remove traders / generic pharma
   - Apply revenue constraints

4. **Layer 3 — Evaluation**
   - Federer Scoring (C1–C6)
   - Evidence-backed assessment

5. **Final Output**
   - Ranked ICP companies with justification

---

## Key Principle

> Automate repetitive tasks, not judgment.

- Automation used for:
  - data extraction
  - filtering
- Manual validation used for:
  - edge cases
  - final decision-making

---

## Scale-Up Proposal

A detailed plan is included to scale from:
- **100 companies → 1000 ICP-qualified companies**

Key aspects:
- Multi-source sourcing
- Automated filtering pipeline
- Manual quality control layer
- Weekly execution plan
- Yield-based funnel design

---

## Outcome

- Built a **high-quality, evidence-backed ICP dataset**
- Designed a **scalable sourcing system**
- Balanced **automation + human judgment**

---

### Note

This project emphasizes:
- **Research quality over volume**
- **Evidence-backed evaluation**
- **System thinking for scalability**

---