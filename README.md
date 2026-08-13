# DL_NN__002
# Practical No. 2
## Constructing a Deep Neural Network for Binary Classification Using TensorFlow

---

### Aim
To design, train, and evaluate a Deep Neural Network (DNN) for solving a binary classification problem using TensorFlow and Keras.

--- 

### Scope
This practical focuses on implementing a complete deep learning workflow for binary classification, including data preprocessing, model construction, training, evaluation, and prediction using TensorFlow.

---

### Dataset
**Breast Cancer Wisconsin Diagnostic Dataset**

### Dataset Source
[Kaggle – Breast Cancer Wisconsin Diagnostic Dataset](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)

- 569 samples
- 30 numerical features
- Binary target: `0` = Malignant, `1` = Benign

---

### Libraries Used
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

### Data Preprocessing

The following sequence is applied strictly to prevent data leakage:

```
Train/Test Split  (80% train / 20% test, random_state=42)
        ↓
Fit StandardScaler on Training Data
        ↓
Transform Training Data
        ↓
Transform Test Data
```

> **Important:** `StandardScaler` is fitted **only on the training data**. The same fitted scaler is then used to transform the test data. Fitting on the full dataset before splitting would leak test-set statistics into training, which is incorrect.

---

### Model Architecture

| Layer          | Configuration    |
|----------------|------------------|
| Input Layer    | 30 features      |
| Hidden Layer 1 | 32 neurons, ReLU |
| Hidden Layer 2 | 16 neurons, ReLU |
| Output Layer   | 1 neuron, Sigmoid|

---

### Model Compilation

|   Setting     |          Value      |
|---------------|-------------------- |
| Optimizer     |        Adam         |
| Loss Function | Binary Crossentropy |
| Metric        |        Accuracy     |

---

### Model Training

| Setting         | Value                     |
|-----------------|-------------------------- |
| Epochs          | 100                       |
| Batch Size      | 32                        |
| Validation Split| 0.2 (20% of training data) |

---

### Performance Evaluation

The notebook evaluates the trained model using the following metrics:

- Accuracy
- Confusion Matrix
- Precision
- Recall
- F1-Score
- Prediction for new samples

---

### Part E – Experimental Analysis

The notebook compares model performance across four experiments using the same train/test split and standardized data throughout:

1. **Different numbers of hidden layers** — 1, 2, and 3 hidden layers
2. **Different numbers of neurons** — 8, 16, and 32 neurons per layer
3. **Optimizers** — Adam vs SGD
4. **Activation functions** — ReLU vs Tanh vs Sigmoid

The final comparison is presented as a single table containing the experimental configuration and test accuracy for each run.

---

### Results and Outcome


#### Performance Metrics

| Metric | Result |
|---|---:|
Test Loss: 0.1248849481344223
Test Accuracy: 0.9649122953414917
Accuracy: 0.9649122807017544
Precision: 0.958904109589041
Recall: 0.9859154929577465
F1 Score: 0.9722222222222222



![Accuracy Graph](accuracy_plot.png)

#### Training and Validation Loss

![Loss Graph](loss_plot.png)

---

