# ⚙️ Operational Performance Analysis

## Objective
The goal of this project was to analyze operational workflow data to evaluate performance, identify bottlenecks, measure SLA compliance, and understand what drives cycle time and backlog growth. The focus is on consistency and repeatable execution rather than isolated “good” or “bad” weeks.

---

## Table of Contents
- [Data](#data)
- [Approach](#approach)
- [Results](#results)
- [Tools](#tools)

---

## Data
The dataset includes operational records such as work items, timestamps, statuses, workflow stages, priorities, and SLA targets. The data represents a real-world operations workflow and was sanitized to remove sensitive or identifying information.

Typical fields used in the analysis:
- Item ID
- Created and completed timestamps
- Status and workflow stage
- Priority and category
- Team / location
- SLA target and actual cycle time

> Note: The dataset follows a structured schema intended to mirror production operational data (one record per work item, with standardized stages and timestamps).

---

## Approach

### Step 1: Data Cleaning & Preparation (Excel / Power Query)

Raw operational data required standardization and validation before it could be analyzed. Excel was used to review the dataset, validate the schema, and clean records in a transparent way. In this step, I:

- Standardized status names, workflow stages, and category labels
- Validated timestamps (created, started, completed) and removed invalid or incomplete records
- Separated open vs. completed items to avoid skewing cycle-time metrics
- Removed duplicates and enforced one record per operational item
- Ensured required fields were present for SLA evaluation (priority, stage, timestamps, SLA target)

**Output:** a clean, reliable dataset suitable for performance, cycle-time, and SLA analysis.

---

### Step 2: Metric Definition & KPI Calculation (Excel / PivotTables)

Rather than relying on raw volume alone, I defined metrics aligned with operational decision-making and service performance. Key KPIs included:

- SLA compliance rate (overall and by segment)
- Average and median cycle time
- Backlog volume and backlog growth over time
- Aging buckets for open items (to flag SLA risk early)
- Stage-level time contribution (where work spends time)
- Completion trends over time (throughput)

These KPIs were calculated using PivotTables so results were easy to validate and explain without “black box” logic.

**Output:** a structured KPI layer designed to support fair comparisons across teams, categories, priorities, and time periods.

---

### Step 3: Analytics & Business Question Analysis

Using the KPI layer, I analyzed workflow performance with a focus on efficiency and repeatability:

- Evaluated SLA performance across priorities, categories, and locations to identify where misses were concentrated
- Identified workflow stages contributing the most to total cycle time (bottleneck stages)
- Analyzed backlog aging to surface risk areas before SLA breach rather than after the fact
- Compared completion trends over time to identify operational strain, seasonality, or process improvements

This approach avoids overemphasizing “how many got done” and instead highlights where the process slows down and why.

---

### Step 4: Interpretation & Insights

Results were interpreted through an operational/business lens and documented with assumptions so they can be reviewed and reused:

- SLA misses were not evenly distributed; they clustered in specific workflow stages
- High-priority work tended to meet SLA more consistently than lower-priority items (suggesting prioritization improves service outcomes)
- A small subset of categories and locations accounted for a disproportionate share of long-aged backlog
- Delays were frequently driven by handoffs and queue time rather than active execution time

---

### Step 5: Reporting & Scalability (SQL / BI-ready outputs)

Findings were summarized in structured outputs designed to scale into SQL and BI tools (Power BI or Tableau). Emphasis was placed on:

- Choosing metrics that directly answer operational questions (service level, cycle time, backlog risk)
- Documenting assumptions and limitations (open vs. completed items, timestamp validity rules)
- Structuring outputs so they can be automated later (refreshable queries and consistent dimensions)

**Output:** clear, business-relevant insights backed by documented metrics and scalable data design.

---

## Results
- Identified the workflow stage(s) contributing the largest share of cycle time, highlighting where process changes would have the biggest impact  
- Found that SLA misses were concentrated in specific categories/locations rather than spread evenly, helping narrow where to focus operational attention  
- Built backlog aging buckets to flag items at risk *before* SLA breach, enabling proactive prioritization instead of reactive cleanup  
- Produced a BI-ready KPI layer (SLA rate, cycle time, backlog trends, stage contribution) that can be refreshed and extended as new data is added  

---

## Tools
- **Excel / Power Query** – cleaned and standardized operational data, validated timestamps, handled incomplete records, and produced analysis-ready tables  
- **Pivot Tables** – calculated KPIs including SLA compliance, cycle time, backlog aging, stage-level contribution, and completion trends  
- **SQL (optional/scalable layer)** – supports repeatable aggregation and a clean KPI dataset for dashboards and future automation  
- **Dashboarding (Tableau or Power BI)** – created an interactive view of SLA performance, bottlenecks, backlog risk, and trends over time  
- **Operational Metrics Design** – defined KPIs aligned to real operational decisions rather than raw counts  
- **Documentation** – documented assumptions, metric definitions, and limitations so results are easy to audit and reuse  

