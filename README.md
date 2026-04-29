# Somerset Furniture Company: Supply Chain Analysis
### Case Problem 10.1 | Procurement & Supply Chain Management
 
---
 
## Overview
 
This project analyzes the global supply chain of **Somerset Furniture Company**, a Virginia-based furniture manufacturer that fully offshored its production to China by 2000. The analysis is based on the case packet and was conducted entirely in Excel across five structured worksheets. The goal was to diagnose the root causes of Somerset's supply chain dysfunction and develop data-backed remediation recommendations.
 
The case surfaces four core problem areas: **excessive and unpredictable lead times**, **demand forecasting failures**, **high inventory costs driven by variability**, and **chronic quality defects**. Each sheet in the workbook addresses one or more of these areas.
 
---
 
## File Structure
 
| Sheet | Purpose |
|---|---|
| `Lead Time` | Full end-to-end lead time breakdown with variability metrics |
| `Demand Forecast` | 24-month rolling forecast model with seasonality and safety stock |
| `Inventory & Safety Stock` | EOQ model, safety stock calculation, and scenario cost comparison |
| `Remediation Plan` | 15 prioritized strategic and tactical improvement initiatives |
| `Scenario Analysis` | KPI comparison across four supply chain scenarios |
 
---
 
## Sheet-by-Sheet Summary
 
### 1. Lead Time Analysis
 
This sheet maps every stage of Somerset's supply chain, from purchase order development in the US through warehouse unloading in Virginia: with minimum, maximum, and average durations, plus a variability index for each stage.
 
**Key findings:**
- Total lead time ranges from **135 to 245 days** (avg. ~190 days), a spread of 110 days
- The **variability index** across the full chain is 1.81 (max/min ratio), indicating extremely unreliable delivery windows
- The highest-variance stages are **Security Inspection** (0–21 days, variance index 2.0), **Warehouse Unloading** (1–30 days, index 1.87), and **Transport to Port in China** (7–21 days, index 1.0)
- Fixed-duration stages: Manufacturing (60 days) and Ocean Transit (28 days), accounts for ~46% of average lead time but contribute zero variability
- The 40% delay rate cited in the case translates to an estimated **60% on-time delivery rate**
**What still needs to be done:** A sensitivity analysis could be added to quantify which individual stages, if reduced, would have the greatest impact on overall lead time. Regression or simulation (e.g., Monte Carlo) would strengthen the variability estimates.
 
---
 
### 2. Demand Forecast Model
 
This sheet builds a 24-month rolling forecast using a base annual demand assumption of 4,800 units, a 0.5%/month trend growth rate, and seasonal indices that peak in Q4 (1.2x) and trough in Q1 (0.85x). It applies an 8% forecast error standard deviation to produce upper and lower confidence bounds.
 
**Key findings:**
- Year 1 point forecast totals ~4,964 units; the confidence range spans roughly **4,567 to 5,361 units**
- Recommended order quantities range from ~513 units (January) to ~760 units (November), reflecting seasonality
- With a 27-week average lead time, reorder points are high: orders must be placed nearly **half a year in advance** of when the product is needed
- Safety stock requirements mirror order quantities due to the extreme lead time, ranging from 513 to 760 units monthly
- Stockout risk is held to ~4% across all months under the current model assumptions
**What still needs to be done:** The model currently uses assumed demand figures. It should be validated against Somerset's actual historical sales data when available. The forecast error rate (8% std dev) is also an estimate: actual error measurement would sharpen the safety stock and reorder calculations. Integrating the forecast directly with the S&OP process (Initiative #6 in the Remediation Plan) is a critical next step.
 
---
 
### 3. Inventory & Safety Stock
 
This sheet calculates Somerset's optimal inventory parameters using standard supply chain formulas (EOQ, safety stock, reorder point) and benchmarks the current state against two improvement scenarios.
 
**Current State Outputs (China-sourced, 27-week lead time):**
 
| Metric | Value |
|---|---|
| Safety Stock | ~41 units |
| Reorder Point | ~421 units |
| EOQ | ~362 units |
| Avg Inventory | ~222 units |
| Annual Holding Cost | $19,406 |
| Annual Ordering Cost | $15,848 |
| **Total Inventory Cost** | **$35,254** |
| Inventory Turns | 21.6x |
 
**Scenario Comparison:**
 
