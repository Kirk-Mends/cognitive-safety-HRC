# Predictive Stress Detection in Human-Robot Collaboration
**Kirk-Mends Attafuah | MSc Statistics, Wake Forest University**

### Project Overview
This research addresses the "Cognitive Safety" gap in high-stakes operational environments. I developed a machine learning pipeline to predict human stress states using multimodal physiological signals (EDA, ECG, and Heart Rate), allowing for adaptive safety interventions in complex human-robot systems.

### Technical Challenges and Data Engineering
The primary challenge was the raw sensor data, which was asynchronous and noisy. I architected a custom ETL workflow in R to:
* Reconstruct inconsistent timestamps to align multimodal signals.
* Normalize data across multiple test subjects to ensure model generalizability.
* Extract 50+ statistical and physiological features, specifically identifying Heart Rate Variability (HRV) as a key indicator.

### Model Benchmarking
I evaluated several classification algorithms to find the best balance between latency and accuracy:
* **Models Tested:** Logistic Regression, SVM, k-NN, Gradient Boosting, and Random Forest.
* **Selection:** Random Forest delivered the most robust performance, effectively handling the non-linear spikes typical in biometric telemetry.

### Results and Insights
The final model achieved an accuracy of [Your %]. The project demonstrates that raw, noisy biometric data can be transformed into a reliable safety layer for real-time operational decision-making.

---
*Note: Raw biometric datasets are excluded per data privacy and governance protocols. Cleaning and modeling scripts are located in the /scripts folder.*
