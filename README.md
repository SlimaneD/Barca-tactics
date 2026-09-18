# Does Barça Change Its Identity Away From Home?

**Measuring tactical adaptation with StatsBomb event data.**

---

## The question

Most football teams play more aggressively at home than away — a pattern consistent with the *Bourgeois* strategy from evolutionary game theory (Hawk when owner, Dove when intruder). Does FC Barcelona follow this pattern, or does it impose its tactical identity regardless of venue?

## Why it matters

For a professional club, knowing *which* tactical behaviours are venue-dependent — and which remain constant — has direct applications:

- **Self-evaluation**: identify dimensions of play that "travel" vs. those that don't.
- **Opponent preparation**: if Barça adapts less than typical opponents, that changes how you approach them at home vs away.
- **Training design**: stress-test the behaviours that tend to collapse under away conditions.
- **KPI monitoring**: track match-to-match tactical identity rather than just outcomes.

## Data

[StatsBomb Open Data](https://github.com/statsbomb/open-data) — Barcelona La Liga matches from the Messi era (2004/05–2020/21). Rich event data including passes, carries, pressures, duels, and shots with x/y coordinates.

## Method (plain language)

1. **Measure tactical aggression** across multiple dimensions — pressing intensity, defensive action height, progressive passing, territorial occupation — rather than collapsing everything into a single score too early.
2. **Compare home vs away** for the same Barça–opponent pair across seasons, holding opponent identity roughly constant.
3. **Control for relative strength**: a very dominant team may appear always-aggressive simply because it is always stronger. We separate the *identity* hypothesis from the *resource-holding potential* hypothesis.
4. **Uncertainty**: bootstrap confidence intervals and mixed-effects models that account for match-level and opponent-level clustering.

## Main results

> *To be completed during analysis.*

## Actionable conclusions

> *To be completed during analysis.*

---

## Repository structure

```
Barca-tactics/
├── data/
│   ├── raw/          # StatsBomb JSON (not committed — fetched via statsbombpy)
│   └── processed/    # computed per-match features
├── notebooks/
│   ├── 01_data_audit.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_modelling.ipynb
│   └── 04_club_report.ipynb
├── src/
│   └── barca_tactics/
│       ├── data.py      # data loading helpers
│       ├── metrics.py   # aggression dimension computations
│       └── viz.py       # plotting helpers
├── reports/
│   └── figures/
├── requirements.txt
└── README.md
```

## Reproducing the analysis

```bash
# 1. Create and activate a virtual environment
python -m venv .venv && source .venv/bin/activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch JupyterLab
jupyter lab
```

StatsBomb data is fetched automatically via `statsbombpy` — no manual download required.

---

*Portfolio project — Slimane Dridi, September 2026.*
