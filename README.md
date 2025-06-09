This repository contains the code and (partial) data used in the master's thesis project completed at Tilburg University for the MSc in Data Science & Society.

📘 Project Overview
This project explores how well current AI-generated text detectors generalize under realistic distribution shifts. Specifically, it evaluates model performance across three key dimensions:

Text granularity: Sentence-level, full-text-level, and mixed training/testing structures

Content domain: Academic writing, news, social media, emails, government documents, and more

LLM sources: Including GPT-3.5, GPT-4.5, GPT-4o, LLaMA, ChatGLM, and DeepSeek R1

The study is multilingual, with separate modeling strategies for English and Chinese. A new benchmark dataset, AGT-2025, was created to test generalization on outputs from state-of-the-art LLMs released in 2025.

⚙️ Methods
Four transformer-based classifiers were fine-tuned and tested:

roberta-base (English)

chinese-roberta-wwm-ext (Chinese)

DistilBERT (English, lightweight baseline)

MacBERT (Chinese, language-specific)

XLM-R (Multilingual baseline)

Approaches used:

Fine-tuning on balanced human vs. machine-generated datasets (HC3, M4GT)

Cross-granularity training: full-text, sentence, and mixed formats

Cross-domain evaluation: tested on COLING-2025

Cross-LLM robustness: tested on AGT-2025 (GPT-4.5, DeepSeek R1)

SHAP analysis for feature importance and interpretability

🧪 Evaluation
Metrics: F1-score, precision, recall, and accuracy

Highlights:

RoBERTa achieves 0.998 F1 on unseen GPT-4.5 text

All detectors fail to reliably detect DeepSeek R1 (F1 < 0.30 in Chinese)

Mixed-granularity training improves robustness across domains and LLMs

XLM-R shows better robustness in Chinese cross-LLM evaluation

Confusion matrices, domain-level results, and full evaluation details are provided in the thesis appendices.

📁 Repository Structure
bash
复制
编辑
├── src/                    # Code for data preprocessing, training, evaluation
│   ├── models/             # Model loading and fine-tuning scripts
│   ├── data/               # Custom dataset handling (AGT-2025, COLING, etc.)
│   ├── analysis/           # Scripts for evaluation and visualization
│   └── utils/              # Helper functions
├── notebooks/              # Jupyter notebooks for exploratory analysis
├── results/                # Model outputs and evaluation logs
├── figures/                # Visualizations and diagrams used in the thesis
├── appendix/               # Supplementary tables (precision, recall, CM, etc.)
├── thesis.pdf              # Full master's thesis document
└── README.md               # Project overview
📦 Datasets
Train: HC3, M4GT (English & Chinese)

Test: COLING-2025 (OOD benchmark), AGT-2025 (custom test set for GPT-4.5 & DeepSeek R1)

All datasets are anonymized and used solely for academic research.

🖥️ Environment
Python 3.10

PyTorch 2.0+

Huggingface Transformers

Google Colab Pro (A100 GPU)

🔗 Related Resources
Thesis PDF: Detecting Machine-Generated Text Across Granularity, Domains, and LLMs

AGT-2025 Dataset: To be released (TBD)

COLING-2025 Task Website: https://github.com/mbzuai-nlp/COLING-2025-Workshop-on-MGT-Detection-Task1

