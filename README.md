# TechTalent BI
### European Developer Market Intelligence (2018–2025)

**TechTalent BI** is a Power BI business-intelligence project that explores European developer-survey data to support technology, recruitment, salary-planning, and AI-adoption decisions for a fictional telecommunications and digital-services company.

The project uses the annual Stack Overflow Developer Surveys (2018–2025) as its stated data source and presents the analysis through an interactive Power BI report and an accompanying French academic project report.

> **Portfolio note:** The dashboard and report are included in this repository. The original Python ETL scripts and source CSV files were not present in the supplied ZIP, so the full data-preparation pipeline is not yet independently reproducible from this repository alone.

## Business questions

The analysis is framed around five business units:

1. **Chatbots and conversational AI**
2. **Telecom software**
3. **Web development** — frontend, backend, and databases
4. **Mobile applications**
5. **Cybersecurity**

It aims to help decision-makers explore:

- Which programming languages and developer profiles are represented in the European survey data?
- How do reported salaries vary by experience and technology?
- How has reported use of AI-assisted development tools changed over time?
- What should a new technology company consider when planning hiring and technology investments?

## Dashboard pages

The Power BI file contains four report pages:

| Page | Focus | Example analyses |
|---|---|---|
| **Global** | Overall survey overview | Respondent counts by year, salary and satisfaction KPIs, gender distribution, satisfaction by work arrangement |
| **System** | Developer-market composition | Developer types, experience distribution, language comparisons, salary/satisfaction exploration |
| **Developer** | Compensation and technologies | Salary by language and experience, salary-growth comparisons |
| **AI** | AI-tool adoption | Adoption over time, salary comparison by AI-use status, adoption by language |

The report includes interactive filters for survey year, region, and (where relevant) programming language.

## Data and analytical model

The accompanying report describes annual Stack Overflow Developer Survey CSV files from 2018 through 2025. It states that records were harmonized across survey editions, filtered to a defined European geography, and transformed using Python/Pandas before being loaded into Power BI.

The documented warehouse is a **snowflake-style dimensional model** centered on a developer fact table, with dimensions for profile, technology, geography, time, work, and developer type. Technology-related sub-dimensions include language and database.

The report identifies the following tools:

- **Power BI Desktop** — data model and interactive dashboard
- **DAX** — KPI and measure calculations
- **Python / Pandas** — described ETL and harmonization workflow
- **Stack Overflow Developer Survey** — stated survey source

## Repository contents

```text
.
├── README.md
├── .gitignore
├── powerbi/
│   └── techtalent-bi-dashboard.pbix
├── docs/
│   ├── project-report-fr.pdf
│   ├── methodology-and-model.md
│   ├── validation-notes.md
│   └── figures/
│       └── README.md
└── data/
    └── README.md
```

## Open the dashboard

1. Install **Power BI Desktop** on Windows.
2. Download or clone this repository.
3. Open `powerbi/techtalent-bi-dashboard.pbix`.
4. If Power BI prompts for credentials or data-source access, review the source settings before refreshing.
5. Explore the four report pages and use the available slicers.

The `.pbix` file contains the Power BI report and its model. Exact refresh behavior depends on how its data sources were configured when it was authored.

## Important validation notes

This repository is a cleaned, documented packaging of the supplied files—not a revalidation of the original analysis. Before presenting the findings as evidence or using them for business decisions, review `docs/validation-notes.md`.

In particular, the supplied PDF reports figures that appear inconsistent across sections, including the overall AI-adoption rate and later-year adoption rates. Salary values and growth rates also require validation against the underlying survey fields, currency definitions, filters, and sample sizes. The report's recommendations should be treated as exploratory rather than definitive labor-market advice.

## Reproducibility and next steps

To make this project fully reproducible, add—where you have permission to publish them:

- Python ETL scripts and a clear environment specification
- Dataset download instructions, source links, licenses, and exact survey-year file names
- A data dictionary mapping survey-year columns to standardized fields
- Documented Power Query steps and DAX measures
- A validation notebook or script for row counts, missing values, outliers, and KPI reconciliation
- Exported, approved dashboard screenshots for a quick visual preview

Do not commit restricted survey extracts, personal data, credentials, or large generated files without checking the relevant terms.

## Responsible interpretation

Stack Overflow survey respondents are not necessarily representative of every European developer or of the telecom sector specifically. Survey questions and answer options can change between years. Salary observations are self-reported and may be affected by currency, geography, experience, and missingness. Correlation between AI-tool use and salary does not establish that AI use causes higher pay.

## License

No license is included. Choose a license for your own documentation or code only after confirming the rights and terms applicable to the Power BI file, report, survey data, and any third-party assets.
