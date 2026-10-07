# Jev and Laya Model Use Cases

This repository contains practical Jupyter notebooks demonstrating structured decision workflows with Jev and Laya. Jev is accessed through the BeatAI API; Laya is an open-source model used through its Python package. The examples cover text classification, routing, configurable checks, and AI safety.

## About the models

### Jev

Jev is a **System One model** for structured decisions that software can use directly. Rather than generating a free-form response, it takes unstructured input (the task's state) and returns typed results that follow a predefined schema. Applications can use these results for classification, routing, scoring, extraction, or conditional branching.

Jev returns probabilities and confidence scores so applications can account for uncertainty. It is designed for decision steps within software workflows, rather than general-purpose text generation or chat.

The examples use Jev's three decision primitives:

- **`noul`** — a yes/no decision.
- **`choice`** — a selection from named options.
- **`score`** — an ordered or numerical assessment.

The Jev examples call the BeatAI API using the `jev-1.13-free` model identifier. Running them requires a BeatAI API key with access to Jev.

### Laya

Laya is an open-source, multilingual, non-autoregressive System 1 decision model. It accepts a **state**—such as text, an email, a support ticket, or JSON—and typed questions, then returns structured answers with probabilities instead of free-form text. This repository runs Laya locally through the `laya` Python package; it does not use the BeatAI API for Laya.

The Laya examples use the package's `Router` interface and `Router.predict(state, questions)` method. They demonstrate yes/no (`noul`), category selection (`choice`), and ordered assessment (`score`) decisions. Laya's router can detect language and script and route across supported languages; actual language coverage and performance depend on the package version and runtime setup.

Treat Jev and Laya outputs as model-generated results, not guaranteed facts or replacements for application logic, policy checks, or human judgment.

## Use cases

The notebooks include examples for:

- **Customer support:** classify incoming tickets, identify urgent issues, and suggest a suitable team or queue.
- **Content moderation:** identify potentially unsafe or policy-violating content and categorize the concern.
- **Resume screening:** structure candidate information against stated criteria; do not use outputs as the sole basis for hiring decisions.
- **E-commerce reviews:** flag reviews that may warrant further investigation for suspicious or incentivized activity.
- **Sentiment and sales:** summarize sentiment and help categorize leads by intent or qualification signals.
- **Content quality checks:** surface potential bias or unsupported claims in news and articles.
- **IT and security operations:** triage incident logs, assess tool-call risk, prioritize alerts, and categorize security events.
- **Medical and legal intake:** organize symptoms or contract issues for qualified professionals to review; these examples do not provide professional advice.
- **AIOps and anomaly review:** demonstrate urgency scoring and numerical assessments for operational events.
- **AI security guardrails:** check for prompt-injection attempts, sensitive-data concerns, and potentially destructive agent actions.

These notebooks are educational examples, not production-ready safety controls. Evaluate the models with representative data, add application-side validation and escalation rules, and require qualified human review for consequential decisions—especially in medical, legal, hiring, security, and financial settings.

## Notebooks

| Notebook | Description |
| --- | --- |
| [jev-laya-model-use-cases.ipynb](jev-laya-use-cases.ipynb) | Business and operational examples using Jev and Laya: support triage, moderation, screening, review checks, sentiment, lead qualification, bias checks, security logs, medical and legal intake, urgency, and anomaly detection. |
| [jev-model-ai-security-use-cases.ipynb](jev-ai-security-use-cases.ipynb) | Jev-focused AI security examples covering prompt injection, sensitive data, agent tool-call review, security operations, and AIOps. |

## Requirements

- Python 3.10 or later
- Jupyter Notebook or Google Colab
- A BeatAI `TYPESAFE_API_KEY` with Jev API access (required for Jev examples)
- The open-source `laya` Python package (required for Laya examples)

Install the Python dependencies from the repository root:

```bash
python -m pip install -r requirements.txt
```

## Jev API access

To access Jev, provide a BeatAI `TYPESAFE_API_KEY` to the notebook. Keep the key in a secure secret store; do not write it directly in notebook cells or commit it to this repository. In Google Colab, store it as a notebook secret named `TYPESAFE_API_KEY` and grant the notebook access.

Jev examples send prompts and sample data to the BeatAI API. Laya examples run through the open-source `laya` package. Do not submit real personal, confidential, or regulated data unless your organization has approved that use.

## Run the notebooks

1. Install the dependencies with `python -m pip install -r requirements.txt`.
2. Open a notebook in Jupyter or Google Colab.
3. For Jev examples, configure the `TYPESAFE_API_KEY` secret and ensure it has Jev API access. For Laya examples, use the installed `laya` package.
4. Run the cells from top to bottom. Jev API calls require network access.

---
