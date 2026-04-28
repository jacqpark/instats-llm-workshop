# instats-llm-workshop

A 3-day intensive webinar workshop teaching political scientists with little or no LLM background to use large language models for measurement and data wrangling.

## Day 1. What is an LLM, and which kind do I want?

Files in [`day1/`](./day1/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser. Arrow keys or click to advance, `F` for fullscreen.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab Pro with GPU. Reads the NTE corpus from Google Drive at `MyDrive/nte_text/NTE_IPR_final_v2.csv`.
- `handson.ipynb`. Participant notebook. Self-contained, runs on free Colab CPU in under 3 minutes. Five real NTE excerpts, three small experiments.
- `cheat_sheet.html`. One-page printable reference. Encoder vs generative decision, code snippets, model IDs, common pitfalls.

## Day 2. From a model to a measurement.

Files in [`day2/`](./day2/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab Pro with GPU. Reuses the NTE corpus from Day 1. Builds a 30-paragraph gold set, runs single-hypothesis baseline vs 13-hypothesis weighted ensemble, computes Cohen's kappa and Pearson correlation, aggregates to country-year, and plots Israel and Turkey time series against external events.
- `validation_template.ipynb`. Reusable template. Adapt the CSV path, column names, and hypothesis list to validate your own zero-shot pipeline against your own gold set.
- `cheat_sheet.html`. One-page printable. Five-step pipeline, codebook rules, kappa thresholds, hypothesis-engineering recipe, validation appendix checklist.

## Day 3. Generative LLMs for wrangling and crawling.

Files in [`day3/`](./day3/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab with an Anthropic API key. Extracts a four-field schema (signatories, agreement type, year, sector) from 50 messy news leads using Claude Haiku 4.5 with prompt caching, runs four programmatic validity checks, then crawls five CSIS analysis articles with a polite Python requests pipeline and re-extracts the same schema from the parsed text. Includes a Qwen 2.5-1.5B no-key fallback cell for participants without an API key.
- `news_leads.csv`. 50 constructed news leads spanning trade, climate, defense, health, finance, IP, infrastructure, and security. Mix of clean and intentionally messy.
- `cheat_sheet.html`. One-page printable reference. Schema design, prompt-caching pattern, four programmatic validity checks, robots.txt etiquette, polite-fetch helper.

## About the workshop

Hosted by Jihye Park at the University of Geneva. The Day 1 stance demo anchors on Park's R&R paper at the *Review of International Organizations*, "Aid, Lending, and TRIPS," which uses DeBERTa-v3-large with 13 weighted NLI hypotheses on US National Trade Estimate reports 1995 to 2022. Replication data for that paper lives in the separate [`nteText`](https://github.com/jacqpark/nteText) R package.
