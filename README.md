# Oil & Gas Asset Integrity Dashboard (Power BI)

A portfolio-ready **asset integrity** dashboard that demonstrates how Power BI can turn operational data into role-based insights for **engineering**, **compliance**, and **business optimization**. Built with simulated datasets to mirror common KPIs and workflows used in natural gas infrastructure.

---

## What this shows (at a glance)
- **Status tracking** for *Deviation*, *Anomaly*, and *Management of Change (MoC)* items (in-progress, overdue, closed).
- **Compliance & certifications** overview (PLO, COI, Helideck) and **SCE cumulative** progress to target.
- **Trends** for corrosion rate (mmpy) and oil-in-water content (ppm) with monthly slicing.
- **Inspection performance** for lifting equipment (scope, inspected, overdue) across multiple years.
- **Backlog & SRB** tiles that surface overall risk level and inspection backlog %.
- **Slicers** for Month/Year + role-oriented layouts to support engineers and managers.

---

## Tech & approach
- **Platform:** Microsoft Power BI Desktop  
- **Data modeling:** Star-style tables for KPIs + thin model for cards/donuts  
- **Connectors (simulated):** SQL Server schema + SharePoint-list style tables  
- **Refresh behavior:** Daily refresh pattern simulated in PBIX  
- **Audience:** Engineers (tactical view), Managers (roll-ups), Leadership (KPI tiles)

---

## Demo data (included)
This project uses **simulated CSV datasets** that align with the screenshots and PBIX visuals.

Place these in a folder named `data/` at the repo root:

- `corrosion_rate_2020.csv` — corrosion rate (mmpy) by month (2020)
- `oil_in_water_content_2020.csv` — oil-in-water content (ppm) by month (2020)
- `lifting_equipment_overview.csv` — yearly scope / inspected / overdue (2018–2023)
- `action_item_status.csv` — Deviation & Anomaly (in_progress, overdue, closed)
- `moc_status.csv` — MoC open count
- `certifications_progress.csv` — % complete for PLO, COI, Helideck
- `sce_and_close_rates.csv` — SCE overdue >1 month, total closed actions, total MoC
- `inspection_backlog_and_srb.csv` — inspection backlog % and SRB label
- `sce_cumulative_status.csv` — SCE cumulative remaining-to-target (0.94)

> **Note:** Values are synthetic and provided for portfolio demonstration only.

---

## Visuals → data mapping

| Visual (PBIX)                           | Fields / Table                                      |
|----------------------------------------|-----------------------------------------------------|
| Deviation / Anomaly status donuts      | `action_item_status.csv` (type, in_progress, overdue, closed) |
| MoC status donut + Total MoC           | `moc_status.csv` and `sce_and_close_rates.csv`      |
| Certifications gauges (PLO/COI/Heli)   | `certifications_progress.csv` (percent_complete)    |
| SCE cumulative “Remaining” card        | `sce_cumulative_status.csv` (value)                 |
| Corrosion rate line (mmpy)             | `corrosion_rate_2020.csv` (month, corrosion_mmpy)   |
| Oil in water area (ppm)                | `oil_in_water_content_2020.csv` (month, oil_in_water_ppm) |
| Lifting equipment clustered bars       | `lifting_equipment_overview.csv` (year, scope, inspected, overdue) |
| Inspection backlog % tile              | `inspection_backlog_and_srb.csv` (Inspection_Backlog_Percent) |
| SRB level tile                         | `inspection_backlog_and_srb.csv` (SRB_Level_Label)  |
| KPI summary card (right rail)          | `sce_and_close_rates.csv`                            |

---

## How to run
1. **Clone** the repo and create a `data/` folder at the root.  
2. **Copy CSVs** from `/data` (this repo) into that folder.  
3. Open `dashboard.pbix` in **Power BI Desktop**.  
4. If prompted, verify the **file paths** for the CSVs (Transform data → Data source settings).  
5. Click **Refresh**. Confirm visuals align with the screenshots.

---

## Screenshots

### Status Overview & Certifications
![Dashboard Overview](./assets/Status-1.png)

### Inspection & Corrosion Trends
![Trends](./assets/Trends-1.png)

---

## Why this matters
- **Business process visibility:** surfaces delays, backlogs, and risk in one place.
- **Stakeholder-ready:** role-based views for engineers vs. managers; KPI tiles for leadership.
- **Transferable skills:** data modeling, Power BI report design, KPI definition, and clear communication.

---

### Disclaimer
This solution uses **dummy/simulated data** and does **not** represent real company operations or confidential information.
