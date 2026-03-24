# Predictive Stress Detection in Human-Robot Collaboration
**Kirk-Mends Attafuah | MSc Statistics, Wake Forest University**

### Project Overview
This research addresses the **"Cognitive Safety"** gap in high-stakes operational environments. While current ISO standards focus on physical safety, this project develops a machine learning framework to monitor operator well-being. Using multimodal physiological signals (EDA, ECG, and Heart Rate), I built a predictive pipeline to identify stress states, enabling adaptive safety interventions in complex human-robot systems.

### Technical Challenges & Data Engineering
The primary challenge was managing high-velocity, asynchronous sensor data. I architected a custom ETL workflow in R to:
* **Timestamp Reconstruction:** Implemented conditional parsing to align heterogeneous data formats across multiple wearable sensors.
* **Multimodal Integration:** Synchronized EDA (Electrodermal Activity), HR (Heart Rate), and ECG (Electrocardiogram) signals into a unified feature set.
* **Baseline Normalization:** Applied **Baseline Subtraction** to normalize individual physiological differences, ensuring model generalizability across 21 different test subjects.
* **Feature Engineering:** Extracted 50+ statistical and physiological features, including **RMSSD** for heart rate variability and **SCR (Skin Conductance Response)** metrics.

### Model Benchmarking & Performance
I evaluated five classification algorithms to find the optimal balance between predictive power and operational latency. The results confirmed that non-linear ensemble methods are superior for biometric telemetry:

| Model | ROC-AUC | Note |
| :--- | :--- | :--- |
| **Random Forest** | **0.971** | **Selected for production-grade robustness** |
| Gradient Boosting (GBM) | 0.914 | Strong performance, slightly higher latency |
| SVM | 0.876 | Good discrimination, less robust to noise |
| Logistic Regression | 0.709 | Insufficient for non-linear stress signals |
| GLMNET | 0.706 | Limited by linear constraints |

### Key Results & Industry Impact
* **High Precision:** The Random Forest model achieved a **0.971 AUC**, demonstrating excellent discrimination between stress and non-stress states.
* **Operational Insight:** Identified Heart Rate Variability (HRV) and Skin Conductance as the most significant "signals" for real-time stress monitoring.
* **Scalability:** The pipeline is designed for non-invasive wearable sensors, making it viable for industrial deployment in automotive or electronics manufacturing.

---
*Note: Due to data privacy and governance protocols, raw biometric datasets are excluded. Full modeling scripts (R Markdown) are located in the `/scripts and /python_scripts` folder.*
