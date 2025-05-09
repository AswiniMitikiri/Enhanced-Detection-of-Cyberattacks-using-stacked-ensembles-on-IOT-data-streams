# 🔐 Enhanced Detection of Cyberattacks using Stacked Ensembles on IoT Data Streams

This project presents a comprehensive framework for detecting cyberattacks in IoT data using ensemble learning techniques. It integrates advanced preprocessing, feature engineering, optimization, and stacking strategies to improve accuracy in both binary and multi-class classifications.

---

## 📂 Dataset

We utilized two publicly available datasets:

- **ACI IoT Dataset**
- **CICIDS IoT Dataset**

Download ACI dataset here: [CIC-BCCC-NRC-ACI-IOT-2023](http://cicresearch.ca/IOTDataset/CIC-BCCC-NRC-TabularIoTAttacks-2024/Dataset/)

---

## ⚙️ Pipeline Overview
![image](https://github.com/user-attachments/assets/cc629da1-91a1-4fac-a0db-f03f03ee5b1a)


### Preprocessing

- Standard Scaling  
- SMOTE (Synthetic Minority Over-sampling Technique)  
- Missing/Infinite Value Imputation  

### Filtering Techniques

| Technique                   | Best Applied To        |
|----------------------------|------------------------|
| Correlation Filtering      | ACI, CICIDS            |
| Variance Threshold         | CICIDS Multi           |
| Mutual Information         | All                    |

### Feature Selection Techniques

| Technique                    | Best Applied To          |
|-----------------------------|--------------------------|
| K-Best Feature Selection     | ACI                      |
| Mutual Information           | CICIDS Binary            |
| Recursive Feature Elimination | CICIDS Multi           |

---

## 🤖 Models Used

- Random Forest
- Extra Trees
- Decision Tree
- XGBoost
- LightGBM
- CatBoost

Optimized using:
- Grid Search
- Particle Swarm Optimization (PSO)

The best models were selected based on a **penalty score** (combining accuracy and runtime), followed by **stacked ensembling** of the top 3 models.

---

## 📊 Results

### 🧪 ACI Dataset – Binary Classification

| Model         | Grid Search Accuracy | PSO Accuracy |
|---------------|----------------------|--------------|
| Extra Tree    | 0.9748               | 0.9735       |
| Random Forest | 0.9988               | 0.9707       |
| Decision Tree | 0.9921               | 0.9643       |
| XGBoost       | 0.9934               | 0.9770       |
| LightGBM      | 0.9948               | 0.9754       |
| CatBoost      | 0.9974               | 0.9683       |
| **Stacking**  | —                    | **0.9749**   |

---

### 🧪 ACI Dataset – Multi-Class Classification

| Model         | Grid Search Accuracy | PSO Accuracy |
|---------------|----------------------|--------------|
| Extra Tree    | 0.9876               | 0.9879       |
| Random Forest | 0.9865               | 0.9860       |
| Decision Tree | 0.9406               | 0.9364       |
| XGBoost       | 0.9899               | 0.9895       |
| LightGBM      | 0.9912               | 0.9913       |
| CatBoost      | 0.9832               | 0.9766       |
| **Stacking**  | —                    | **0.9912**   |

---

### 🧪 CICIDS Dataset – Binary Classification

| Model         | Grid Search Accuracy | PSO Accuracy |
|---------------|----------------------|--------------|
| Extra Tree    | 0.9964               | 0.9963       |
| Random Forest | 0.9991               | 0.9991       |
| Decision Tree | 0.9981               | 0.9982       |
| XGBoost       | 0.9991               | 0.9991       |
| LightGBM      | 0.9991               | 0.9992       |
| CatBoost      | 0.9989               | 0.9989       |
| **Stacking**  | —                    | **0.9991**   |

---

### 🧪 CICIDS Dataset – Multi-Class Classification

| Model         | Grid Search Accuracy | PSO Accuracy |
|---------------|----------------------|--------------|
| Extra Tree    | 0.9956               | 0.9948       |
| Random Forest | 0.9985               | 0.9985       |
| Decision Tree | 0.9960               | 0.9960       |
| XGBoost       | 0.9987               | 0.9987       |
| LightGBM      | 0.9992               | 0.9993       |
| CatBoost      | 0.9986               | 0.9982       |
| **Stacking**  | —                    | **0.9992**   |

---

## 🏆 Top 3 Models by Dataset

| Dataset           | Top 1        | Top 2        | Top 3        |
|-------------------|--------------|--------------|--------------|
| ACI - Binary      | RandomForest | ExtraTrees   | CatBoost     |
| ACI - Multi       | XGBoost      | ExtraTrees   | LightGBM     |
| CICIDS - Binary   | RandomForest | LightGBM     | CatBoost     |
| CICIDS - Multi    | LightGBM     | CatBoost     | XGBoost      |

---

## 🧰 Technologies & Libraries

- Python (Pandas, NumPy, Scikit-learn)
- SMOTE (imbalanced-learn)
- XGBoost, LightGBM, CatBoost
- Matplotlib, Seaborn
- PSO (custom / PySwarm-based optimization)

---

## 🚀 Future Enhancements

- Real-time stream-based attack detection
- Edge deployment on resource-constrained IoT devices
- AutoML integration for model tuning

---

## 👤 Author

- Sanket Mishra
- Aswini Mitikiri
- Aleena Maria
- Vismaya K Santhosh

---

## 📄 License

This project is licensed under the MIT License.
