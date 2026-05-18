# Phishing URL Detection in a Sub-Saharan African Context

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

> **Note:** This repository contains the official code and dataset for our research paper evaluating BERT and XGBoost models for phishing detection.

## 📝 Abstract

This repository provides the implementation and dataset for our research on phishing URL detection, specifically tailored to address methodological flaws in existing datasets and focusing on a Sub-Saharan African context. We compare the performance, inference speed, and deployment cost of a high-performance **BERT** model against a lightweight **XGBoost** model. 

To prevent data leakage during training, we utilize `GroupShuffleSplit` for domain-level dataset splitting. 

## 🗂️ Dataset

The dataset used in this study includes a custom collection of legitimate URLs featuring regional Top-Level Domains (TLDs) relevant to the Sub-Saharan African context (e.g., `.rw`, `.ke`, `.za`, etc.), paired with known phishing URLs. 

- **Data Leakage Prevention:** The dataset was split at the *domain level* rather than the URL level to ensure the models learn generalizable features rather than memorizing specific domains.

## ⚙️ Repository Structure

```text
Rwanda_Phishing/
├── data/
│   ├── raw/                 # Original, unprocessed datasets
│   └── processed/           # Cleaned data after domain-level splitting
├── notebooks/               # Jupyter notebooks for EDA and model prototyping
├── src/
│   ├── data_preprocessing.py # Script for cleaning and GroupShuffleSplit
│   ├── train_xgboost.py      # Training and evaluating the XGBoost model
│   ├── train_bert.py         # Training and evaluating the BERT model
│   └── inference.py          # Script for testing deployment speed/cost
├── requirements.txt         # Python dependencies
└── README.md
```
*(Adjust the file names above to match your actual files!)*

## 🚀 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ninzizah/Rwanda_Phishing.git
   cd Rwanda_Phishing
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## 📊 Usage

### 1. Data Preprocessing
Run the preprocessing script to prepare the dataset and perform the domain-level split:
```bash
python src/data_preprocessing.py
```

### 2. Train the XGBoost Model
```bash
python src/train_xgboost.py
```

### 3. Train the BERT Model
```bash
python src/train_bert.py
```

## 📈 Results Summary

| Model | Accuracy | Precision | Recall | F1-Score | Inference Speed (ms/URL) |
|-------|----------|-----------|--------|----------|--------------------------|
| **XGBoost** | XX.X% | XX.X% | XX.X% | XX.X% | Fast |
| **BERT**    | XX.X% | XX.X% | XX.X% | XX.X% | Slower |

*Our findings indicate that while BERT achieves marginally higher accuracy, XGBoost offers a significantly more viable path for cost-effective, real-world deployment.*

## 🤝 Citation

If you use this code or dataset in your research, please cite our paper:

```bibtex
@article{yourlastname2026phishing,
  title={Your Paper Title Here},
  author={Your Name and Co-authors},
  journal={Name of Journal},
  year={2026}
}
```
