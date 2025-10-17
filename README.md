# Fetal Health Classification Using Machine Learning and Deep Learning
## A Comprehensive Comparative Analysis for Maternal Health in Sub-Saharan Africa

**Author:** Victoria Fakunle  
**Course:** Introduction to Machine Learning - Summative Project  
**Date:** October 2025

---

##  Project Overview

This project addresses a critical maternal health challenge in Sub-Saharan Africa through automated fetal health classification using Cardiotocography (CTG) data. The work provides a **rigorous, systematic comparative analysis** of traditional machine learning and deep learning approaches, conducting **comprehensive experiments** to identify optimal algorithmic strategies for resource-limited healthcare settings.

### Mission Alignment
- **66% of global maternal deaths** occur in Sub-Saharan Africa (only 16% of the world population)
- **Shortage of specialist obstetricians** limits access to quality prenatal monitoring
- **Automated diagnostic tools** can empower non-specialist healthcare workers to save lives


##  Problem Statement

**Challenge:** Manual interpretation of Cardiotocography (CTG) results is:
- **Time-consuming** for clinical staff
- **Subjective** with high inter-observer variability
- **Inaccessible** in resource-limited settings lacking specialist obstetricians

**Solution:** Develop automated classification systems that:
1. Assist healthcare workers in interpreting CTG results accurately
2. Provide reliable predictions without requiring specialist expertise
3. Operate efficiently on modest hardware (suitable for low-resource environments)
4. Enable early detection of fetal distress to prevent stillbirths and maternal deaths

---

##  Dataset

**Source:** [UCI Machine Learning Repository - Fetal Health Classification](https://archive.ics.uci.edu/dataset/193/cardiotocography)

### Dataset Characteristics
- **Size:** 2,126 Cardiotocogram (CTG) examinations
- **Features:** 21 physiological indicators derived from CTG signals
- **Target Classes:** 
  - **Normal:** 1,655 cases (77.8%)
  - **Suspect:** 295 cases (13.9%)
  - **Pathological:** 176 cases (8.3%)
- **Data Quality:** 0% missing values, clean dataset
- **Class Imbalance:** Severe imbalance requiring SMOTE intervention

### Feature Groups
- **Fetal Heart Rate Patterns:** baseline value, accelerations, decelerations
- **Uterine Contractions:** frequency and intensity
- **Fetal Movement:** activity indicators
- **Statistical Features:** histogram metrics, variability measures


---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or Google Colab
- Git

### Step 1: Clone Repository
```bash
git clone https://github.com/yourusername/fetal-health-classification.git
cd fetal-health-classification
```

### Step 2: Create Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook
```bash
jupyter notebook fetal_health_classification.ipynb
```

### Required Libraries
```txt
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
imbalanced-learn>=0.9.0
xgboost>=1.5.0
tensorflow>=2.8.0
```


### Evaluation Strategy
- **Primary Metric:** F1-Score (weighted) - critical for imbalanced medical data
- **Secondary Metrics:** Accuracy, Precision, Recall, AUC-ROC
- **Cross-Validation:** 5-fold stratified CV for traditional ML
- **Data Splits:** 70% training, 15% validation, 15% test (stratified)
- **Reproducibility:** Random seed control (RANDOM_SEED=42) across all experiments

---
##  Results Summary

### Top 5 Models (Ranked by F1-Score)
| Rank | Model | Type | F1-Score | Accuracy | AUC |
|------|-------|------|----------|----------|-----|
|  1 | **RF + SMOTE** | Traditional ML | **0.9335** | 0.9342 | 0.9826 |
|  2 | XGBoost (Tuned) | Traditional ML | 0.9267 | 0.9279 | 0.9786 |
|  3 | Random Forest (Tuned) | Traditional ML | 0.9192 | 0.9216 | 0.9796 |
| 4 | Ensemble (RF+XGB+SVM) | Traditional ML | 0.9135 | 0.9154 | 0.9813 |
| 5 | Final Optimized DNN | Deep Learning | 0.8970 | 0.8934 | 0.9740 |

### Statistical Comparison
| Approach | Mean F1 | Max F1 | Min F1 | Std F1 |
|----------|---------|--------|--------|--------|
| **Traditional ML** (6 models) | **0.9062** | 0.9335 | 0.8602 | 0.0282 |
| **Deep Learning** (11 models) | 0.8779 | 0.8970 | 0.7945 | 0.0286 |

---

###  Class-Specific Performance Analysis
| Class | RF+SMOTE Precision | RF+SMOTE Recall | RF+SMOTE F1 |
|-------|-------------------|-----------------|-------------|
| **Normal** (78%) | 0.9451 | 0.9634 | 0.9541 |
| **Suspect** (14%) | 0.9205 | 0.8945 | 0.9073 |
| **Pathological** (8%) | 0.9167 | 0.9091 | 0.9129 |

**Clinical Impact:** Excellent minority class performance (Pathological: 91.29% F1) ensures critical cases are detected.

---



##  Demo Video

 **[Watch 5-Minute Project Demo](https://drive.google.com/file/d/1ESR8q9JvxXz8RZJNAgVf_7FkZzqSCu2N/view?usp=sharing)**



##  Documentation

### Written Report
 **[Complete Written Report (PDF)](https://docs.google.com/document/d/1fim8OOmesMnfXYR8pBFIfkBofoXRmVQW0Kk1s9gYVX4/edit?usp=sharing)** -


---

##  Acknowledgments

- **UCI Machine Learning Repository** for providing the Fetal Health Classification dataset
- **World Health Organisation** for maternal health statistics and stillbirth data
- **TensorFlow and Scikit-learn communities** for excellent documentation and support
- **Introduction to Machine Learning instructors** for guidance throughout the project

---

