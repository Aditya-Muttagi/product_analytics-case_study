# Course Completion Analysis — Product Analytics Case Study

## Context
Online courses often suffer from very low completion rates.  
The goal of this project was to understand **where learners drop off**, **which early behaviors are associated with completion**, and **what product change would be most likely to improve outcomes**.

This work was done as a standalone product analytics case study using an anonymized online course dataset.

---

## Core Question
**Which early learner behaviors are most strongly associated with course completion, and where should the product intervene in the learner lifecycle?**

---

## Data
The dataset contains one row per learner per course, including:
- Registration, engagement, and completion indicators
- Aggregated engagement metrics (events, videos, chapters, forum posts)
- Course start and last activity timestamps

Raw data is not included due to privacy constraints.

---

## Approach

### Lifecycle and Funnel Analysis
I first modeled the learner lifecycle from registration through engagement to completion to identify where the largest drop-offs occur. This helped isolate whether completion failure was a late-stage content issue or an early engagement problem.

### Retention Analysis
Using course start time as the cohort anchor, I analyzed learner retention over time and built retention curves to understand how long learners typically remain active. This revealed a clear early retention threshold beyond which completion becomes materially more likely.

### Cohort Validation
To ensure the findings were not driven by a single time period, I repeated the retention and completion analysis across monthly cohorts.

### Behavioral Comparison
I then focused only on learners who crossed the early retention threshold and compared their engagement patterns. To avoid bias from longer course duration, engagement metrics were normalized per active day.

### Experiment Design
Finally, I translated the findings into a concrete A/B experiment that could be run by a product team.

---

## Key Findings

- Overall course completion was very low (~2–3%)
- Learners who disengaged within the first week almost never completed a course
- Reaching approximately 8 active days appears to be a prerequisite for completion
- Among learners who were retained beyond this point, higher video consumption intensity per active day was strongly associated with completion
- Forum or social activity did not meaningfully differentiate completers from non-completers

---

## Recommendation
Based on these findings, the highest-leverage product change is to focus on **early video engagement** rather than late-stage nudges or community features.

A reasonable first step would be to guide new learners through a clear video sequence during the first week, making it easier to maintain momentum while engagement patterns are still forming.

---

## Experiment Design (Summary)

- **Population:** Newly registered learners at course start  
- **Treatment:** Video-focused onboarding during the first week  
- **Primary metric:** Course completion rate  
- **Secondary diagnostics:** Videos per active day, share of learners reaching ≥8 active days  
- **Guardrails:** Early abandonment and signs of session fatigue  

---

## Tools
- SQL (SQLite)
- Python (Pandas, NumPy, Matplotlib)

---

## Author
Aditya Gururaj Muttagi
