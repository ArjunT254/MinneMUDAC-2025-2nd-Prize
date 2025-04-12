# MinneMUDAC Hackathon - Push To Prod 🚀

🏆 **2nd Place Winner - MinneAnalytics MUNDAC Hackathon 2025**  
📅 Duration: One-month long challenge  
🤝 In collaboration with: Big Brothers Big Sisters Twin Cities  
🎯 Theme: **Improving mentorship outcomes using structured and unstructured data**

---

## 🧠 Problem Statement

The task was to predict the **match length (in days)** for mentor-mentee relationships using structured profile data and unstructured contact notes. 

The challenge involved:
- A test set containing **match IDs with truncated meeting notes**, ending at random intervals — simulating partial visibility into match history.
- Identifying emotional and behavioral signals hidden in text data to forecast when a match might close.
- Designing data-driven interventions that could help prevent early match closures.

---

## 💡 Our Technical Solution

### 📌 Key Objectives
1. Predict the duration of a match using partial interaction history.
2. Engineer meaningful features from free-text notes.
3. Improve model generalization under real-world imbalance and truncation scenarios.

---

### 🔍 3-Phase Approach

#### 🔹 Pre-Match
- Engineered clusters using mentor and mentee demographic and preference features.
- Identified high-potential matching profiles based on historical success patterns.

#### 🔹 During Match
- **NLP pipeline** applied to contact notes to extract:
  - Sentiment scores using **BERT-based transformers** (HuggingFace models)
  - Emotion tone classification (e.g., frustration, satisfaction, disengagement)
- Built custom text-based feature vectors using embeddings, sentiment, emotion frequency, and note density.
- Developed a **custom oversampling function** to augment underrepresented match durations and handle label imbalance.

#### 🔹 Modeling
- Built a regression pipeline using **XGBoost Regressor** to predict match length.
- Performed **cross-validation with grid search** for hyperparameter tuning.
- Applied early stopping and feature importance tracking for model optimization.

#### 🔹 Post-Match
- Interpreted key predictors contributing to early closures.
- Suggested staff-facing tools for early intervention and dynamic resource allocation.

---

## ⚙️ Tech Stack

- **Python 3.9**
- **Pandas, NumPy, scikit-learn** for data processing and modeling
- **XGBoost** for final regression model
- **HuggingFace Transformers (BERT)** for NLP sentiment/emotion extraction
- **NLTK, spaCy** for preprocessing
- **Matplotlib, Seaborn** for EDA and visualizations
