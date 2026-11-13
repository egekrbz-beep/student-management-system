# Relational Student Management & Analytics System

A Python and SQLite application designed to manage student records, course grades, and multi-table academic reporting using relational database principles.

## Architecture & Workflow

```text
  [ ogrenciler.csv ]
          │
          ▼
  ┌───────────────┐
  │  csv_oku.py   │  ──▶ Parses raw student records from CSV
  └───────┬───────┘
          │
          ▼
  ┌───────────────┐     ┌─────────────────┐
  │    main.py    │ ──▶ │  add_grades.py  │
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
