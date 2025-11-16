# Private Capital Research and GPTs

Overview
--------
This repository collects research, datasets, code examples, tutorials, notebooks, and GPT artifacts (specialized prompt sets / model configurations) related to private capital investing and research workflows.

This README is intended to be a single, discoverable reference that describes:
- What is in the repo and where to find it
- How the GPT assets are organised and how to use them
- Contribution, licensing, and contact information

Repository snapshot
-------------------
This README corresponds to the repository state at commit: `60264c58fb6807a08b16c60a5b34facd12778040`. If you are viewing a newer commit or branch, verify that any file or directory names referenced here still match the repository layout.

Top-level structure (canonical / expected)
------------------------------------------
The repository is organised into the following high-level folders. If a folder below does not exist yet in this repository, consider it the recommended place to add that type of content.

- research/        — Research papers, write-ups, and analytical reports (PDF, DOCX, or Markdown).
- datasets/        — Raw and processed datasets used for private capital analysis (CSV, parquet, JSON).
- code/            — Scripts, utilities, and example projects (Python, R, or other languages).
- notebooks/       — Jupyter / Colab notebooks demonstrating analysis or reproducible research.
- tutorials/       — Step-by-step guides for reproducing analyses and using code or models.
- gpts/            — GPT artifacts: prompt collections, fine-tune configs, agent-configs, and README for each GPT.
- examples/        — Small runnable examples that demonstrate how to call the GPTs or use the code.
- docs/            — Additional documentation, diagrams, or design notes.
- LICENSE          — Project license (MIT).
- README.md        — This file (overview + usage).

Content index (high-level)
--------------------------
Note: Replace or expand these items to reflect the exact files present in your repository.

1. Research Papers
   - research/ — contains research papers and internal reports analyzing private capital markets, fund structures, returns, and case studies.
   - Each paper should include a short summary README or has a top-level index.md in the research/ folder.

2. Datasets
   - datasets/raw/ — original unmodified data (with README describing source, license, and collection date).
   - datasets/processed/ — cleaned and feature-engineered datasets used by notebooks and models.
   - Each dataset directory should include a data dictionary and example usage notebook.

3. Code Examples
   - code/analytics/ — core analytics functions and utilities.
   - code/etl/ — data collection and ETL scripts.
   - code/modeling/ — model training, evaluation scripts and model artifacts.

4. Tutorials & Notebooks
   - tutorials/ — step-by-step guides (Markdown) for common workflows (data ingestion, portfolio construction, valuation models).
   - notebooks/ — Jupyter notebooks referenced from the tutorials or used as reproducible research.

5. GPTs (Prompt & Model Artifacts)
   - gpts/ contains one directory per GPT or agent. Each GPT directory should include:
     - README.md — brief description: intended use-case, authors, limitations, and example prompts.
     - metadata.json (recommended) — machine-readable metadata (see example schema below).
     - prompts/ — prompt templates, few-shot examples, and variants.
     - config/ — runtime or deployment configuration files (if any).
     - examples/ — example inputs and expected outputs, tests, or evaluation notes.

   Example GPT directory layout
   gpts/
     └─ research-assistant/
         ├─ README.md
         ├─ metadata.json
         ├─ prompts/
         │   ├─ summarize_investment_memo.md
         │   └─ extract_key_terms.md
         ├─ examples/
         └─ config/

   Example metadata.json schema (suggested)
   {
     "name": "research-assistant",
     "version": "0.1.0",
     "author": "Tanya Matanda",
     "description": "Assists with summarizing memos, extracting key investment terms, and drafting diligence checklists for private capital deals.",
     "intended_use": "research/diligence support",
     "limitations": "Not legal or tax advice. Validate outputs before use in production.",
     "source_files": ["prompts/summarize_investment_memo.md"],
     "license": "MIT"
   }

How to use the GPT artifacts
----------------------------
- Read the GPT README first: Each GPT folder must contain a README describing:
  - purpose and scope
  - required inputs and expected outputs
  - privacy considerations (what data can be provided)
  - evaluation notes and known failure modes

- Running prompts locally:
  1. Choose the GPT folder under gpts/
  2. Open the prompt templates in prompts/ and adapt the few-shot examples to your dataset.
  3. Use your local tooling or an API wrapper to send inputs and receive outputs. Example wrappers are in code/ (see code/examples or code/modeling).

- Examples and tests:
  - Use the examples/ subfolder in each GPT directory to validate behavior.
  - Maintain minimal unit-style tests for critical prompts (even simple input-output pairs) to detect regressions after edits.

Documentation & Reproducibility
-------------------------------
- Every dataset should include provenance and a license note.
- Notebooks should be runnable (or have a small README describing required environment and data paths).
- Code should include a requirements.txt (Python) or environment specification so others can reproduce the results.

Contribution guidelines
-----------------------
Please follow these standards when contributing:
- Open an issue to discuss major additions or breaking changes.
- Prefer small, focused pull requests with a clear description and tests / examples where appropriate.
- For new GPT artifacts:
  - Add a directory under gpts/ with README.md and metadata.json.
  - Provide example inputs and expected outputs in examples/.
  - Document any external dependencies or API keys (do not commit secrets—use environment variables).

License
-------
This repository is licensed under the MIT License. See the LICENSE file for full terms.

Contact
-------
Owner: TanyaMatanda (GitHub profile: https://github.com/TanyaMatanda)
For questions or access requests, open an issue in this repository.

Acknowledgements
----------------
This project collects and curates materials related to private capital research and purpose-built GPT artifacts for productivity and analysis. Where external datasets or papers are included, please see the specific files for source attribution and license details.