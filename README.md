# Daikibo Analytics — Data Analytics Job Simulation

**Deloitte Australia | Forage Job Simulation**

This repository contains my completed work for the Daikibo Analytics job simulation, where I stepped into the role of a data analyst supporting a global manufacturing company. The simulation involved two hands-on tasks: analyzing machine downtime across factories using Tableau, and building an automated fairness classification in Excel.

---

## 📋 Overview

| | |
|---|---|
| **Simulation** | Deloitte Australia — Data Analytics Job Simulation |
| **Platform** | [Forage](https://www.theforage.com/) |
| **Tools Used** | Tableau, Microsoft Excel |
| **Skills Demonstrated** | Data visualization, calculated fields, dashboard design, conditional formulas, data-driven storytelling |

---

## ✅ Task 1: Machine Downtime Analysis (Tableau)

**Objective:** Use telemetry data from Daikibo's factories to identify where machines were breaking down most, and which device types were driving that downtime.

### Approach
1. Imported factory telemetry data (`daikibo-telemetry-data.json`) into Tableau.
2. Built a calculated field, **Unhealthy**, converting each "Unhealthy" status reading into 10 minutes of downtime:
   ```
   IF [Status] = "Unhealthy" THEN 10 ELSE 0 END
   ```
3. Created two sheets:
   - **Down Time per Factory** — total downtime by factory location, sorted descending
   - **Down Time per Device Type** — total downtime by machine type, filterable by factory
4. Combined both into an interactive dashboard, using the factory chart as a filter for the device-type breakdown.

### Key Findings
- **Daikibo-Factory-Seiko** recorded the highest downtime (480 unhealthy units), pointing to significant production issues.
- **Daikibo-Shenzhen** followed closely (420 units), suggesting maintenance gaps.
- **Daikibo-Factory-Meiyo** showed moderate downtime (110 units).
- **Daikibo-Berlin** had the lowest downtime (20 units) — the strongest performer for equipment health.
- At the device level, the **Laser Welder** (480 units) and **Laser Cutter** (430 units) were the biggest contributors to downtime, while the **Metal Press** and **Air Wrench** reported zero downtime.

### Takeaway
Downtime is concentrated in a small number of high-risk devices and locations. Prioritizing preventive maintenance on laser welders and cutters at the Seiko and Shenzhen factories — and studying what Berlin is doing right — would have the biggest impact on uptime.

📊 *Dashboard screenshot included in this repo: `dashboard-screenshot.png`*

---

## ✅ Task 2: Equality Classification (Excel)

**Objective:** Build a formula-driven classification system to flag potential pay/hiring discrimination based on an "Equality Score" dataset.

### Approach
1. Added a new column, **Equality Class**, next to the existing Equality Score data.
2. Applied the following formula to classify each row:
   ```excel
   =IF(ABS(C2)>20, "Highly Discriminative", IF(ABS(C2)>10, "Unfair", "Fair"))
   ```
3. Filled the formula down through the full dataset and validated results against sample rows (e.g., a score of -25 correctly returned "Highly Discriminative").
4. Saved the final output as `Equality Table - Updated.xlsx`.

### Key Findings
- Several factory/role combinations — including roles at **Meiyo** and **Seiko** — returned scores well outside the fair range, flagging them as **Highly Discriminative**.
- Other roles, such as those at **Shenzhen**, fell within the **Fair** range, indicating no significant disparity.

---

## 🛠️ Skills Applied
- Building calculated fields and derived metrics in Tableau
- Interactive dashboard design with cross-filtering
- Conditional logic and nested `IF` formulas in Excel
- Translating raw operational/HR data into actionable business insights
- Root-cause thinking around equipment reliability and workplace fairness

---

## 🎓 Certificate
Completion certificate: *Deloitte Data Analytics Certificate (Forage).pdf*

## 🔗 Connect
- GitHub: *[[Click Here to View my Profile]](https://github.com/JD-3010)*
- LinkedIn: *[add your LinkedIn profile link]*

---

⭐ If this walkthrough was useful, feel free to star the repo!
