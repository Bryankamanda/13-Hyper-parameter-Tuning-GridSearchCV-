

#  Hyperparameter Tuning & Model Selection – Iris Classification

##  Project Overview

This project demonstrates how to systematically select and optimize a machine learning model using:

* Train-Test Split (baseline)
* K-Fold Cross Validation
* GridSearchCV (automated hyperparameter tuning)

The goal is to identify the **best-performing model configuration** for classifying iris flower species using the **Iris dataset from Scikit-learn**.

---

##  Objective

To:

* Compare different model evaluation strategies
* Apply cross-validation for reliable performance estimation
* Tune hyperparameters to improve model accuracy
* Select the best model based on empirical results

---

##  Dataset Used

###  Iris Dataset (Scikit-learn)

* 150 samples
* 4 features (sepal & petal dimensions)
* 3 classes:

  * Setosa
  * Versicolor
  * Virginica

This dataset is well-suited for testing classification algorithms due to its **clear class structure with slight overlap**.

---

##  Model Selection Approaches

###  Approach 1: Train-Test Split + Manual Tuning

* Used a single split of data into training and testing sets
* Parameters were adjusted manually through trial and error

**Limitations:**

* Performance depends on one random split
* High variance in results
* Not reliable for model selection

---

###  Approach 2: K-Fold Cross Validation

* Applied **5-Fold Cross Validation** using `cross_val_score`
* Tested different models and parameters manually

**Advantages:**

* More robust performance evaluation
* Reduces bias from single split
* Better generalization estimate

---

###  Approach 3: GridSearchCV (Automated Tuning)

* Performed exhaustive search over hyperparameter combinations
* Used cross-validation internally
* Automatically selected the best model

**Advantages:**

* Efficient and systematic
* Eliminates manual tuning effort
* Production-ready approach

---

##  Model Performance Comparison

| Model               | Parameters           | Mean CV Score    |
| ------------------- | -------------------- | ---------------- |
| SVM                 | C=1, kernel='linear' | ~0.97            |
| SVM                 | C=1, kernel='rbf'    | **~0.98 (Best)** |
| Logistic Regression | default              | ~0.96            |
| Decision Tree       | default              | ~0.95            |

>  *Scores are approximate and depend on random state and folds*

---

##  Final Model Selection

Based on cross-validation performance:

 **Support Vector Machine (SVM)**

* `C = 1`
* `kernel = 'rbf'`

was selected as the **optimal model** for this classification problem.

---

##  Why RBF Kernel Performed Better

The **Radial Basis Function (RBF) kernel** outperformed the linear kernel because:

* The Iris dataset is **not perfectly linearly separable**
* RBF captures **non-linear relationships** between features
* It maps data into a higher-dimensional space where classes become separable
* Provides flexible decision boundaries compared to linear models

This makes RBF more effective for datasets with **overlapping class distributions**.

---

##  Tools & Libraries Used

* Python 
* NumPy 
* Pandas 
* Scikit-learn 
* Jupyter Notebook 

---

##  Key Takeaways

* Train-test split alone is insufficient for reliable evaluation
* Cross-validation significantly improves model assessment
* Hyperparameter tuning is essential for optimal performance
* GridSearchCV provides a scalable and automated solution
* Kernel selection plays a critical role in SVM performance

---

##  Why This Project Matters (Recruiter View)

This project demonstrates:

* Strong understanding of **model evaluation strategies**
* Ability to compare and justify different approaches
* Practical experience with **hyperparameter tuning**
* Knowledge of **bias-variance tradeoff**
* Readiness for real-world ML workflows and model optimization

---

##  Real-World Applications

* Fraud detection systems
* Medical diagnosis models
* Customer classification
* Financial risk prediction
* Any ML system requiring optimized performance

---

##  Author

Bryan Kamanda


