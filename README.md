# 🏥 NHS Antimicrobial Resistance — Dual-Audience Data Visualisation

![Tableau](https://img.shields.io/badge/Tool-Tableau%20Desktop%20Professional-1F6BB5?style=flat&logo=tableau&logoColor=white)
![Domain](https://img.shields.io/badge/Domain-Public%20Health%20%7C%20Healthcare%20Analytics-red)
![Data](https://img.shields.io/badge/Data-NHS%20Digital%20%7C%20ESPAUR%20%7C%20ONS-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed%20%26%20Published-success)
![Academic](https://img.shields.io/badge/Academic-MSc%20Business%20Analytics%20%7C%20University%20of%20Birmingham-blue)

---

## Table of Contents

- [Project Overview](#-project-overview)
- [Live Dashboards](#-live-dashboards)
- [Business Problem](#-business-problem)
- [Key Statistics](#-key-statistics)
- [Dual-Audience Design Strategy](#-dual-audience-design-strategy)
  - [Dashboard 1 — Public (International News Organisation)](#dashboard-1--public-international-news-organisation)
  - [Dashboard 2 — Internal (NHS Country Directors)](#dashboard-2--internal-nhs-country-directors)
- [Data Sources & Preparation](#-data-sources--preparation)
- [Key Findings](#-key-findings)
- [Design Principles](#-design-principles)
- [Strategic Recommendations](#-strategic-recommendations)
- [Limitations & Future Work](#️-limitations--future-work)

---

##  Project Overview

This project addresses **England's antimicrobial resistance (AMR) crisis** through a dual-audience data visualisation strategy, communicating the same underlying NHS dataset in two fundamentally different ways for two distinct audiences. Two fully interactive **Tableau dashboards** were designed, built, and published, each tailored to the cognitive needs, goals, and expertise level of its intended audience.

> Antimicrobial resistance is declared by the **WHO as one of the top 10 global public health threats**. This project translates 405,751 bacterial infection episodes into actionable intelligence for both the general public and NHS leadership.

---

##  Live Dashboards

> **Click the badges below to open the fully interactive Tableau Public dashboards:**

| Dashboard | Audience | Link |
|-----------|----------|------|
| 🌍 **The Silent Crisis: Superbugs Spreading Across England's Hospitals** | International News Organisations / General Public | [![Tableau](https://img.shields.io/badge/Open%20Dashboard%201-Tableau%20Public-1F6BB5?style=flat&logo=tableau)](https://public.tableau.com/views/TheSilentCrisisSuperbugsSpreadingAcrossEnglandsHospitals/Dashboard1) |
| 🏥 **NHS AMR Strategic Intelligence Report** | NHS Country Directors / Healthcare Leadership | [![Tableau](https://img.shields.io/badge/Open%20Dashboard%202-Tableau%20Public-1F6BB5?style=flat&logo=tableau)](https://public.tableau.com/views/NHSIntranetReport/Dashboard2) |

---

##  Business Problem

England's NHS faces a dual communication challenge around antimicrobial resistance:

1. **Public Awareness Gap**: The general public and international media lack accessible, emotionally engaging visualisations that make AMR data personally relevant and understandable without medical expertise
2. **Strategic Intelligence Gap**: NHS Country Directors need operational dashboards surfacing regional performance disparities, resource misallocation, and prescribing inefficiencies to justify strategic intervention

The same dataset must speak two entirely different languages — one human, one operational.

---

##  Key Statistics

| Metric | Value |
|--------|-------|
| Total bacterial infection episodes (2023-24) | **405,751** |
| Annual bloodstream infections | **240,000+** |
| Annual abdominal infections (largest category) | **200,000+** |
| K. pneumoniae resistance increase | **+32%** (post-pandemic) |
| Post-pandemic antibiotic consumption vs. pre-pandemic | **+8% above baseline** |
| North West daily antibiotic consumption | **18.4 DDDs** per 1,000 inhabitants (vs. 17.6 national average) |
| North East infection rates vs. South West | **20% higher** |
| Bloodstream infection avg. hospital stay | **11 days** (vs. 3 days for other categories) |
| Length-of-stay variation for bloodstream infections | **40% across regions** (8–14 days) |
| Primary care share of antibiotic consumption | **71%** |
| Regions with integrated stewardship programmes | **15% lower** infection rates |

---

##  Dual-Audience Design Strategy

The core design challenge was adapting a single dataset into two communication registers — public storytelling and executive analytics — using Tableau Desktop Professional.

### Dashboard 1 - Public (International News Organisation)

**Three-panel layout: "The Growing Threat" → "Where Superbugs Strike Hardest" → "What This Means for You"**

| Panel | Chart Type | Design Decision |
|-------|-----------|----------------|
| **The Growing Threat** | Multi-line time series (2018–2024) | Distinct colours per pathogen; COVID-19 and post-pandemic surge annotated with callouts; K. pneumoniae highlighted with +32% annotation |
| **Where Superbugs Strike Hardest** | Interactive choropleth map of England | Warm yellow→deep red palette; darker = higher infection rate per 100K; numerical overlays per region for self-exploration |
| **What This Means for You** | Horizontal traffic-light bar chart | Infection types colour-coded red/yellow by severity; abdominal in yellow (high volume/moderate risk), bloodstream in deep red (critical) |

**Design philosophy:** F-pattern reading layout; emotional engagement via "SuperBugs" framing; progressive disclosure from personal relevance → geographic → temporal; no medical jargon without contextualisation; colorblind-accessible palettes (ColorBrewer).

---

### Dashboard 2 - Internal (NHS Country Directors)

**Four-panel operational intelligence layout with drill-down and filtering capabilities**

| Panel | Chart Type | Operational Insight |
|-------|-----------|-------------------|
| **Regional Performance Overview** | Scatter plot (infection rate vs. antibiotic consumption) | Identifies misaligned regions — high consumption AND high infections; North West quadrant flagged |
| **Antibiotic Consumption vs. Resistant Infections Trend** | Dual-axis line chart (2019–2023) | Post-pandemic 9.3% rebound in consumption; outpatient prescribing upward trajectory visible |
| **Length of Stay by Infection Type** | Heatmap (infection type × NHS region) | 40% variation in bloodstream infection LOS across regions; underperforming trusts identifiable |
| **Demographic Burden Analysis** | Stacked bar chart by age group and region | 75+ age cohort disproportionately affected in specific geographies; care home intervention signal |

**Design philosophy:** Analytical depth with drill-down actions; parameter controls for scenario benchmarking; KPI-anchored layout; data-ink ratio optimised (Tufte, 2001); NHS colour conventions respected for institutional credibility.

---

##  Data Sources & Preparation

### Primary Dataset
**Hospital Admitted Patient Care Activity 2023-24** — NHS Digital  
📎 [Download from NHS Digital](https://digital.nhs.uk/data-and-information/publications/statistical/hospital-admitted-patient-care-activity/2023-24)  
- 405,751 bacterial infection episodes (ICD-10 codes A00-B99)
- Provider-level, regional, and national aggregations
- Sheets used: `Bacteria_Provider_Level`, `Diagnosis_3_Character`

### Supplementary Datasets

| Source | Data Extracted | Purpose |
|--------|---------------|---------|
| **ESPAUR 2023-24** (UKHSA) | Tables 45a/45b — regional antibiotic consumption (DDDs) | Regional stewardship analysis |
| **ESPAUR Figure 2.1** | Pathogen-specific bacteraemia trends (2018–2024) | Temporal resistance trend lines |
| **ESPAUR Figure 2.2** | Resistance burden calculations | Quantifying resistance growth |
| **ONS Mid-Year Population Estimates** | Population denominators by NHS region | Rate standardisation (per 100K) |
| **WHO Global Health Observatory** | International benchmarking data | Contextual comparisons for public dashboard |

### Data Preparation Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| NHS `*` suppressed values (small cell counts) | Imputed using regional averages where statistically valid |
| Financial year (2023-24) ≠ Calendar year (2023) | Calendar-year to financial-year mapping protocol |
| ICD-10 codes ↔ ESPAUR pathogen naming mismatch | Harmonisation lookup table created in Excel |
| Provider organisation code inconsistencies | Standardised to 7 NHS commissioning regions |
| Tableau null/missing handling | Tableau's built-in **Data Interpreter** function applied |

**Tools:** Tableau Desktop Professional (visualisation) · Microsoft Excel (data preparation & integration)

---

##  Key Findings

**Resistance Trends:**
- Post-pandemic resistance surge is real and measurable — E. coli resistance has risen continuously since 2021
- K. pneumoniae shows the sharpest increase at +32%, representing the most urgent intervention target
- Antibiotic consumption stabilised but remains entrenched 8% above pre-pandemic levels

**Regional Disparities:**
- North West: highest infection burden (18.4 DDDs/1,000 inhabitants/day) + high infection rates = suboptimal stewardship cycle
- South West: achieves lower infection rates with 33.0M DDDs vs. North West's 50.5M DDDs — a model for national adoption
- North East / Yorkshire: 20% higher infection rates than South West despite comparable infrastructure

**Operational Insights:**
- Regions with integrated antimicrobial stewardship programmes show **15% lower infection rates** and **12% less inappropriate prescribing**
- Primary care drives **71% of antibiotic consumption** — yet coordination with secondary care is insufficient
- Bloodstream infection LOS ranges **8–14 days across regions** — a 40% variation pointing to protocol inconsistency

---

##  Design Principles

| Principle | Application |
|-----------|------------|
| **Tufte's Data-Ink Ratio** | Maximised data-to-decoration ratio; removed all chartjunk |
| **Stephen Few's Dashboard Design** | KPI-first layout; consistent visual hierarchy |
| **F-Pattern Reading Convention** | Critical insights placed in top-left primary attention zone |
| **Traffic-Light Colour Convention** | Red/amber/green universally understood risk coding |
| **Colorblind Accessibility** | ColorBrewer palettes used throughout |
| **Progressive Disclosure** | Summary → region → provider drill-down path |
| **Emotional Engagement (Public)** | "SuperBugs" framing; football stadium capacity metaphors; personal risk framing |
| **Analytical Depth (NHS Internal)** | Parameter controls; cross-filter actions; comparative benchmarking |

---

##  Strategic Recommendations

| Priority | Action | Target |
|----------|--------|--------|
| 🔴 **Immediate** | Mandatory regional infection control standardisation for North East and North West | NHS Country Directors |
| 🔴 **Immediate** | Deploy specialist antimicrobial stewardship pharmacists to high-consuming trusts | NHS Trusts |
| 🟡 **Short-term** | Mandate electronic prescribing with integrated decision support in primary care | Primary Care Networks |
| 🟡 **Short-term** | Establish regional AMR surveillance networks for real-time monitoring | UKHSA / NHS England |
| 🟢 **Strategic** | Adopt South West infection prevention protocols nationally | NHS England |
| 🟢 **Strategic** | Link trust performance ratings to stewardship compliance + financial incentives | NHS England |

**Investment required:** £50 million for enhanced stewardship programmes  
**Target outcomes:** 20% reduction in regional infection rate variation (18 months) · 15% decrease in inappropriate prescribing

---

> **Note on Tableau files:** Interactive dashboards are published and hosted on **Tableau Public** (links above). `.twbx` packaged workbook files can be provided on request — they are not committed to this repository due to embedded NHS dataset governance requirements.

---

##  Limitations & Future Work

- No provider-level antibiotic consumption data available — forced adaptation to regional aggregations, limiting stewardship correlation precision
- Monthly infection patterns unavailable — seasonal resource planning analysis constrained
- NHS `*` data suppression in smaller providers may understate community infection burdens
- No real-time data feeds — dashboards reflect 2023-24 snapshot only
- Formal user testing with target audiences was not conducted — audience assumption validation remains qualitative

**Future enhancements:** Real-time ESPAUR surveillance feed integration · Machine learning resistance forecasting · Cost-effectiveness modelling with financial data overlay · Provider-level antibiotic consumption granularity

---

