# ML-Network-Intrusion-Detection
Machine learning-based network intrusion detection system that trains and compares Random Forest, Decision Tree, Logistic Regression, and SVM models on the CIC-IDS2017 dataset to classify network traffic as normal or attack with 99.88% accuracy.
# ML-Based Network Intrusion Detection System

A machine learning-based network intrusion detection system (IDS) that trains and compares four different ML models on the CIC-IDS2017 dataset to classify network traffic as either normal or attack.

## Project Overview

Network attacks are becoming more complex and frequent every year. Traditional rule-based detection systems cannot keep up with modern attacks because they rely on fixed rules that become outdated quickly. This project addresses this problem by building an ML-based IDS that learns attack patterns automatically from real network traffic data.

## Dataset

- **Name:** CIC-IDS2017
- **Source:** Canadian Institute for Cybersecurity
- **Files Used:** All 7 CSV files combined
- **Total Records:** 2,604,998 rows, 79 columns
- **After Cleaning:** 2,602,165 rows
- **Normal Traffic (class 0):** 2,173,634 records
- **Attack Traffic (class 1):** 428,531 records
- **Train/Test Split:** 80% training / 20% testing

### Attack Types Covered
DoS Hulk, PortScan, DoS GoldenEye, FTP-Patator, SSH-Patator, DoS Slowloris, DoS Slowhttptest, Botnet, Web Attack Brute Force, Web Attack XSS, Infiltration, Web Attack SQL Injection, Heartbleed

## Models Trained

| Model | Description |
|---|---|
| Random Forest | Ensemble of decision trees — strong on large datasets |
| Decision Tree | Tree-based model — simple and interpretable |
| Logistic Regression | Linear model — fast but limited on complex patterns |
| SVM | Finds best boundary — trained on sample due to scalability |

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Random Forest | 99.88% | 1.00 | 1.00 | 1.00 |
| Decision Tree | 99.87% | 1.00 | 1.00 | 1.00 |
| Logistic Regression | 89.58% | 0.79 | 0.51 | 0.62 |
| SVM | 88.00% | 0.90 | 0.32 | 0.48 |

**Random Forest is the best model** — 99.88% accuracy with perfect recall on 2.6 million records.

## Technologies Used

- Python
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Anaconda

## Project Structure
