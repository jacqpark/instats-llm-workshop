# instats-llm-workshop

A 3-day intensive webinar workshop teaching political scientists with little or no LLM background to use large language models for measurement and data wrangling.

## Day 1. What is an LLM, and which kind do I want?

Files in [`day1/`](./day1/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser. Arrow keys or click to advance, `F` for fullscreen.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab Pro with GPU. Three sections. A three-line Cardiff Twitter-RoBERTa sentiment demo on five political sentences. A live CPU-vs-GPU benchmark on 1000 UN General Assembly speech sentences. A zero-shot DeBERTa stance pass on roughly 200 sentences from the UN General Debate Corpus 2017 snapshot, with five misclassifications and a calibration histogram.
- `handson.ipynb`. Participant notebook. Self-contained, runs on free Colab CPU in under three minutes. Ten short UN-style sentences, three small experiments (run as-is, change candidate labels, swap in your own text).
- `cheat_sheet.html`. One-page printable reference. Encoder vs generative decision matrix, NLI trick, code snippets for both families, model IDs, common pitfalls.

## Day 2. From a model to a measurement.

Files in [`day2/`](./day2/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab Pro with GPU. Five sections. Stratified 5,000-row sample from the full UN General Debate Corpus. Zero-shot DeBERTa scoring in batches with three candidate labels about climate stance. Speech-level and country-year CSVs. A 30-row hand-coded gold set with confusion matrix, Cohen's kappa, accuracy, Pearson r, Spearman rho, and a subgroup table by era. A time-series plot of climate emphasis 1970 to present with the Paris Agreement marked, plus a regional overlay. Off-the-shelf only, no fine-tuning.
- `validation_template.ipynb`. Reusable participant template. Replace the CSV path, candidate labels, and 30-row gold set to validate any zero-shot pipeline against your own hand codes. Outputs kappa, accuracy, Pearson r, Spearman rho, confusion matrix, and a subgroup table.
- `cheat_sheet.html`. One-page printable. Five-step pipeline, Adcock and Collier 2001 framework, codebook rules, Landis and Koch kappa thresholds, aggregation choices, validation appendix checklist.

## Day 3. Generative LLMs for wrangling and crawling.

Files in [`day3/`](./day3/).

- `slides.html`. Self-contained HTML slide deck. Open in any browser.
- `demo.ipynb`. Instructor notebook. Runs on paid Colab with an Anthropic API key. Extracts a four-field schema (signatories, agreement type, year, sector) from 50 messy news leads using Claude Haiku 4.5 with prompt caching, runs four programmatic validity checks, then crawls five CSIS analysis articles with a polite Python requests pipeline and re-extracts the same schema from the parsed text. Includes a Qwen 2.5-1.5B no-key fallback cell for participants without an API key.
- `news_leads.csv`. 50 constructed news leads spanning trade, climate, defense, health, finance, IP, infrastructure, and security. Mix of clean and intentionally messy.
- `cheat_sheet.html`. One-page printable reference. Schema design, prompt-caching pattern, four programmatic validity checks, robots.txt etiquette, polite-fetch helper.

## Datasets used

- **UN General Debate Corpus** (Day 1, Day 2). Harvard Dataverse, doi:10.7910/DVN/0TJX8Y. CC0. About 8,000 speeches by heads of delegation, 1970 to present. Day 1 uses the 2017 snapshot for stance demos. Day 2 uses the full corpus stratified by year for the walk-through and time-series plot.
- **CSIS analysis articles** (Day 3). Public web pages under csis.org/analysis. Server-rendered HTML, robots.txt permits `/analysis/` for generic crawlers. Five articles fetched with rate limiting.

## Models used

- `cardiffnlp/twitter-roberta-base-sentiment-latest`. Encoder. CC-BY-4.0. ~125M params. Day 1 sentiment baseline.
- `MoritzLaurer/DeBERTa-v3-base-mnli-fever-anli`. Encoder. MIT. ~184M params. Day 1 and Day 2 zero-shot stance workhorse.
- `claude-haiku-4-5-20251001`. Generative. Anthropic API. Day 3 extraction.
- `Qwen/Qwen2.5-1.5B-Instruct`. Generative. Open weights. Day 3 no-key fallback.

## About the workshop

Hosted by Jihye Park at the University of Geneva. Audience is political scientists with some R or Stata familiarity and little to no Python or LLM background. Format is three livestreamed sessions of 2.5 hours each, with one short hands-on segment in Day 1 on free Colab and instructor-driven demos on paid Colab Pro thereafter.
