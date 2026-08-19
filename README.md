# Nigerian Banking Complaint Analysis MVP — Adapted Customer Complaint Dataset

A Power BI-driven analysis of bank customer complaints, adapted to reflect the realities of Nigerian retail banking — built as the DA-13 capstone project for the 3MTT NextGen Cohort (Data Analysis & Visualization track).

![status](https://img.shields.io/badge/status-complete-brightgreen)
![tool](https://img.shields.io/badge/tool-Power%20BI-yellow)
![track](https://img.shields.io/badge/3MTT-DA--13-blue)


## Table of Contents
1. [Problem Definition](#1-problem-definition)
2. [Dataset Profiling](#2-dataset-profiling)
3. [Data Cleaning](#3-data-cleaning)
4. [Nigerian Banking Adaptation](#4-nigerian-banking-adaptation)
5. [Text Categorization](#5-text-categorization)
6. [Exploratory Data Analysis](#6-exploratory-data-analysis)
7. [MVP Development](#7-mvp-development)
8. [Power BI Dashboard](#8-power-bi-dashboard)
9. [Insights & Recommendations](#9-insights--recommendations)
10. [MVP Validation](#10-mvp-validation)
11. [Limitations & Data Ethics](#11-limitations--data-ethics)
12. [Deliverables](#12-deliverables)
13. [Demo](#13-demo)
14. [Future Improvements](#14-future-improvements)


## 1. Problem Definition

Nigerian bank customers face recurring frustrations — failed transfers, USSD/app downtime, unauthorized debits, and unresolved disputes — but there is little public, structured data that captures these patterns in a way banks or regulators (like the CBN) can act on. Most available complaint datasets (e.g. the U.S. CFPB dataset) reflect a different banking system entirely: card networks, dispute-resolution timelines, and channels that don't map onto Nigeria's cash-and-USSD-heavy retail banking environment.

**Objective:** Build a Power BI dashboard that categorizes and visualizes bank complaints in a way that is *recognizably Nigerian* — surfacing which issues occur most, which banks/channels they cluster around, and how resolution outcomes vary — to demonstrate an end-to-end data analytics workflow from raw data to actionable insight.

> This is a portfolio project; and could serve as a tool to help bank regulators in their control and monitoring of banks.


## 2. Dataset Profiling

The project began with the CFPB "Bank account or service" complaints dataset — 84,811 records, 2012–2017, U.S. banks and states — as a structural reference for what a real-world complaints dataset looks like (fields, categories, resolution outcomes, timelines).

A second candidate — a "Nigerian-adapted" version of the dataset — was profiled and found to have **statistically independent, shuffled columns** (e.g. bank names appearing in the resolution-outcome field), making it structurally meaningless. It was discarded after profiling confirmed the fields had no real relationship to one another.

**Decision:** Rather than force-fit unusable or non-Nigerian data, a fully synthetic dataset was designed and generated from scratch — with intentional, documented statistical relationships between fields — per the 3MTT brief's explicit allowance for synthetic data where real regional data is unavailable.


## 3. Data Cleaning
Cleaned the data using Power Query including:

Removing duplicates
Handling missing values
Standardizing date formats
Cleaning text fields
Standardizing bank names
Removing unnecessary columns
Correcting inconsistent categories

I also created new fields such as:

Complaint Month
Complaint Quarter
Complaint Year
Complaint Weekday
Region
Resolution Time
Complaint Severity
Digital vs Physical Channel


## 4. Nigerian Banking Adaptation

The dataset was rebuilt around Nigerian banking realities instead of simply relabeling U.S. data:

- **20,000 synthetic records** across **12 Nigerian banks**
- Fields and categories reflect actual Nigerian retail banking pain points rather than U.S. equivalents (e.g. no "credit card dispute" — replaced with USSD and POS-specific issues)
- Designed (not random) statistical relationships between fields, for example:
  - Resolution time and resolution outcome depend on issue type
  - Transaction amount distribution depends on channel (USSD vs POS vs ATM vs mobile app)
- Documented generation logic so the dataset is transparent about being synthetic-but-realistic, not claimed as real customer data


## 5. Text Categorization

Complaints are categorized into **7 Nigerian-banking-context categories**:

| Category | Description |
|---|---|
| Failed Transfer | Transfer initiated but not completed / funds not received |
| Excess Charges | Unexplained or disputed bank charges/fees |
| USSD/App Failure | Failed or hung transactions via USSD code or mobile app |
| Account Blocked | Account frozen or restricted without clear resolution |
| POS Debit Without Reversal | POS transaction debited but not reversed after failure |
| Unauthorized Debit | Debit not initiated by the customer |
| ATM Dispensed No Cash | ATM debited the account but did not dispense cash |




## 6. Exploratory Data Analysis

- Distribution of complaints by category and by bank
- Complaint volume trends over time
- Resolution time by category (which issues take longest to resolve)
- Channel breakdown (USSD vs app vs POS vs ATM) by complaint volume and amount



## 7. MVP Development

The project was scoped as a Minimum Viable Product per the 3MTT DA-13 brief: a working, demonstrable dashboard built on a defensible dataset, rather than a fully production-scale system. Development moved from raw dataset design → cleaning → categorization → dashboard build, with each stage documented so the reasoning (especially around the synthetic-data decision) is transparent to anyone reviewing the repo.

---

## 8. Power BI Dashboard

Built in **Power BI** (matching the 3MTT Power BI training track), the dashboard includes:

- Executive Overview: total complaints, top categories, top banks
  <img width="1338" height="796" alt="image" src="https://github.com/user-attachments/assets/ca2bf83c-b490-4a91-916a-8aaba49bc1d6" />

- Hidden Service Issues: resolution time and outcome by category
  <img width="1404" height="807" alt="image" src="https://github.com/user-attachments/assets/c1b982e6-5fc6-46dd-ba1d-0b3701585133" />

- Customer Experience analysis: complaint volume and amount by channel
  <img width="1337" height="795" alt="image" src="https://github.com/user-attachments/assets/b748944c-68c8-4bc9-a779-5d2a7979bd15" />

- Text Complaints Explorer:
<img width="1324" height="798" alt="image" src="https://github.com/user-attachments/assets/332c424a-6c16-423f-ae31-e31c1cc0d850" />



## 9. Insights & Recommendations

- Which category drives the most complaints, and for which banks
- Which channel has the longest average resolution time
- A concrete recommendation banks/regulators could act on based on the pattern


## 10. MVP Validation

_Describe how you checked the MVP actually works/holds up, e.g.:_
- Sanity-checked dashboard totals against the underlying dataset
- Verified category logic against sample records
- (If applicable) Gathered informal feedback from peers/mentors in the 3MTT cohort



## 11. Limitations & Data Ethics

- **Synthetic data:** This dataset is fully synthetic and does not represent real customer complaints or real bank performance. It is explicitly *not* claiming to reflect actual outcomes at any named Nigerian bank — bank names are used for realism and structure, not as factual claims about those institutions.
- **No real customer data used:** No real, identifiable customer information was used or is contained in this dataset, avoiding privacy concerns.
- **Designed, not observed, relationships:** Statistical relationships between fields were deliberately designed to be realistic, not derived from real-world observation — conclusions should be read as illustrative of a method, not as verified facts about Nigerian banking.
- **Bias disclosure:** Category definitions and relative frequencies reflect the author's judgment of common Nigerian banking complaints, not a statistically sampled survey.



## 12. Deliverables

Per the 3MTT DA-13 brief, this repository contains:


["C:\Users\olaid\OneDrive\Documents\3MTT NEXTGEN_ CAPSTONE_PROJECT\3MTT Capstone.pbix" ] Interactive Power BI dashboard (`.pbix`)
- ["C:\Users\olaid\Downloads\01_cleaned_nigerian_bank_complaints_mvp.csv" ] Cleaned dataset (`.csv`/`.xlsx`)
- [ https://docs.google.com/document/d/1Lk74LAqhH2bK1A2PFDRoKpLUj3PzC-XEsSak0YQ_WZ8/edit?usp=sharing] One-page insight summary (`.pdf`/`.md`)
- [ ] 2–3 minute demo video (linked below)

> _Check these off / link the actual files once uploaded to the repo._

---

## 13. Demo

📹 _Add your demo video link here (YouTube/Loom/Drive) once recorded._

---

## 14. Future Improvements

> _A few to consider — trim to what's actually true for you:_
- Incorporate real, anonymized complaint data (e.g. via a partnership or public CBN dataset) if one becomes available
- Add a text-classification model to automate categorization instead of rule-based logic
- Extend to a Power BI Service-published, shareable live dashboard
- Add year-over-year trend analysis if the dataset is extended with a longer time span

---

## Repository Structure

```
├── data/
│   ├── raw/                # Original CFPB reference dataset
│   └── processed/          # Final cleaned, adapted Nigerian dataset
├── dashboard/
│   └── bank_complaints.pbix
├── docs/
│   └── insight_summary.pdf
├── assets/                 # Dashboard screenshots
└── README.md
```

> _Adjust to match your actual folder layout._

## Tools Used

- **Power BI** — dashboard & DAX
- **Excel/Python** — dataset generation and cleaning
- 3MTT NextGen Cohort — Data Analysis & Visualization track (DA-13)

## Author

Built by Olaide Olabode as part of the 3MTT NextGen Cohort capstone project.
