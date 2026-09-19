# Is Barcelona's Offside Trap a Sustainable Defensive Identity?

**A data-driven analysis across the Messi era (StatsBomb) and the Flick era (FBref/Understat).**

---

## The question

Barcelona under Hansi Flick plays with one of the highest defensive lines in European football. In 2024/25 this worked — La Liga title, 115 offsides caught, only 39 goals conceded. In 2025/26 the same system is failing: critics call it "kamikaze", opponents are routinely breaching it on the counter, and Flick is doubling down.

But the debate is mostly qualitative. This project asks a sharper, data-answerable question:

> **Is the offside trap condition-dependent — and if so, what conditions determine whether it works?**

The central hypothesis: the trap is only safe when coordinated with high pressing. A high defensive line without the press creates catastrophic space behind it. This is falsifiable with data.

## Why it matters

Understanding *when* the trap fails — not just *that* it sometimes fails — has direct applications:

- **For Barcelona:** identify the match conditions and opponent profiles that most expose the system; design training scenarios around them; define KPIs to monitor each match.
- **For opponents:** know which tactical approaches most reliably break the line.
- **For Twelve's Earpiece:** this analysis is a prototype of a reusable *Tactical Risk Profile* — a feature that quantifies any team's defensive line exposure under different conditions.

## Structure

The project has three parts, each constrained by available data:

### Part 1 — The mechanism (Messi era, 2004/05–2020/21)
Using **StatsBomb open event data** — the richest freely available football data — we measure how Barcelona's offside trap actually worked across managerial eras. We extract offside events, compute pressing intensity (PPDA), and test whether the press–line relationship explains when the trap succeeded and when it was beaten.

### Part 2 — The current crisis (Flick era, 2024/25–2025/26)
StatsBomb open data does not cover Flick's Barcelona. We use **FBref match logs** and **Understat shot data** — aggregated, less granular, but sufficient to quantify the deterioration in trap effectiveness and test whether the press has dropped alongside it.

### Part 3 — What a full comparison would need
A methodological section describing the study that would definitively answer the cross-era question: continuous tracking data (SkillCorner / Second Spectrum), StatsBomb 360 freeze frames, and the specific variables and model structure required.

## Data

| Source | Coverage | Granularity |
|---|---|---|
| [StatsBomb Open Data](https://github.com/statsbomb/open-data) | La Liga 2004/05–2020/21 | Full event data with coordinates |
| [FBref](https://fbref.com) | La Liga + UCL 2024/25–2025/26 | Per-match aggregates |
| [Understat](https://understat.com) | La Liga 2024/25–2025/26 | Shot-level with xG and location |

## Main results

> *To be completed during analysis.*

## Club-facing conclusion

> *To be completed during analysis.*

---

## Repository structure

```
Barca-tactics/
├── data/
│   ├── raw/          # fetched at runtime — not committed
│   └── processed/    # computed per-match features
├── notebooks/
│   ├── 01_data_audit.ipynb          # what data is available and what events matter
│   ├── 02_messi_era_offside.ipynb   # Part 1: mechanism analysis
│   ├── 03_flick_era.ipynb           # Part 2: FBref/Understat analysis
│   └── 04_ideal_study_design.ipynb  # Part 3: what a full comparison needs
├── src/
│   └── barca_tactics/
│       ├── data.py      # data loading helpers
│       ├── metrics.py   # PPDA, offside extraction, etc.
│       └── viz.py       # plotting helpers
├── reports/figures/
├── requirements.txt
└── README.md
```

## Reproducing the analysis

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

StatsBomb data is fetched automatically via `statsbombpy`. FBref and Understat data are fetched in the respective notebooks.

---

*Portfolio project — Slimane Dridi, September 2026.*
