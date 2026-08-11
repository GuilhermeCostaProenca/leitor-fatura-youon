# Leitor de Fatura — Energy-Bill Parser

A Python service that turns messy energy-bill PDFs into clean, validated, structured data — built for the workflow at YOU.ON.

## What it does

- **Reads bills with Azure AI Document Intelligence** (Form Recognizer) — `src/azure_reader.py`
- **Parses** the extracted content into structured fields (`src/parser/`)
- **Validates** the result before it leaves the pipeline (`src/validador.py`)
- **Serves** it over a small FastAPI app (`src/web_server.py`) with HTML templates
- **Integrates** downstream (e.g. Monday.com) for the operational workflow

## Stack

Python · Azure AI Document Intelligence · FastAPI · Uvicorn · Jinja2

## Getting started

```bash
git clone https://github.com/GuilhermeCostaProenca/leitor-fatura-youon.git
cd leitor-fatura-youon
pip install -r requirements.txt
```

Set your Azure credentials in `.env`, then run the web server from `src/`. Sample bills live in `sample_faturas/`.
