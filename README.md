# FinSense — Financial News Sentiment Analysis

An experimental financial-news sentiment analysis project. This notebook covers dataset preprocessing, fine-tuning FinBERT and BERT, a TF-IDF + Logistic Regression baseline, model evaluation, attention visualization, combined-dataset experiments, and a financial-news analysis pipeline.

## What is included
- `FinSense.ipynb` — training, evaluation, and application code, with saved results from an earlier run
- `requirements.txt` — Python dependencies
- `.gitignore` — excludes generated data, checkpoints, and secrets

## Running
1. Use Python 3.10+ or Google Colab (GPU recommended for model fine-tuning).
2. Install packages: `pip install -r requirements.txt`. In Colab, upload the requirements file or install the same dependencies there.
3. Open `FinSense.ipynb` and run the cells **in order**. Dataset downloads require internet access.
4. The notebook creates `FinSense/data`, `FinSense/models`, `FinSense/logs`, and `FinSense/figures` **under the current Python working directory**. In Colab this is typically `/content/FinSense` and may disappear when the session ends. For persistence, adjust `PROJECT_DIR` in the setup cell to a mounted Drive folder.

Model training is compute-intensive. The saved notebook outputs are from the original run; this cleaned notebook has not been rerun end-to-end. Third-party news feeds and article extraction may change or fail independently of model code.

## Data and methods
The notebook downloads a FinancialPhraseBank mirror and Twitter financial sentiment data using Hugging Face Datasets. It fine-tunes FinBERT and BERT, compares them with a TF-IDF / Logistic Regression baseline, and reports accuracy, F1, and confusion matrices. FinSense also uses financial news and stock data to provide experimental sentiment summaries. **Sentiment is not a reliable prediction of stock price movements or investment advice.**

## Publishing notes
Generated model weights and downloaded datasets are not included. Do not commit API keys, access tokens, or private data. The optional Hugging Face model-upload step was removed.
