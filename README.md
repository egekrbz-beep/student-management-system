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
