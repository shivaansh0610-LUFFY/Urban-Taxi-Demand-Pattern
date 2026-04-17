# 🚖 Urban Taxi Demand Pattern Analysis

> Uncovering when, where, and how often New Yorkers hail a cab — using NYC TLC trip data, Python, and Tableau.

**Project Type:** Data Analytics &nbsp;|&nbsp; **Year & Section:** 2025, Sem 2A
**Mentor:** Navneet Nautiyal &nbsp;|&nbsp; **Team:** Shivaansh Pandey · Prantik

---

## 📌 What This Project Is About

Urban taxi demand is far from predictable. It spikes during rush hours, drops on rainy Sunday mornings, and concentrates around a handful of high-traffic zones. Without understanding these patterns, taxi services and city planners are essentially flying blind.

This project digs into historical **NYC Yellow and Green Taxi trip records** (published monthly by the NYC Taxi & Limousine Commission) to:

- Identify **peak demand hours** across a 24-hour cycle
- Spot **weekday vs. weekend** and **seasonal** demand shifts
- Map demand to **specific boroughs and taxi zones**
- Fit **statistical distributions** to trip metrics (distance, fare, duration)
- Deliver findings through a clean, interactive **Tableau dashboard**

The entire pipeline runs end-to-end on a standard laptop using Python and Jupyter Notebooks, with all steps version-controlled for full reproducibility.

---

## 📂 Project Structure

```
urban-taxi-demand/
│
├── data/
│   ├── raw/                        # Original .parquet files from NYC TLC
│   └── processed/                  # Cleaned & feature-engineered Parquet files
│
├── notebooks/
│   ├── 01_data_ingestion.ipynb     # Download & load raw data
│   ├── 02_data_cleaning.ipynb      # Clean, validate, engineer features
│   ├── 03_eda.ipynb                # Exploratory analysis & visualisations
│   ├── 04_statistical_analysis.ipynb  # Distribution fitting & outlier detection
│   └── 05_dashboard_export.ipynb   # Aggregate & export CSVs for Tableau
│
├── outputs/
│   ├── eda/                        # Saved chart PNGs
│   └── tableau/                    # CSV files ready for Tableau import
│
├── docs/
│   ├── HLD.md                      # High-Level Design
│   ├── LLD.md                      # Low-Level Design
│   ├── Consumer_Flow_Diagram.md    # How each stakeholder uses the system
│   └── Data_Flow_Diagram.md        # Data journey from raw → insight
│
├── utils.py                        # Shared helper functions
├── requirements.txt                # Pinned Python dependencies
└── README.md                       # You are here
```

---

## 🗂️ Dataset

**Source:** [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

| Dataset | Format | Coverage |
|---|---|---|
| Yellow Taxi Trip Records | `.parquet` (monthly) | Manhattan + all boroughs |
| Green Taxi Trip Records | `.parquet` (monthly) | Outer boroughs |
| Taxi Zone Lookup Table | `.csv` | 265 named zones |
| Taxi Zone Shapefile | `.zip` | Borough boundaries |

**Key columns used:**

| Column | What It Tells Us |
|---|---|
| `tpep_pickup_datetime` | When the trip started (demand timestamp) |
| `PULocationID` / `DOLocationID` | Where trips started and ended (zone ID) |
| `trip_distance` | How far the ride was |
| `fare_amount` / `total_amount` | Revenue-side analysis |
| `passenger_count` | Occupancy patterns |

---

## 🛠️ Tech Stack

| Purpose | Tool |
|---|---|
| Language | Python 3.10+ |
| Data Wrangling | Pandas, NumPy |
| Statistical Analysis | SciPy |
| Visualisation | Matplotlib, Seaborn |
| Dashboard | Tableau Public / Power BI |
| Notebooks | Jupyter Notebook / JupyterLab |
| Data Format | Apache Parquet (PyArrow) |
| Version Control | Git + GitHub |

---

## ⚙️ How to Run This Project

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/urban-taxi-demand.git
cd urban-taxi-demand
```

### 2. Set up the Python environment

```bash
python -m venv venv
source venv/bin/activate       # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Run the notebooks in order

Open JupyterLab or Jupyter Notebook and run the notebooks **in sequence**:

```
01_data_ingestion.ipynb       ← Downloads raw Parquet files
02_data_cleaning.ipynb        ← Cleans and validates the data
03_eda.ipynb                  ← Generates EDA charts
04_statistical_analysis.ipynb ← Runs distribution fitting & stats
05_dashboard_export.ipynb     ← Produces CSVs for Tableau
```

### 4. Load the dashboard

Import the CSV files from `outputs/tableau/` into Tableau Public or Power BI to build (or refresh) the demand dashboard.

---

## 📐 Design Documents

All technical design documentation lives in the `/docs` folder:

| Document | Description |
|---|---|
| [HLD.md](./docs/HLD.md) | **High-Level Design** — System overview, architecture, tech stack, and key decisions |
| [LLD.md](./docs/LLD.md) | **Low-Level Design** — Module breakdown, function signatures, schemas, and error handling |
| [Consumer_Flow_Diagram.md](./docs/Consumer_Flow_Diagram.md) | **Consumer Flow** — How the Data Analyst, City Planner, Taxi Ops team, Policy Maker, and Mentor each interact with the system |
| [Data_Flow_Diagram.md](./docs/Data_Flow_Diagram.md) | **Data Flow Diagram** — Level 0 → Level 2 breakdown of how every row of data travels from raw Parquet to final insight |

---

## 📊 Key Analysis Outputs

Once all notebooks are run, you'll have:

- 📈 **Hourly demand curve** — Which hours of the day see the highest trip volume
- 📅 **Weekly heatmap** — Day-of-week × hour demand intensity
- 🗺️ **Zone-level demand map** — Top 10 pickup zones ranked by trip count
- 📉 **Distribution charts** — Histograms and KDE plots for distance, fare, and duration
- 📋 **Statistical summary table** — Mean, median, skewness, kurtosis, and best-fit distribution per metric
- 🖥️ **Tableau dashboard** — Interactive, filterable stakeholder view

---

## ✅ Evaluation Criteria Coverage

| Criterion | How We Address It |
|---|---|
| Clean, reproducible code | Modular notebooks + `utils.py` + `requirements.txt` |
| Statistical rigour | SciPy distribution fitting, KS tests, IQR outlier detection |
| Visual storytelling | Seaborn/Matplotlib charts + Tableau dashboard |
| Stakeholder-readiness | Filtered dashboard + executive summary PDF |
| Version control | Full Git history on GitHub |

---

## 👥 Team & Responsibilities

| Task | Shivaansh | Prantik |
|---|---|---|
| Data ingestion & cleaning | ✅ | ✅ |
| EDA & distribution analysis | ✅ | ✅ |
| Dashboard development | ✅ | ✅ |
| Documentation & presentation | ✅ | ✅ |

---

## 📅 Project Timeline

| Week | Milestone |
|---|---|
| Week 1 | Project launch, problem scoping, dataset access |
| Week 2 | Consumer flows & product design |
| Week 3 | HLD + LLD technical design |
| Week 4 | Data ingestion, cleaning, EDA (core notebooks) |
| Week 5 | Statistical analysis & feature completion |
| Week 6 | Evaluation & first working pipeline |
| Week 7 | Deployment & public dashboard |
| Week 8 | Scalability review & engineering maturity check |
| Week 9 | Final evaluation & project defence |

---

## 📄 License

This project is for educational purposes as part of the OJT 2026 programme. Data is sourced from the publicly available [NYC Open Data / TLC Trip Records](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page).
