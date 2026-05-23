# 💰 Daily Cost Visibility Dashboard — Non-Large, Large & Myntra

> **Multi-asset cost visibility in Power BI** — Plan vs Actual volume, vehicles, loadability, and CPS (Cost Per Shipment) for Non-Large, Large, and Myntra assets at one place, navigable by a single click.
> Data sourced live from Google Sheets trackers via `IMPORTRANGE`, requiring zero manual refresh.

---

## 🧭 Overview

This dashboard provides daily and MTD cost visibility across all three asset types operated by Flipkart's logistics network. It enables the central team to monitor Plan vs Actual deviations, projected costs, and CPS trends at facility, zone, and day level — without waiting for manual consolidation.

**Key capabilities:**
- All 3 assets (Non-Large · Large · Myntra) in one report, switchable via BU filter
- Plan vs Actual at facility level with D-2 lag view and PvA% colour coding
- CPS tracking — ML CPS, NL CPS, L CPS — updated daily
- Projected monthly cost at BU and zone level
- DRR (Daily Run Rate) vs projected cost for forward planning
- Overall cost trend by zone (North / South / East / West) over time

---

## 📸 Dashboard Preview

### 🌐 Non-Large — Cost & CPS Overview (Multi-Asset)
Facility-level MTD cost, projected cost by BU, CPS KPIs, loadability table, and PvA trend charts across all assets.

![NL Cost Overview](01_nl_cost_overview.png)

---

### 📊 Large — Plan vs Actual Facility Level (D-2)
Facility-level Plan vs Actual for volume, vehicles, loadability, and cost with PvA% heat-coded green/red.

![Large Plan vs Actual](02_large_plan_vs_actual.png)

---

### 🏭 Non-Large — Facility / Day / Zone Level Cost
Granular MTD cost view at facility, daily, and zone level with trend chart and zone-level projected cost comparison.

![NL Facility Day Zone](03_nl_facility_day_zone.png)

---

## 🏗️ Data Architecture

```
Google Sheets Trackers (multiple sources)
        │  IMPORTRANGE
        ▼
Master Consolidation Sheet
  ├── Non-Large cost & volume data
  ├── Large cost & volume data
  └── Myntra cost & volume data
        │
        │  Power BI connector
        ▼
Power BI Report
  ├── NL / Large / Myntra toggle (BU filter)
  ├── Facility Level View (MTD & Projected Cost)
  ├── Day Level View (MTD & Projected Cost)
  ├── Zone Level View (MTD & Projected Cost)
  ├── DRR & Projected Cost (Monthly)
  └── CPS KPIs — ML / NL / L
```

---

## 📐 Key Metrics

| Metric | Description |
|---|---|
| **Plan Vol / Actual Vol** | Planned vs actual shipment volume |
| **Plan Veh / Actual Veh** | Planned vs actual vehicle count |
| **Plan / Actual Loadability** | Vehicle fill efficiency |
| **PvA %** | Plan vs Actual deviation %, colour-coded |
| **Plan Cost / Actual Cost** | Gross transport cost |
| **PvA Cost (MTD)** | MTD cost deviation vs plan |
| **Projected Cost** | Forward projected monthly cost at BU/zone level |
| **DRR P Vol / A Vol** | Daily Run Rate — planned vs actual |
| **ML / NL / L CPS** | Cost Per Shipment by asset type |

---

## 🔄 Data Refresh

- Source data lives in **Google Sheets** trackers maintained by operations teams
- The master sheet pulls from individual trackers using **`IMPORTRANGE`** — no manual copy-paste
- Power BI connects to the master sheet and refreshes on schedule
- **Last Refresh Time** is displayed on every report page for transparency

---

## 📂 Repository Structure

```
daily-cost-visibility/
│
├── README.md
├── 01_nl_cost_overview.png
├── 02_large_plan_vs_actual.png
└── 03_nl_facility_day_zone.png
```

---

## 👤 Author

**Sri Ranganatha Perumal Venkatesan** — dashboard design, data architecture, IMPORTRANGE consolidation pipeline, and Power BI report build.

For access or queries, raise an issue in this repository or connect via GitHub.

---

*Logistics Cost Intelligence © 2026 | Flipkart Supply Chain*
