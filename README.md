# Activity-Based Time Study Calculator — Warehouse Picking

A single-file, browser-based tool for conducting activity-based time studies on warehouse picking operations. No installation, no build step — just open `index.html` in any browser.

---

## Features

### Setup Tab
- Study metadata: name, analyst, picker, shift, date
- Picking method: RF Scanner, Voice Directed, Pick-to-Light, Paper, RFID
- Pick type: Single Order, Batch/Multi-Order, Zone, Cluster
- Equipment/MHE selection
- Configurable PF&D allowance %
- Add/remove custom activity codes with VA/NVA classification

### Record Tab
- Live stopwatch timer with **snapback** (measures each element) or **continuous** timing mode
- One-click activity buttons colour-coded by category
- Per-observation performance rating factor and notes
- Multi-round support — add rounds to separate study cycles
- Undo last observation

### Results Tab
- Per-activity statistics: count, average, std deviation, normal time, standard time
- Estimated picks per hour based on standard time + allowance
- Value-Added vs NVA-Necessary vs Non-Value-Added time breakdown
- Horizontal bar chart by activity
- Round comparison table (when multiple rounds recorded)
- **CSV export** with all observations and study metadata

---

## Default Activity Codes

| Code | Activity | Category |
|------|----------|----------|
| TT | Travel (Empty) | NVA-Necessary |
| TL | Travel (Loaded) | NVA-Necessary |
| LC | Locate / Search | Non-Value-Added |
| PK | Pick Item | Value-Added |
| SC | Scan / Verify | Value-Added |
| HA | Handle / Stage | Value-Added |
| WT | Wait / Idle | Non-Value-Added |
| AD | Admin / Label | NVA-Necessary |
| RE | Return to Start | NVA-Necessary |
| OT | Other | Non-Value-Added |

Custom codes can be added in the Setup tab.

---

## How to Use

1. Open `index.html` in a browser (or serve locally with `python3 -m http.server 8080`)
2. Fill in study details in the **Setup** tab
3. Go to the **Record** tab, press **Start**, then click activity buttons as the picker performs each task
4. View statistics and export results from the **Results** tab

### Timing Modes
- **Snapback** — each click records the elapsed time *since the last click*. Best for element-by-element studies.
- **Continuous** — each click records cumulative elapsed time. Duration is the time at the moment of click.

### Standard Time Calculation
```
Normal Time  = Observed Time × (Rating % / 100)
Standard Time = Normal Time × (1 + PF&D Allowance %)
```

---

## No Dependencies

The tool is self-contained vanilla HTML/CSS/JavaScript with no external libraries or CDN dependencies. It works offline and from a local file.
