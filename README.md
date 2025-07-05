# Customer Churn Model 📉🛫

A lightweight, end‑to‑end demonstration of predicting customer‑churn risk with classical machine‑learning techniques.  
The current notebook trains a **Random Forest** classifier on the popular *Telco Customer Churn* data set and reports accuracy and a full classification report.:contentReference[oaicite:0]{index=0}

---

## Table of Contents
1. [Project Motivation](#project-motivation)  
2. [Dataset](#dataset)  
3. [Approach & Notebook Walk‑through](#approach--notebook-walk%E2%80%91through)  
4. [Quick Start](#quick-start)  
5. [Project Structure](#project-structure)  
6. [Results](#results)    

---

## Project Motivation

Churn directly affects a company’s bottom line: retaining a customer is usually cheaper than acquiring a new one.  
By identifying *who* is at risk *before* they leave, businesses can target retention campaigns more efficiently.  

This repository is meant to be:
- **Educational** – a clear, minimal example of the ML‑for‑churn workflow.  
- **Extendable** – drop in new features, models or MLOps tooling without major refactor.  
- **Reproducible** – a single Jupyter Notebook drives the whole pipeline.

---

## Dataset

| Name | Records | Features | Source |
|------|---------|----------|--------|
| Telco Customer Churn | 17 000 + | Demographic, engagement & financial metrics | Automatically downloaded via the `skillsnetwork` helper (IBM Skills Network).:contentReference[oaicite:1]{index=1} |

*Target*: **`CHURNRISK`** (categorical: *Low*, *Medium*, *High*).

---

## Approach & Notebook Walk‑through

| Step | Description |
|------|-------------|
| **1. Exploration** | Quick pandas profiling, missing‑value audit, churn distribution. |
| **2. Pre‑processing** | *Numerical*: impute → standard‑scale.  *Categorical*: impute → One‑Hot encode. |
| **3. Train/Test Split** | 80 / 20 with stratification to preserve class balance. |
| **4. Modelling** | `RandomForestClassifier(n_estimators = 100, random_state = 42)`. |
| **5. Evaluation** | Accuracy plus precision/recall/F1 per class; feature‑importance bar chart. |
| **6. Persistence** | Save the trained RF model with `joblib` (placeholder – uncomment in notebook). |
| **7. Prediction Demo** | Simulate scoring a single customer record. |

> **Why Random Forest?**  
> Good baseline, handles mixed data types out‑of‑the‑box, interpretable via feature importance.

---

## Quick Start

 **Clone** the repo  
```
   git clone https://github.com/ShivamMitra/Customer-churn-model.git
   cd Customer-churn-model
```


Project Structure
```
Customer-churn-model/
│
├── Churn Probability (Random Forest ) Model.ipynb   ← main notebook
├── requirements.txt                                 ← dependency pin‑list (add yours)
└── README.md                                        ← you are here
```


Results
```
Metric	Value*
Overall Accuracy	~ 88 % (demo run, will vary)
Macro F1‑Score	~ 0.86
Top 5 Features	TOTALDOLLARVALUETRADED, ESTINCOME, TOTALUNITSTRADED, DAYSSINCELASTLOGIN, NETREALIZEDGAINS_YTD
```
* See the final notebook cell for the exact run in your environment.
   