| Metric | Current (China) | Nearshore (Mexico/SE US) | Hybrid |
|---|---|---|---|
| Lead Time (weeks) | 27 | 8 | 12 |
| Safety Stock (units) | 41 | 30 | 51 |
| Total Inventory Cost | $35,254 | $30,286 | Intermediate |
| On-Time Rate | 60% | 92% | 85% |
| Quality Reject Rate | 15% | 3% | 8% |
 
**What still needs to be done:** The nearshore scenario savings ($4,968/year in inventory cost) are modest relative to the likely unit cost increases from nearshoring. A full landed cost model, comparing Chinese sourcing cost + supply chain risk cost against nearshore unit costs, needs to be built to make a fully defensible sourcing recommendation. The holding cost rate (25% of item value) should also be verified against Somerset's actual carrying cost data.
 
---
 
### 4. Remediation Plan
 
This sheet contains 15 prioritized improvement initiatives, categorized as strategic or tactical, with timelines, priority ratings, and expected outcomes.
 
**Critical Priority Initiatives (must-do):**
 
1. **Nearshore / Reshore Partial Manufacturing** (Mexico or SE US): Reduces lead time from 28+ weeks to 8–12 weeks; cuts variability by ~60%. Timeline: 12–24 months.
2. **Dual/Multi-Sourcing Strategy** (Vietnam + China + US): Eliminates single-supplier dependency and geographic risk. Timeline: 12–18 months.
3. **Implement S&OP Process**: Aligns demand forecasting with supply planning; targets cutting PO development cycle from 12–25 days down to 7 days. Timeline: 3–6 months.
**High Priority (significant impact, shorter horizon):**
 
- Long-term container contracts / SME consortium to secure container availability
- Reduce product line refresh frequency to 5-year cycles (from the current rapid cadence) to cut obsolescence risk and simplify warranty support
- Establish a parts/warranty depot in China to fulfill the 1-year warranty without waiting on active production runs
- Rolling 13-week demand forecast via ERP to replace ad-hoc forecasting
- Embed dedicated QC inspector at each Chinese manufacturer (rather than rotating auditors)
- Implement humidity-controlled kiln-drying standards at all supplier plants to fix the creaking defect
**Medium Priority:**
 
- Pre-certify as a Trusted Shipper under the C-TPAT program to reduce post-9/11 inspection delays
- Establish Vendor Managed Inventory (VMI) with top 10 retail customers to stabilize demand signal
- GPS tracking on all containers for real-time transit visibility
- Partial container sharing agreements to reduce underutilized container costs
**What still needs to be done:** Each initiative needs a cost estimate and ROI calculation. Priority was assigned based on impact and feasibility, but a formal cost-benefit analysis would allow Somerset to sequence initiatives by payback period. An implementation Gantt chart would also be useful for program management.
 
---
 
### 5. Scenario Analysis
 
This sheet compares four supply chain scenarios across 11 KPIs to quantify the upside from improvement.
 
| KPI | Status Quo | Tactical Fixes | Nearshoring | Hybrid Optimal | Improvement (Hybrid vs. Status Quo) |
|---|---|---|---|---|---|
| Lead Time Min (days) | 135 | 90 | 55 | 65 | **-52%** |
| Lead Time Max (days) | 245 | 180 | 90 | 120 | **-51%** |
| On-Time Delivery | 60% | 78% | 93% | 90% | **+50%** |
| Quality Reject Rate | 15% | 8% | 3% | 4% | **-73%** |
| Customer Complaint Rate | 12% | 7% | 2% | 3% | **-75%** |
| Total Cost Index | 1.00 | 0.92 | 0.88 | 0.85 | **-15%** |
| Inventory Turns | 2.8x | 3.5x | 5.2x | 4.8x | **+71%** |
| Forecast Accuracy | 65% | 80% | 88% | 92% | **+42%** |
| Warranty Resolution | 45 days | 30 days | 10 days | 14 days | **-69%** |
| SKU Obsolescence Risk | 20% | 15% | 8% | 10% | **-50%** |
 
The **Hybrid Optimal scenario** (combination of nearshoring + tactical fixes) delivers the best overall balance: near-term quality and service improvements through tactical changes, combined with structural lead time reduction through partial nearshoring while keeping cost reductions comparable to pure nearshoring.
 
**What still needs to be done:** The cost indices are relative, not absolute. Translating these into dollar figures, especially the revenue impact of improving on-time delivery from 60% to 90%, would make the business case much more compelling to leadership. Customer lifetime value modeling and churn assumptions based on the 40% delay rate would strengthen the case for urgency.
