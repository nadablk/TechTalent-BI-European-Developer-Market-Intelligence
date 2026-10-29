# Methodology and data model

## Project objective

The project frames a business-intelligence question for a proposed technology and telecommunications company: how can developer-market survey data inform technology choices, recruitment profiles, compensation planning, and investment in AI-assisted development tools?

## Stated source and scope

The supplied French report identifies annual Stack Overflow Developer Surveys from 2018 to 2025 and a European geographic focus. It describes extraction and transformation with Python/Pandas, followed by loading and analysis in Power BI.

The report describes harmonization across survey editions, standardization of developer types, experience bucketing, salary normalization to USD, an AI-use indicator, and different missing-value handling for salary versus popularity analyses. The source ZIP did not contain the Python ETL scripts or the source CSV files, so these steps are documented from the report rather than independently reproduced here.

## Dimensional model described in the report

The report describes a snowflake-style model with a central developer fact table and dimensions including:

- **Profile** — age, education, experience, gender, and years coding
- **Technology** — AI-use attributes and technology identifier
- **Geography** — country, region, and geography identifier
- **Time** — survey year and period
- **Work** — employment, industry, organization size, and remote-work attributes
- **Developer type** — standardized developer categories
- **Language / Database** — technology sub-dimensions

The report describes measures such as average salary, average job satisfaction, total respondents, AI adoption, and salary growth.

## Dashboard page intent

- **Global:** headline KPIs and broad population trends.
- **System:** developer profile, experience, and language landscape.
- **Developer:** salary patterns by experience and language.
- **AI:** AI-tool adoption patterns over time and by language.

## Interpretation

The dashboards are descriptive and exploratory. Comparisons across survey years require careful handling of changing question wording, available answer choices, missingness, and survey participation. The model should not be interpreted as a representative census of European developers or as telecom-sector-specific salary data.
