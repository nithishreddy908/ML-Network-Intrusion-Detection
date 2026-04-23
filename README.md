# ML-Based Network Intrusion Detection System

A machine learning based network intrusion detection system that trains and compares four ML models on the CIC-IDS2017 dataset to classify network traffic as either normal or attack. Random Forest achieved the best result with 99.88% accuracy and perfect recall on over 2.6 million records.

---

## Project Overview

Network attacks are growing every year and traditional rule based systems cannot keep up because they use fixed rules that become outdated quickly. This project solves this problem by building an ML based IDS that learns attack patterns automatically from real network traffic data. Four machine learning models were trained and compared to find out which one works best for detecting network attacks.

---

## Dataset

| Detail | Value |
|---|---|
| Name | CIC-IDS2017 |
| Source | Canadian Institute for Cybersecurity |
| Files Used | All 7 CSV files combined |
| Total Records (before cleaning) | 2,604,998 rows, 79 columns |
| Total Records (after cleaning) | 2,602,165 rows |
| Normal Traffic (class 0) | 2,173,634 records |
| Attack Traffic (class 1) | 428,531 records |
| Training Set | 2,081,732 rows (80%) |
| Testing Set | 520,433 rows (20%) |

### How to Download the Dataset

1. Go to this link: https://www.unb.ca/cic/datasets/ids-2017.html
2. Scroll down and click **Download**
3. Download all 7 CSV files
4. Place all CSV files in the same folder as the notebook

### Attack Types Covered

DoS Hulk, PortScan, DoS GoldenEye, FTP-Patator, SSH-Patator, DoS Slowloris, DoS Slowhttptest, Botnet, Web Attack Brute Force, Web Attack XSS, Infiltration, Web Attack SQL Injection, Heartbleed

---

## Models Trained

| Model | Description |
|---|---|
| Random Forest | Builds many decision trees and combines their votes — very strong on large datasets and handles class imbalance well |
| Decision Tree | Splits data step by step based on most useful features — simple and easy to understand |
| Logistic Regression | Linear model that finds best boundary between classes — fast but struggles on complex data |
| SVM | Finds the best separating boundary — trained on only 3,000 records due to scalability issues on large datasets |

---

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Random Forest | 99.88% | 1.00 | 1.00 | 1.00 |
| Decision Tree | 99.87% | 1.00 | 1.00 | 1.00 |
| Logistic Regression | 89.58% | 0.79 | 0.51 | 0.62 |
| SVM | 88.00% | 0.90 | 0.32 | 0.48 |

**Random Forest is the best model** with 99.88% accuracy and perfect recall on 2.6 million records.

**Recall is the most important metric** in intrusion detection because missing a real attack is far more dangerous than a false alarm.

---

## Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Main programming language |
| Scikit-learn | Building and evaluating all ML models |
| Pandas | Loading and cleaning the dataset |
| NumPy | Numerical operations |
| Matplotlib | Plotting comparison charts |
| Jupyter Notebook | Writing and running the code |
| Anaconda | Python environment management |
| VS Code | Development environment |

---

## Project Structure
```
ML-Network-Intrusion-Detection/
│
├── intrusion_detection.ipynb     # Main notebook with all code
├── all_models_comparison.png     # Bar chart comparing all 4 models
├── comparison.png                # Model accuracy comparison chart
├── final_comparison.png          # Final results chart
├── .gitignore                    # Ignores large CSV dataset files
└── README.md                     # Project documentation
```
---

## How to Run

### Step 1 — Install Requirements

Make sure Python 3 and Anaconda are installed on your computer. Then open your terminal or Anaconda prompt and run this command:
```
pip install scikit-learn pandas numpy matplotlib jupyter
```
Or if you are using Anaconda:
```
conda install scikit-learn pandas numpy matplotlib jupyter
```
### Step 2 — Download the Dataset

Download the CIC-IDS2017 dataset from:
https://www.unb.ca/cic/datasets/ids-2017.html

Place all 7 CSV files in the same folder as the notebook file.

### Step 3 — Open the Notebook

Open VS Code or Jupyter Notebook and open this file:
```
intrusion_detection.ipynb
```
### Step 4 — Run All Cells

Run all cells from top to bottom in order. The notebook will automatically do the following steps:

1. Load and combine all 7 CSV files into one dataset
2. Remove missing and infinite values
3. Encode labels — BENIGN = 0, all attacks = 1
4. Split data into 80% training and 20% testing
5. Train all 4 machine learning models
6. Print classification reports for each model
7. Show a comparison table and bar chart for all models

> **Note:** Running the full notebook may take some time because the dataset has over 2.6 million records.

---

## Key Findings

- Random Forest and Decision Tree both got near perfect scores on all metrics on the full 2.6 million record dataset
- Logistic Regression missed 49% of real attacks — not suitable for real world intrusion detection
- SVM missed 68% of real attacks and could not be trained on the full dataset due to scalability issues
- Class imbalance in the dataset directly affected the performance of Logistic Regression and SVM
- Recall for the attack class is the most important metric in intrusion detection — not overall accuracy

---

## Limitations

- Class imbalance — 2.17M normal records vs only 428K attack records affected Logistic Regression and SVM
- SVM was trained on only 3,000 records which makes the comparison less fair with other models
- SMOTE was not applied to fix the class imbalance problem
- Deep learning models were not tested for comparison

---

## Future Work

- Apply SMOTE to balance the dataset before training to improve recall scores for weaker models
- Test SVM on the full dataset using faster kernel methods
- Explore deep learning models like RNN or Autoencoder
- Test the system on live network traffic for real time detection

---

## References

- Sharafaldin et al. (2018) — CIC-IDS2017 dataset
- Breiman (2001) — Random Forest algorithm
- Cortes and Vapnik (1995) — Support Vector Machines
- Quinlan (1993) — Decision Tree C4.5
- Leevy et al. (2018) — Class imbalance in big data
- Chawla et al. (2002) — SMOTE technique

---

## Course

**Information Assurance — Final Project**
University of North Florida
School of Computing
