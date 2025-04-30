# Galter_Collection_Analysis

## Journal Scoring Pipeline

This Python script ingests publication and citation data, enriches it with metadata, computes a suite of normalized metrics, and produces data-driven recommendations for library journal renewal, cancellation, or evaluation.

---

## 🔍 Project Overview

1. **Clean & Standardize**  
   - Normalize ISSN codes across all data sources.  
   - Ensure every publication record has a valid ISSN.

2. **Filter by Department**  
   - Focus analysis on `Medical Education` and `Preventive Medicine` faculty outputs.

3. **Compute Core Metrics**  
   - **Authorship Share**: Fractional Northwestern (NU) author contribution per journal.  
   - **Citation Flows**:  
     - *CitationsToNU*: How often each journal cites NU work  
     - *CitationsByNU*: How often NU papers cite that journal  
   - **Journal Impact**: Web of Science (WOS) JIF percentiles (with JCI fallback).  
   - **Open-Access Status**: Classify each journal as Gold / Hybrid / Subscription.  
   - **Alignment & Interdisciplinarity**:  
     - Subscription alignment score per department  
     - Bonus points for journals serving multiple departments  

4. **Normalize & Score**  
   - Scale each metric to a common range.  
   - Sum into a **Total_Score** for each journal-department pair.

5. **Generate Recommendations**  
   - **Keep / Fund** (>60)  
   - **Evaluate** (50–60)  
   - **Consider Cancellation** (<50)  
   - Flag “referenced-only” titles (journals cited by NU but not currently subscribed).

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+  
- `pandas`  
- Data exports from:  
  - Symplectic Elements (publication records)  
  - OpenAlex (metadata enrichment)  
  - InCites (journal impact metrics)

### Installation

1. Clone this repo:
   ```bash
   git clone https://github.com/your-org/journal-scoring.git
   cd journal-scoring
