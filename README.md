# Technology-IR-Project

Information Storage and Retrieval project — Technology version, implemented with Python and PySpark.

## Project structure

```text
Technology-IR-Project/
├── data/
│   ├── d1.txt
│   ├── d2.txt
│   ├── d3.txt
│   ├── d4.txt
│   ├── d5.txt
│   ├── d6.txt
│   ├── d7.txt
│   ├── d8.txt
│   ├── d9.txt
│   └── d10.txt
├── src/
│   ├── dataset_processing.py
│   ├── positional_index.py
│   ├── statistics.py
│   ├── weighting.py
│   ├── queries.py
│   └── similarity_ranking.py
├── results/
│   └── .gitkeep
├── main.py
├── requirements.txt
├── README.md
└── .gitignore
```

## Requirements

- Python
- Java JDK (required by Spark)
- PySpark

## Setup (Windows PowerShell)

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Run

```powershell
python main.py
```

## Dataset and calculation conventions

- The `data/` directory contains the ten supplied Technology documents.
- Convert terms to lowercase and tokenize on whitespace.
- Token positions start at 1 in each document.
- Number of documents: `N = 10`.
- `IDF(t) = log10(N / DF(t))`.
- Weighted TF for a nonzero term frequency: `1 + log10(TF)`.
- `TF-IDF = Weighted TF * IDF`.
- Use L2 normalization for document and query vectors.

## Required queries

- Phrase query: `machine learning`
- Phrase query: `data science`
- Boolean query: `machine learning AND data science`
- Boolean query: `machine learning AND NOT data science`

## Team responsibilities

1. `dataset_processing.py` — dataset loading and tokenization.
2. `positional_index.py` — Spark positional index.
3. `statistics.py` — TF, DF, and IDF.
4. `weighting.py` — TF-IDF and normalization.
5. `queries.py` — phrase and Boolean query processing.
6. `similarity_ranking.py` — similarity scores and ranking.

The source files are starter modules; implementation will be added in the corresponding project stages.
