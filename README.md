# Lab 03: Benchmark-Aligned Email Classification & LLM Draft Generation
## 1. Overview
This repository contains an end-to-end, two-stage predictive analytics system for organizational shared inbox email management:
1. **Classifier Module:** Evaluates classical sparse-text models (Naive Bayes, Logistic Regression, LinearSVC) and modern representation extensions (Sentence-Transformers, Keras BiLSTM) across multiple datasets to categorize incoming email intent.
2. **LLM API Auto-Drafting Module:** Uses sanitized email content, predicted class labels, and uncertainty review signals to automatically generate context-conditioned response drafts for human review.
> **Mandatory Boundary:** This system **generates local draft text only**. It does not send emails, connect to live mailboxes, or execute autonomous actions. Every draft requires manual human review and approval.

## 2. Environment & Dependency Setup

### System Requirements
* **Python Version:** 3.10 or higher
* **OS Compatibility:** Linux, macOS, or Windows WSL2

### Required Packages & Libraries
Install all necessary packages via `pip`:

```bash
pip install -U pandas numpy scipy scikit-learn matplotlib seaborn joblib openai sentence-transformers tensorflow

#To call the LLM API for automatic draft generation, configure your API key securely using environment variables or Colab Secrets. Never hardcode keys inside code files or commit .env files.
export OPENAI_API_KEY="your-actual-api-key-here"
export OPENAI_MODEL="gpt-5-mini"
#windows command prompt
set OPENAI_API_KEY=your-actual-api-key-here
set OPENAI_MODEL=gpt-5-mini
