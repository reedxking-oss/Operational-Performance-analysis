# ⚙️ Operational Performance Analysis

## Objective
The goal of this project was to analyze operational workflow data to evaluate performance, identify bottlenecks, measure SLA compliance, and uncover factors that most impact cycle time and backlog growth. The analysis focuses on consistency, efficiency, and repeatable execution rather than isolated outcomes.

---

## Table of Contents
- [Data](#data)
- [Approach](#approach)
- [Results](#results)
- [Tools](#tools)

---

## Data
The dataset includes operational records such as work items, timestamps, statuses, workflow stages, priorities, and SLA targets. Data represents real-world operational processes and was sanitized to remove sensitive or identifying information.

Data fields include:
- Item ID
- Created and completed timestamps
- Status and workflow stage
- Priority and category
- Team/location
- SLA target and actual cycle time

> Note: This project uses a structured, analysis-ready schema designed to mirror production operational datasets.

---

## Approach

### Step 1: Data Cleaning & Preparation
Raw operational data required standardization and validation before it could be analyzed. In this step, I:
- Standardized status names, workflow stages, and category labels
- Validated timestamps and removed invalid or incomplete records
- Handled open vs. completed items to avoid skewed cycle-time metrics
- Removed duplicates and ensured one record per operational item
- Ensured required fields were present for SLA evaluation

**Output:** a clean, reliable dataset suitable for performance and SLA analysis.

---

### Step 2: Metric Definition & KPI Calculation
Rather than relying solely on raw counts, I defined metrics aligned with operational decision-making. Key KPIs included:
- SLA compliance rate
- Average and median cycle time
- Backlog volume
- Aging buckets for open items
- Stage-level time contribution
- Completion trends over time

Metrics were calculated using Excel (Power Query and PivotTables) to ensure transparency, repeatability, and ease of validation.

**Output:** a structured KPI layer designed to support fair comparisons across teams, categories, and time periods.

---

### Step 3: Analytics & Business Question Analysis
Using the defined KPIs, I analyzed operational performance with a focus on efficiency and consistency:
- Evaluated SLA performance across priorities, categories, and locations
- Identified workflow stages contributing the most to overall cycle time
- Analyzed backlog aging to highlight risk areas before SLA breach
- Compared completion trends over time to identify operational strain or improvement

This approach avoids overemphasizing volume alone and instead highlights sustainable, repeatable performance.

---

### Step 4: Interpretation & Insights
Results were interpreted through an operational and business lens:
- Items failing SLA targets were concentrated in specific stages rather than evenly distributed
- High-priority items generally met SLAs more consistently than lower-priority work
- A small subset of categories and locations accounted for a disproportionate share of long-aged backlog
- Delays were often driven by handoff and queue time rather than execution time

All insights were documented alongside assumptions and metric definitions to ensure clarity and auditability.

---

### Step 5: Reporting & Scalability
Findings were summarized using pivot tables and structured outputs designed to scale into SQL and BI tools such as Power BI or Tableau. Emphasis was placed on:
- Selecting metrics that directly answer operational questions
- Designing the dataset for future automation and expansion
- Maintaining clear documentation of assumptions and limitations

**Output:** actionable operational insights supported by scalable, well-documented data design.

---

## Results
- a
- b
- c
- d


---

## Tools
- **Excel / Power Query** – cleaned and standardized raw operational data, handled missing or invalid records, and prepared analysis-ready datasets
- **Pivot Tables** – calculated KPIs including SLA compliance, cycle time, backlog aging, and completion trends
- **Python** – performed data transformation, KPI calculations, and exploratory analysis to support repeatable and scalable insights
- **Dashboarding** – built an interactive dashboard to visualize operational performance, bottlenecks, and SLA risk
- **Operational Metrics Design** – defined KPIs aligned to real-world operational decision-making rather than raw counts
- **Documentation** – documented assumptions, metric definitions, and data limitations for transparency and reuse

