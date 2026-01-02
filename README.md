
---

# Automated Daily Indian Economic Insights Pipeline

## Project Summary

Built an end-to-end automation system that converts **daily Indian economic news into structured, consulting-grade insights** and publishes them across platforms with controlled AI usage.

The project demonstrates skills in **automation design, prompt engineering, API governance, and content reuse**, rather than simple AI prompting.

---

## Problem Addressed

Professionals and analysts face two recurring challenges:

1. Producing consistent, high-quality economic insights requires time and discipline.
2. Reusing the same insight across platforms often leads to duplication or inefficiency.

This system addresses both by:

* Generating one high-quality analysis per day
* Reusing it across long-form and short-form platforms without repeated AI calls

---

## What This Project Does

* Fetches **credible Indian economic news** using RSS feeds
* Converts news into **structured, neutral analysis** using an LLM
* Publishes long-form insights automatically to Blogspot
* Generates LinkedIn-ready content from the same report
* Enforces **quota-aware AI usage** to avoid unnecessary API consumption

---

## Skills Demonstrated

### Automation & System Design

* Designed a modular pipeline separating:

  * Data ingestion
  * AI generation
  * Content distribution
* Implemented fallback logic for reliability
* Added safeguards to prevent redundant API calls

### Prompt Engineering

* Created a locked, audit-friendly prompt enforcing:

  * Consulting-style tone
  * Fixed structure
  * Controlled verbosity
  * Elimination of AI artefacts such as questions and meta commentary

### Responsible AI Usage

* Used low-temperature generation for stable, analytical output
* Limited AI calls to one per day by design
* Reused generated content across platforms instead of regenerating

### API & Security Practices

* Integrated OpenRouter for LLM access
* Managed credentials using environment variables
* Avoided hard-coded secrets and respected platform limits

### Python & Tooling

* Python scripting
* RSS ingestion using `feedparser`
* HTTP API interaction using `requests`
* File-based audit trail for transparency and debugging

---

## Technology Stack

* Language: Python
* LLM Access: OpenRouter (Mistral 7B Instruct)
* News Sources: LiveMint RSS, Economic Times RSS
* Publishing: Blogspot (email-based publishing)
* Distribution: LinkedIn-ready content generation (offline)

---

## Project Structure

```
.
├── report_generator.py      # News ingestion and AI analysis
├── linkedin_generator.py    # Converts report to LinkedIn format
├── news_today.txt           # Raw news snapshot
├── prompt_today.txt         # Exact AI prompt used
├── daily_report.txt         # Final analytical report
├── linkedin_post.txt        # LinkedIn-ready summary
└── README.md
```

---

## Automation Flow

1. Fetch top Indian economic news via RSS
2. Build a structured, locked prompt
3. Generate a single analytical report
4. Save all intermediate and final artefacts
5. Publish the report to Blogspot
6. Reuse the same output for LinkedIn content

This design minimizes API usage while maintaining consistency and quality.

---

## Why This Project Matters

The project reflects real-world constraints common in consulting, analytics, and product roles:

* Limited budgets
* API quotas
* Need for explainability
* Repeatable, auditable outputs

The focus is on **design judgment and system thinking**, not model complexity.

---

## Potential Enhancements

* Scheduled daily execution
* Date-based file versioning
* Market data integration (commodities, macro indicators)
* Automated LinkedIn posting
* Multi-model comparison experiments

---

## Author Note

This project was built as a learning exercise in:

* Prompt engineering
* AI-assisted content systems
* Responsible automation design

It intentionally avoids scraping and paid APIs to focus on ethical, transparent workflows.

---

