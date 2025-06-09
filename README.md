# Detecting Machine-Generated Text Across Granularity, Domains, and LLMs

This repository contains the code and (partial) data used in the master's thesis project completed at Tilburg University for the MSc in Data Science & Society.

## 📘 Project Overview

The project investigates the generalization capabilities of machine-generated text detectors under realistic distribution shifts. Specifically, it evaluates how detection models perform when:

- The **text granularity** varies (e.g., sentence, paragraph, document),
- The **content domain** shifts (e.g., academic, social media, fiction),
- The **source LLM** differs (e.g., ChatGPT, GPT-4, DeepSeek R1).

A multilingual approach was adopted, covering both English and Chinese datasets.

## ⚙️ Methods

Four transformer-based classifiers were fine-tuned and tested:

- RoBERTa (English)
- XLM-R (multilingual)
- DistilBERT (English, efficient)
- MacBERT (Chinese)

Key techniques:

- Fine-tuning on human vs. LLM-generated text
- Cross-domain evaluation
- SHAP analysis for model interpretability
- Custom benchmark dataset: **AGT-2025**

## 🧪 Evaluation

- Models were evaluated using precision, recall, F1, and accuracy.
- Special focus on generalization: tested on unseen domains, granularities, and newer LLMs.
- Confusion matrices and detailed analysis provided in the appendices.

## 📁 Repository Structure

