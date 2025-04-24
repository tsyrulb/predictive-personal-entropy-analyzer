# Predictive Personal Entropy Analyzer (PPEA) — *Work-in-Progress* 🚧

A portfolio project that explores **AI-driven long-term burnout prediction** by fusing
publicly available workplace- and student-mental-health datasets.

> **Status:** Early data-integration phase – core dataset schema finalized, ETL scripts and baseline notebooks under construction.  
> Check the `roadmap` section below for what’s next.

---

## 🌟 Project Goal

Build a transparent, extensible ML pipeline that:

1. **Ingests** multi-domain data  
   (workload, mental-health surveys, psychological scales, organizational support)
2. **Produces** a unified, per-person feature table with a **Burn Rate (0-1)** label  
3. **Trains** baseline models to forecast burnout risk and highlight key drivers  
4. **Lays groundwork** for future time-series “entropy” tracking and a personal dashboard

---

## 📂 Current Data Sources

| Dataset | Link | Role in PPEA |
|---------|------|--------------|
| Mental Health in Tech Survey (2014) | <https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey> | Workplace support & mental-health attitude features |
| Medical Student Mental Health | <https://www.kaggle.com/datasets/azminetoushikwasi/medical-students-mental-health-data> | Psychological scales – MBI, depression (CES-D), anxiety (STAI) |
| *Are Your Employees Burning Out?* (Burn Rate) | <https://www.kaggle.com/datasets/thedevastator/are-your-employees-burning-out> | Workload + Mental Fatigue + **Burn Rate label** |

*(See `docs/data_catalog.yml` for column mappings and licences.)*

---

## 🛠️ Quick Start

> **Prerequisites:** Python 3.11, Poetry (or pip), and ~1 GB free disk.

```bash
git clone https://github.com/<your-gh-handle>/ppea.git
cd ppea

# 1) Create env & install deps
poetry install    # or: pip install -r requirements.txt

# 2) (One-time) download raw datasets to ./data/raw
python scripts/fetch_datasets.py

# 3) Build the integrated CSV (./data/processed/ppea_integrated.csv)
python scripts/build_dataset.py
