# PEP Stats Excel Generator

## Overview

The PEP Stats Excel Generator is a Python-based reporting tool that extracts country-wise Politically Exposed Persons (PEP) statistics from a PostgreSQL database and generates a structured Excel report using a predefined template.

This tool helps monitor data coverage, completeness, and distribution of PEP profiles across different countries, roles, and hierarchy levels.

> Note: This public version does not include SQL queries. Internal queries can be added in the placeholder function.

---

## Features

- Country-wise PEP statistics generation
- Excel template-based reporting with preserved formatting
- Supports merged Excel headers
- Role and Level matrix support (HOS, CAB, LEG, etc.)
- Automatic country code parsing from input file
- Optional database index creation for performance optimization
- Modular and scalable design

---

## Project Structure

pep-stats-generator/
│
├── stats.py # Main script
├── README.md # Documentation
├── .gitignore # Git ignore rules
├── input.xlsx # Input country list (example)
├── templet.xlsx # Excel template
└── output.xlsx # Generated report


---

## Requirements

Install required Python packages:

```bash
pip install pandas psycopg2-binary openpyxl
Database Requirements
Expected PostgreSQL table:

public.new_master_unified_final
Required fields include:

is_pep

pep_country_code

subject_type

pep_type

pep_level

DOB

locations

alias_name

image_url

gender

position

(Note: SQL queries are intentionally removed in public version.)

Configuration
Update database connection in stats.py:

PG = {
    "dbname": "testdatabase",
    "user": "your_user",
    "password": "your_password",
    "host": "localhost",
    "port": 5432,
}
Update file paths:

INPUT_XLSX = "input.xlsx"
TEMPLATE_XLSX = "templet.xlsx"
OUTPUT_XLSX = "output.xlsx"
How to Run
Run the script:

python stats.py
Output will be generated at:

output.xlsx
How It Works
Reads country codes from input Excel

Connects to PostgreSQL database

Fetches statistics for each country (placeholder in public version)

Maps results to Excel template

Generates formatted report

Future Scope
Automated scheduled reporting

Dashboard integration (Kibana / PowerBI)

Data quality scoring

Historical trend analysis

API integration

Scalable reporting for large datasets

Business Impact
Improves compliance reporting efficiency

Helps monitor data completeness and quality

Reduces manual reporting effort

Enables faster validation after data ingestion

Supports operational and compliance decision-making

Security Notice
This public repository does not include SQL queries or sensitive logic.

Internal SQL queries should be added in:

fetch_stats_for_country()
Author
Divyansh Kumar

Machine Learning & Data Engineer
Specializing in PostgreSQL, Elasticsearch, and AI Systems

License
This project is intended for internal and educational use.


---

# Next Step

Save this file as:

README.md


Then push:

```bash
git add README.md
git commit -m "Added README documentation"
git push
