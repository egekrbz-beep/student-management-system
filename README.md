# Relational Student Management & Analytics System

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Relational_DB-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production_Ready-2EA44F?style=flat-square)

An end-to-end relational database and academic reporting pipeline built in **Python** and **SQLite**. Designed to ingest student records from CSV files, maintain normalized relational schemas, and execute multi-table `JOIN` analytics queries.

---

## Architecture & Workflow

```text
  [ ogrenciler.csv ]
          │
          ▼
  ┌───────────────┐
  │  csv_oku.py   │  ──▶ Extracts & parses raw student records from CSV
  └───────┬───────┘
          │
          ▼
  ┌───────────────┐     ┌─────────────────┐
  │    main.py    │ ──▶ │  add_grades.py  │  ──▶ Schema creation & grade ingestion
  └───────┬───────┘     └────────┬────────┘
          │                      │
          ▼                      ▼
  ┌───────────────────────────────────────┐
  │        SQLite Relational DB           │
  │    (Students & Grades Tables)         │
  └───────────────────┬───────────────────┘
                      │
                      ▼
  ┌───────────────────────────────────────┐
  │      sorgula.py / query_join.py       │  ──▶ Multi-table SQL JOIN reporting
  └───────────────────────────────────────┘

student-management-system/
├── ogrenciler.csv              # Source dataset containing raw student records
├── csv_oku.py                  # CSV ingestion and parsing utility
├── main.py                     # Core database initialization & student table setup
├── add_grades.py               # Relational grade insertion and foreign-key mapping
├── pipeline_okul_projesi.py    # End-to-end execution orchestrator
├── sorgula.py                  # Single-table lookup and filtering queries
├── query_join.py               # Multi-table INNER/LEFT JOIN analytical reports
└── README.md                   # Project documentation
