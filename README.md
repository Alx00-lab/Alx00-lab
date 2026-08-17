<h1 align="center">Hi, I'm Alexander 👋</h1>
<h3 align="center">Data / Analytics Engineer — I build the pipelines that make raw data trustworthy</h3>

<p align="center">
I take messy, unreliable data and turn it into pipelines that are tested, orchestrated, and safe to build decisions on.<br/>
Not dashboards first — <b>infrastructure</b> first. The dashboard only matters if the numbers underneath it are right.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white" alt="SQL"/>
  <img src="https://img.shields.io/badge/dbt-FF694B?style=flat&logo=dbt&logoColor=white" alt="dbt"/>
  <img src="https://img.shields.io/badge/BigQuery-4285F4?style=flat&logo=googlebigquery&logoColor=white" alt="BigQuery"/>
  <img src="https://img.shields.io/badge/Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white" alt="Airflow"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white" alt="Docker"/>
</p>

---

### What I do

```
Raw data  →  Python (extract & clean)  →  dbt (transform)  →  BigQuery (warehouse)  →  Airflow (orchestrate)
```

- **Pipeline engineering** — ingestion → cleaning → transformation → load, built as code, not one-off notebooks
- **Data quality as a first-class step** — every null-replacement rule, every type coercion is verified against real data before it ships, not assumed
- **Orchestration & containerization** — pipelines that run on a schedule and are reproducible anywhere, not "works on my machine"

---

### Stack

| Layer | Tools | Depth |
|---|---|---|
| Languages | `Python` · `SQL` | pandas for ETL scripting · window functions, CTEs, query optimization |
| Transformation | `dbt` | staging → intermediate → marts, tests, documentation |
| Warehouse | `BigQuery` · `DuckDB` (local dev) | cloud target + local dev warehouse before promoting to prod |
| Orchestration | `Airflow` | DAG design for multi-step pipelines (extract → clean → transform → validate) |
| Quality | `dbt tests` · `Great Expectations` | contract-style assertions, regression tests for known data bugs |
| Containers | `Docker` | containerizing full pipelines for reproducible runs |
| Versioning | `Git` / `GitHub` | |

---

### Featured Projects

#### 🎫 [IT Support Ticket Pipeline](https://github.com/Alx00-lab/Ticket_Automate_pipeline) — *in active development*
End-to-end pipeline on a 100,000-row ticket dataset: extraction → cleaning → transformation → warehouse, orchestrated and containerized.

- Built a validated extraction layer and caught a silent data-loss bug where pandas' default null-handling was quietly wiping ~20,000 legitimate values
- Two distinct, data-verified rules for placeholder-to-null conversion: assumed `csat_score = 0` was gated by ticket status, same as `resolution_time_hours` — ran a cross-tab before shipping the rule and found a flat ~30% zero-rate across every status, terminal and non-terminal alike. That meant it was a universal "not rated" sentinel, not a state-dependent placeholder, so the rule changed to match what the data actually showed
- Currently loading into DuckDB locally, then building the dbt models on top before promoting to BigQuery, with Airflow orchestration and Docker containerization next

`Python` · `pandas` · `SQL` · `dbt` · `BigQuery` · `Airflow` · `Docker`

#### 🧾 [Invoice PDF Extractor](https://github.com/Alx00-lab/invoice-extractor) — *live tool, warehouse layer in progress*
A working extraction tool that pulls structured data out of unstructured invoice PDFs, with a public demo.

- 🔗 **[Live demo](https://invoice-extractor-cmdkq7ehi57dhjqgqbzlj6.streamlit.app/)**
- Adding a dbt transformation layer and a BigQuery load so extracted invoice data lands in a queryable warehouse, not just a UI

`Python` · `Streamlit` · `dbt` · `BigQuery`

#### 📊 API Ingestion + Dimensional Modeling — *planned*
A pipeline built from a live public API (not a static CSV), with an explicit star or snowflake schema designed and documented — the piece the other two projects don't cover.

`Python` · `dbt` · `BigQuery` · `Dimensional Modeling`

---

### Currently focused on

Finishing the ticket pipeline's dbt + BigQuery layer, then Airflow and Docker — applying for **Data/Analytics Engineer** and **ETL Developer** roles as each stage ships, rather than waiting for a "finished" portfolio.

---

### Let's connect

Open to remote **Data Engineer / Analytics Engineer** roles. If you're building a data team and want someone who owns the pipeline end to end — reach out.

<!-- Add your links: LinkedIn · Email -->
