# Jev and Laya Model Use Cases

Example notebooks demonstrating how to use BeatAI's Jev and Laya models for structured classification, routing, and AI safety workflows.

## Notebooks

| Notebook | Description |
| --- | --- |
| [jev-laya-use-cases.ipynb](jev-laya-use-cases.ipynb) | Jev and Laya examples for support triage, content moderation, resume screening, review fraud, sentiment, lead qualification, bias checks, security logs, medical triage, legal risk, urgency, and anomaly detection. |
| [jev-ai-security-use-cases.ipynb](jev-ai-security-use-cases.ipynb) | Jev examples for prompt-injection detection, sensitive-data handling, agent tool-call checks, security operations, and AIOps. |

These notebooks are examples, not production-ready safety controls. Validate model output and require qualified human review for consequential decisions, especially medical, legal, hiring, security, and financial workflows.

## Requirements

- Python 3.10 or later
- Jupyter Notebook or Google Colab
- A BeatAI API key with access to the models used by the notebooks

Install the Python dependencies from the repository root:

```bash
python -m pip install -r requirements.txt
```

## Authentication

The notebooks currently retrieve `TYPESAFE_API_KEY` through Google Colab's `userdata` secret store. In Colab, add a secret named `TYPESAFE_API_KEY` and grant the notebook access to it before running API cells.

Never paste an API key into a notebook, commit it to Git, or include it in notebook output. If adapting the notebooks for a local Jupyter environment, load the key from an environment variable or another secure secret manager instead.

The examples send prompts and sample data to the BeatAI API. Do not submit real personal, confidential, or regulated data unless your organization has approved that use.

## Run the notebooks

1. Clone or download this repository.
2. Install the dependencies listed above.
3. Configure the `TYPESAFE_API_KEY` secret in Google Colab.
4. Open either notebook and run its cells from top to bottom.

Some examples use `laya`'s `Router` API in addition to direct Jev API calls. Refer to the notebook and the package documentation for model and schema details.

## Push to GitHub

Create an empty repository on GitHub, then run these commands from this directory, replacing the placeholder with your repository URL:

```bash
git init
git add README.md requirements.txt .gitignore *.ipynb
git commit -m "Add Jev and Laya model use cases"
git branch -M main
git remote add origin https://github.com/<OWNER>/<REPOSITORY>.git
git push -u origin main
```

If this directory is already connected to a GitHub remote, check `git remote -v` and use the existing remote instead of adding another one.
