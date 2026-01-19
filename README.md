# ⚙️ Operational Performance Analysis

## Objective
The goal of this project was to analyze operational workflow data to evaluate performance, identify bottlenecks, measure SLA compliance, and understand what factors most impact cycle time and backlog growth. The analysis focuses on consistency, efficiency, and repeatable execution rather than isolated outcomes.

---

## Table of Contents
- [Data](#data)
- [Approach](#approach)
- [Results](#results)
- [Tools](#tools)

---

## Data
The dataset consists of operational work records representing real-world workflow activity. Data was sanitized to remove sensitive or identifying information while preserving the structure and behavior of a production operational dataset.

The data includes:
- Item ID
- Created and completed timestamps
- Status and workflow stage
- Priority and category
- Team / location
- SLA target and actual cycle time

> Note: The dataset follows a structured schema with one record per work item and standardized workflow stages, designed to mirror typical operational tracking systems.

---

## Approach

### Step 1: Data Cleaning & Preparation (Excel / Power Query)

Raw operational data required validation and standardization before analysis. Excel was used as the primary environment to inspect, clean, and prepare the dataset. In this step, I:

- Standardized status names, workflow stages, and category labels
- Validated created and completed timestamps and removed invalid or incomplete records
- Differentiated open vs. completed items to prevent skewed cycle-time calculations
- Removed duplicate records and enforced one record per operational item
- Ensured all required fields were present for SLA evaluation

**Output:** a clean, reliable dataset suitable for cycle-time, backlog, and SLA analysis.

---

### Step 2: Metric Definition & KPI Calculation (Excel)

Before analyzing performance, I defined metrics aligned with operational decision-making rather than relying on raw counts alone. Key KPIs included:

- SLA compliance rate
- Average and median cycle time
- Backlog volume and backlog growth
- Aging buckets for open items
- Stage-level time contribution
- Completion trends over time

These KPIs were calculated using Excel (Power Query and PivotTables) to ensure transparency, traceability, and ease of validation.

**Output:** a structured KPI dataset designed to support fair comparisons across teams, priorities, categories, and time periods.

---

### Step 3: Analytical Processing & Validation (Python)

Python was used to support repeatable analysis and validation beyond Excel. This step focused on:

- Reproducing KPI calculations programmatically to validate Excel results
- Performing grouped aggregations across categories, priorities, and workflow stages
- Identifying distribution patterns and outliers in cycle time and backlog aging
- Preparing analysis-ready tables for visualization

Python allowed the analysis logic to be repeatable and scalable while maintaining alignment with the Excel-based KPIs.

---

### Step 4: Analytics & Business Question Analysis

Using the defined KPIs, I analyzed operational performance with a focus on efficiency and consistency:

- Evaluated SLA performance across priorities, categories, and locations
- Identified workflow stages contributing the largest share of total cycle time
- Analyzed backlog aging to surface risk areas before SLA breach
- Reviewed completion trends over time to identify operational strain or improvement

This approach avoids overemphasizing volume alone and instead highlights sustainable, repeatable performance.

---

### Step 5: Visualization & Insight Delivery (Tableau)

Tableau was used to translate the KPI outputs into clear, interpretable visualizations. Dashboards were designed to support quick understanding by operational stakeholders.

Key design choices included:
- Clear separation between SLA performance, cycle time, and backlog views
- Use of simple, consistent visual encodings to avoid visual bias
- Interactive filters to compare teams, categories, and time periods
- Tooltips to provide context without cluttering the main visuals

The final dashboards emphasize clarity, interpretability, and operational relevance.

---

### Step 6: Reporting & Scalability

Findings were documented with clear metric definitions, assumptions, and limitations. The dataset and KPI structure were designed to support future expansion, automation, and deeper analysis.

**Output:** actionable operational insights supported by a scalable, well-documented data model.

---

## Results
- Identified specific workflow stages that consistently contributed the largest share of overall cycle time
- Found that SLA misses were concentrated within a limited number of categories and locations rather than evenly distributed
- Observed that high-priority work generally met SLA targets more consistently than lower-priority items
- Highlighted backlog aging patterns that can be used to proactively flag SLA risk before breach

These results provide a clearer view of where operational improvements would have the greatest impact.

---

## Tools
- **Excel / Power Query** – cleaned and standardized raw operational data, validated timestamps, handled missing or invalid records, and prepared analysis-ready datasets  
- **Pivot Tables** – calculated KPIs including SLA compliance, cycle time, backlog aging, stage-level contribution, and completion trends  
- **Python** – performed repeatable data transformations, KPI validation, and exploratory analysis to support scalability and consistency  
- **Tableau** – built interactive dashboards to visualize operational performance, bottlenecks, SLA risk, and trends over time  
- **Operational Metrics Design** – defined KPIs aligned with real operational decision-making rather than raw volume  
- **Documentation** – documented assumptions, metric definitions, and data limitations for transparency and reuse  

