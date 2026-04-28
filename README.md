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

Coming soon.

## About the workshop

Hosted by Jihye Park at the University of Geneva. The Day 1 stance demo anchors on Park's R&R paper at the *Review of International Organizations*, "Aid, Lending, and TRIPS," which uses DeBERTa-v3-large with 13 weighted NLI hypotheses on US National Trade Estimate reports 1995 to 2022. Replication data for that paper lives in the separate [`nteText`](https://github.com/jacqpark/nteText) R package.
