# Biometric Identification

This repository contains the final project for the **School on Biometrics** course. The project focuses on evaluating biometric identification tools and implementing "Late Fusion" techniques to improve system accuracy beyond the capabilities of a single algorithm.

## 📋 Project Overview

The project was divided into two primary phases:
1. **Performance Evaluation:** Comparing between three different biometric identification tools and generating ROC curves. (ROC plot is usef to evaluate the performance of a bin classifier system)
2. **Score Fusion:** Developing an aggregation method to combine scores from individual tools to outperform any single tool's individual performance.

## 🛠️ Modality & Data
* **Biometric Feature:** FACE
* **Database:** CASIA-FaceV5
* **Tools Analyzed:**
  1. DeepFace - https://github.com/serengil/deepface
  2. VGGFace - https://github.com/rcmalli/keras-vggface
  3. ArcFace - https://github.com/deepinsight/insightface

## 📊 Phase 1: Performance Analysis
I evaluated the individual performance of three distinct identification tools by calculating error rates across various thresholds.
* **Metrics:** Calculated **FMR** (False Match Rate) and **FNMR** (False Non-Match Rate).
* **Experiment Design:** Balanced the number of genuine tests against impersonation (imposter) tests to ensure statistical validity.
* **Visualization:** Generated a **ROC (Receiver Operating Characteristic)** plot to compare the performance trade-offs of each tool.


## 🧬 Phase 2: Score-Level Fusion (Gradient Boosting)
For the fusion phase, I implemented a machine learning approach to aggregate the outputs of the three biometric tools.

* **The Method:** I utilized a **Gradient Boosting Classifier** to perform late-stage score fusion. 
* **Selection Logic:** While simpler methods like *Rank Averaging* were tested, they resulted in significant information loss (AUC ~0.5). Gradient Boosting was selected because it effectively captures non-linear relationships between the scores of different models.
* **Results:** The fusion model achieved an **AUC of 0.89**, successfully outperforming the best individual tool (DeepFace, AUC 0.87). This confirms that combining the strengths of multiple architectures (ArcFace, VGG, and DeepFace) leads to a more robust identification system.

<img width="597" height="452" alt="image" src="https://github.com/user-attachments/assets/2d1446e2-59d0-4b98-839b-e5232d7d93a1" />

## 💻 Tech Stack
* **Languages:** [Python]
* **Core Concepts:** Biometric Matching, Score Normalization, Late Fusion, Statistical Evaluation.
