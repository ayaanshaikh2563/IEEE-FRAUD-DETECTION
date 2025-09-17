# 💳 IEEE-CIS Fraud Detection: Multilayered ML Model

## Project Overview
Built a high-performance credit card fraud detection model using the complex, real-world **IEEE-CIS Multilayered Dataset** (590k+ transactions).

The goal was to achieve both high overall accuracy and a high detection rate (Recall) of rare fraudulent transactions.

---

## 🛠️ Methodology & Technical Stack

1.  **Data Engineering:** Merged separate Transaction and Identity data files on the 'TransactionID' to successfully integrate the **multilayered data structure**.
2.  **Preprocessing:** Handled the over 400 mixed numerical and categorical features. Used **Label Encoding** for efficiency on high-cardinality categorical variables.
3.  **Training:** Utilized **GPU-accelerated XGBoost** (`tree_method='hist', device='cuda'`) for rapid training on high-volume data.
4.  **Imbalance Mitigation:** Applied **cost-sensitive learning** via the `scale_pos_weight` parameter to successfully boost the detection rate (Recall) against the highly imbalanced dataset.

---

## 📈 Model Performance (Final Metrics)

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| Overall Accuracy | **0.9742** | High overall classification performance. |
| Recall (Fraud) | **0.8043** | **Successfully detected 80.4% of all actual fraud cases.** |
| Precision (Fraud) | **0.60** | The model is correct 60% of the time when it flags a transaction. |
| **Conclusion** | The model prioritizes Recall over perfect Precision, which is the preferred strategy in fraud detection to minimize financial losses (False Negatives). |

---

## 💾 Files in this Repository

* `fraud_detection_model.ipynb`: The complete Jupyter Notebook containing all data processing steps, GPU-accelerated training, and final evaluation output.
* `.gitignore`: Ensures large files (`.csv`, `.zip`) and the virtual environment (`CC-fraud/`) are excluded.
* `requirements.txt`: Lists all Python dependencies needed to run the notebook.
