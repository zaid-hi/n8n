# n8n template

This template deploys a self-hosted version of [n8n](https://n8n.io/). Internally it uses a PostgreSQL database to store the data.

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/r2SNX_?referralCode=fKo7dw)

## ✨ Features

- n8n
- PostgreSQL

## 💁‍♀️ How to use

- Click the Railway button 👆
- Add the required environment variables
- Deploy

## 📝 Notes

- Source image: https://hub.docker.com/r/n8nio/n8n
- Docs: https://docs.n8n.io/

## 🤖 Example automation: find new SDR job applicants

This repo now includes an importable n8n workflow at `workflows/sdr-applicant-sourcing.json` that helps you source **new SDR candidates** automatically.

### What it does

- Runs every 6 hours.
- Searches for SDR candidate profiles by region (Google via SerpAPI).
- Extracts LinkedIn profile leads from results.
- Deduplicates candidates with workflow static data (so you only get net-new leads).
- Sends new leads to Slack (`#recruiting`).

### Setup

1. In n8n, import `workflows/sdr-applicant-sourcing.json`.
2. Add environment variable `SERPAPI_API_KEY` to your n8n deployment.
3. Connect your Slack credential in the `Send To Slack` node.
4. Update `keywords`, `regionsCsv`, and Slack channel as needed.
5. Activate the workflow.

> Note: This workflow is intended as a starting point. You can extend it with ATS sync (Greenhouse/Lever), AI scoring, or Airtable/Notion storage.
