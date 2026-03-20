# Diabetes Prediction – Machine Learning Pipeline

> ⚠️ This repository is a **forked project**.  
> The work below represents my **independent contribution and extension** to the original codebase.

This project implements a complete **end-to-end machine learning pipeline** for predicting diabetes using the Pima Indians Diabetes dataset.  
The pipeline covers **data preprocessing, model training, evaluation, experimentation, and inference via CLI**.

---

## 📁 Project Structure
diabetes_pipeline/
│
├── dataset/
│ └── kaggle_diabetes.csv
│
├── model/
│ ├── diabetes_model.pkl
│ └── scaler.pkl
│
├── experiments/
│ └── experiment_runner.py
│
├── data_preprocessing.py
├── train.py
├── predict.py
├── evaluate.py
└── README.md

---

## 🚀 My Contributions

I independently designed and implemented the following components:

### 1. Data Preprocessing Pipeline
- Handled missing values in medical features:
	- `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI`
- Replaced invalid zeros with `NaN`
- Applied **mean / median imputation**
- Standardized features using `StandardScaler`
- Ensured consistent feature names across training and inference

📄 `data_preprocessing.py`

---

### 2. Model Training
- Implemented a reproducible training pipeline
- Trained and persisted:
	- Random Forest classifier
	- Feature scaler
- Stored trained artifacts for reuse and deployment

📄 `train.py`

---

### 3. Model Evaluation
- Added evaluation logic with:
	- Accuracy
	- Precision, Recall, F1-score
- Verified generalization on the test set

📄 `evaluate.py`

---

### 4. Experimentation Framework
- Benchmarked multiple ML models:
	- Logistic Regression
	- Decision Tree
	- Random Forest
	- Support Vector Machine (SVM)
- Automatically reports accuracy and F1-score

📄 `experiments/experiment_runner.py`

#### Sample Results

| Model                 | Accuracy | F1 Score |
|----------------------|----------|----------|
| Logistic Regression  | 0.7875   | 0.6320   |
| Decision Tree        | 0.9875   | 0.9805   |
| Random Forest        | 0.9950   | 0.9921   |
| SVM                  | 0.8450   | 0.7328   |

✔️ **Random Forest performs best on this dataset**

---

### 5. Command-Line Prediction Interface
- Built a CLI-based inference script
- Ensures:
	- Correct feature order
	- Feature-name alignment with trained scaler
- Predicts diabetes for a single patient input

📄 `predict.py`

Example:
```bash
python predict.py \
	--pregnancies 2 \
	--glucose 120 \
	--bp 70 \
	--skin 20 \
	--insulin 80 \
	--bmi 25 \
	--dpf 0.5 \
	--age 35



---

## 🛠️ Tech Stack

- Python 3.10+
- pandas
- numpy
- scikit-learn
- joblib

---

## 🧩 Notes

- Project is modular and deployment-ready
- Structured to support FastAPI / Flask integration
- Generated files cleaned using `.gitignore`
- Suitable for internship-level ML engineering evaluation

---

## 👩‍💻 Author Contribution

**Contributor:** Lemesa Girma  

**Contribution Scope:**
- ML pipeline design
- Data preprocessing
- Model training & evaluation
- Experimentation framework
- CLI-based inference system

---

## 📌 Disclaimer

This repository is a fork of an existing project.  
All enhancements, restructuring, and ML pipeline components listed above were implemented independently as part of my learning and internship preparation.
