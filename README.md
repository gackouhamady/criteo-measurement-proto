# 🚀 Project Objective

Build an end-to-end mini-pipeline to measure marketing effectiveness across the full purchase cycle: ingestion and structuring of synthetic web logs, funnel definition, descriptive and predictive analyses, and setup of a local interactive dashboard (cost-free).

## 📅 Detailed 1-week plan

```text
Day	Main tasks
Day 1	
• Initialize Git repo and virtual environment
• Collect/generate synthetic dataset (page-view, click, purchase logs)
Day 2	
• Ingest data into SQLite (or Pandas)
• Python scripts for cleaning and normalization
Day 3	
• Design the funnel (e.g.: visit → add-to-cart → purchase)
• Compute key metrics (conversion rate, drop-off)
Day 4	
• Simple predictive model (logistic regression) to estimate purchase probability
• Evaluation (AUC, confusion matrix)
Day 5	
• Simulate an A/B test (effect of a new feature) and measure impact
• Significance statistics (proportion test)
Day 6	
• Create a mini local dashboard with Plotly Dash or Streamlit
• Visualize KPIs and model results
Day 7	
• Write README, document steps and execution instructions
• Packaging (`requirements.txt`), finalize code, and push to Git
```

## ⚙️ Repository setup & structure steps

Initialize the project

```bash
mkdir criteo-measurement-proto && cd criteo-measurement-proto
git init
python -m venv venv
.\venv\Scripts\activate
pip install --upgrade pip
touch requirements.txt
```

Install dependencies
In `requirements.txt`, list:

```
nginx
pandas
numpy
sqlalchemy
scikit-learn
plotly
dash         # or streamlit
pytest       # for unit tests
```

Then:

```bash
pip install -r requirements.txt
```

```text
criteo-measurement-proto/
├── data/                  # datasets (raw & processed)
├── notebooks/             # exploratory analyses
├── src/
│   ├── ingestion.py       # import and cleaning scripts
│   ├── modeling.py        # funnel definition & models
│   ├── evaluation.py      # evaluation functions and A/B test
│   └── dashboard.py       # Dash or Streamlit app
├── tests/                 # pytest unit tests
├── docs/                  # documentation and diagrams
├── .gitignore
└── README.md
```

## Incremental development

* **Ingestion** (`src/ingestion.py`): read CSV, clean, load into SQLite via SQLAlchemy or store as Parquet.

* **Modeling** (`src/modeling.py`): build the funnel, prepare X, y, train `LogisticRegression`.

* **Evaluation** (`src/evaluation.py`): metrics (accuracy, AUC), proportion test function for a simulated A/B.

* **Dashboard** (`src/dashboard.py`): display interactive funnel, ROC curves, and A/B test results.

* **Tests & quality**

Write simple tests in `tests/` to validate that a sample dataset produces the correct KPIs.

Run:

```bash
pytest --maxfail=1 --disable-warnings -q
```

## Dashboard

Modular Python scripts for ingestion, modeling, evaluation, and dashboard.

A local interactive dashboard (Dash or Streamlit) measuring:

* The full funnel (visits → purchases)

* Predictive model performance

* Simulated feature impact via A/B test

Unit tests ensuring reproducibility.

Documentation (text + diagrams) explaining the pipeline.

## This project covers:

* Large-scale data mining (synthetic logs),

* Scalable pipeline (modular scripts, SQL/Parquet),

* Analyses & tests (funnel, A/B, predictive modeling),

* Visualization and reporting (interactive dashboard),

* Common tools (Python, SQL, scikit-learn, Dash).
