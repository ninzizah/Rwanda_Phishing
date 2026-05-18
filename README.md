# Lightweight vs. Deep Learning Models for Phishing Detection in Resource-Constrained African Network Environments: A Comparative Study

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

> **Note:** This repository contains the official code for our research paper evaluating BERT and XGBoost models for phishing detection in Sub-Saharan African contexts.

## 📝 Abstract

While deep learning models such as BERT have shown promising results in detecting phishing URLs, their computational needs prevent their use in Sub-Saharan African countries with limited computing resources. This repository presents the code for a thorough comparative study of **BERT** versus **XGBoost**, an efficient gradient boosting algorithm. 

We train the two machine learning models on a highly balanced dataset utilizing a domain-level data partitioning technique to avoid data leakage. Interestingly, we also investigate a new form of 'shortcut learning' problem wherein ML models artificially inflate accuracy scores by learning the difference between African Top-Level Domains (TLDs like `.rw`, `.ke`, `.za`) and global TLDs (`.com`, `.net`).

## 🗂️ Dataset Collection

The dataset is automatically collected and processed via our Jupyter Notebook to ensure full reproducibility. 
- **Legitimate URLs:** 5,266 real African legitimate domains scraped from the Tranco Top 1 Million dataset.
- **Malicious URLs:** Randomly sampled from a pool of 789,352 global phishing URLs from PhishTank and OpenPhish to create a perfectly balanced dataset.
- **Data Splitting:** `GroupShuffleSplit` is used at the root-domain level to ensure robust validation.

## 🚀 Usage

The entire workflow—including dataset downloading, balancing, domain extraction, and model training—is self-contained within our main Jupyter Notebook.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ninzizah/Rwanda_Phishing.git
   cd Rwanda_Phishing
   ```

2. **Run the Notebook:**
   Open and execute `african_phishing_detection_v2.ipynb` to automatically reproduce all experiments, data collection, and results.

## 📈 Results Summary

The comparison between BERT and XGBoost reveals a critical trade-off between slight accuracy gains and massive computational efficiency.

| Metric | XGBoost | BERT | Advantage |
|--------|---------|------|-----------|
| **Test Accuracy** | 99.30% | 99.91% | BERT (+0.61%) |
| **Precision (Phishing)** | 99% | 100% | BERT (+1%) |
| **Recall (Phishing)** | 100% | 100% | Tie |
| **Training Time** | ~1 min | 148 min | XGBoost (148× faster) |
| **Inference (1000 URLs)**| 0.008 sec | 394 sec | XGBoost (50,000× faster) |
| **Hardware Required** | CPU only | GPU preferred | XGBoost |
| **Est. Monthly Hosting** | $5 VPS | $500+ GPU | XGBoost (100× cheaper) |

*Our findings indicate that while BERT achieves marginally higher accuracy, XGBoost offers a significantly more viable path for cost-effective, real-world deployment in African network infrastructures.*

## 🤝 Citation

If you use this code or dataset methodology in your research, please cite our paper:

```bibtex
@article{shema2026lightweight,
  title={Lightweight vs. Deep Learning Models for Phishing Detection in Resource-Constrained African Network Environments: A Comparative Study},
  author={Shema, Honore Ninziza},
  year={2026}
}
```
