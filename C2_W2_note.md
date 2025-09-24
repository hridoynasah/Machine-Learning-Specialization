#  Week 3 – Advice for Applying Machine Learning

##  Core Theme of Week 3

Week 3 shifts away from math-heavy algorithms into **practical strategy**:

* How to **diagnose problems** in machine learning projects.
* How to decide **what to try next** (collect more data, tune hyperparameters, change features, etc.).
* How to avoid wasting months on unproductive directions.

---

## 1. Common Choices After Training a Model

Suppose you trained **regularized linear regression** on housing prices, but predictions are poor. What could you do?

Possible next steps:

1. **Get more training examples** (data augmentation/collection).
2. **Reduce features** (simplify input space).
3. **Add more features** (collect new data points about houses).
4. **Create polynomial features** (e.g., $x_1^2, x_2^2, x_1x_2$).
5. **Tune regularization parameter ($\lambda$)**:

   * Too big → high bias.
   * Too small → high variance.

---

## 2. The Problem of Choice

* Many options → some may help, some may not.
* Without guidance, teams often waste time:

  * Example: spending *months* collecting more data, only to see little improvement.
* **Efficiency = knowing where to invest time.**

---

## 3. The Role of Diagnostics

* **Diagnostic = test** to understand what’s working or failing.
* Benefits:

  * Helps decide whether more data is worth the effort.
  * Can save **weeks or months** by ruling out ineffective ideas.
* Diagnostics **take time to implement**, but they often save far more time later.

---

## Key Insights :

* By now you know **many algorithms** (linear/logistic regression, neural nets, and decision trees coming up).
* The next challenge: **choosing wisely among options** when your model underperforms.
* Effective ML engineers rely on **diagnostics** to guide choices.
* This week focuses on:

  * Evaluating algorithm performance properly.
  * Running diagnostics to identify bias/variance problems.
  * Making **data-driven decisions** about whether to collect more data, add features, or tune hyperparameters.



  Great — this is **Week 3, Lecture 2** on how to **evaluate a model’s performance**. Here’s the structured tutorial-style breakdown:

---

# Evaluating Model Performance

##  Why Evaluation Matters

* Fitting a complex model (e.g., 4th order polynomial) can perfectly match training data.
* But such a model may **fail to generalize** (too wiggly → overfitting).
* In high dimensions (many features), plotting isn’t possible → need **systematic evaluation**.

---

## 1. Splitting Data into Training & Test Sets

* Dataset split (common ratios):

  * **70% training**, **30% test** (or 80/20).
* Training set → used to fit model parameters $(w, b)$.
* Test set → used to evaluate generalization performance.

### Notation

* Training examples:
  $(x^{(1)}_{\text{train}}, y^{(1)}_{\text{train}}), \dots, (x^{(m_{train})}, y^{(m_{train})})$
* Test examples:
  $(x^{(1)}_{\text{test}}, y^{(1)}_{\text{test}}), \dots, (x^{(m_{test})}, y^{(m_{test})})$

---

## 2. Regression Example (Linear Regression with Squared Error)

### Training

* Minimize **regularized cost**:

  $$
  J(w,b) = \frac{1}{2m_{train}} \sum_{i=1}^{m_{train}} (\hat{y}^{(i)} - y^{(i)})^2 + \frac{\lambda}{2m_{train}} \sum_j w_j^2
  $$

### Evaluation

* **Test Error** (no regularization term):

  $$
  J_{\text{test}}(w,b) = \frac{1}{2m_{\text{test}}} \sum_{i=1}^{m_{\text{test}}} (\hat{y}_{\text{test}}^{(i)} - y_{\text{test}}^{(i)})^2
  $$

* **Training Error** (also excludes regularization):

  $$
  J_{\text{train}}(w,b) = \frac{1}{2m_{\text{train}}} \sum_{i=1}^{m_{\text{train}}} (\hat{y}_{\text{train}}^{(i)} - y_{\text{train}}^{(i)})^2
  $$

Important:

* Cost function during training **includes regularization** (to avoid overfitting).
* Errors (train/test) are reported **without regularization** (to measure pure predictive accuracy).

---

## 3. Classification Example (Logistic Regression)

### Training

* Minimize **logistic loss with regularization**:

  $$
  J(w,b) = \frac{1}{m_{train}} \sum_{i=1}^{m_{train}} \big[ -y^{(i)} \log \hat{y}^{(i)} - (1-y^{(i)}) \log(1-\hat{y}^{(i)}) \big] + \frac{\lambda}{2m_{train}} \sum_j w_j^2
  $$

### Evaluation

* **Option 1: Average logistic loss** on test set (same form as above, but no regularization).
* **Option 2 (common): Misclassification error**:

  * Predict:

    $$
    \hat{y} =
    \begin{cases}
    1 & \text{if } f(x) \geq 0.5 \\
    0 & \text{otherwise}
    \end{cases}
    $$
  * Compute fraction misclassified:

    $$
    J_{\text{test}} = \frac{1}{m_{\text{test}}} \sum_{i=1}^{m_{\text{test}}} \mathbf{1}(\hat{y}^{(i)} \neq y^{(i)})
    $$

---

## 4. Key Takeaways

* Always **separate training and test sets** to check generalization.
* Training error ≈ “fit to known data.”
* Test error ≈ “ability to generalize.”
* **Low train error + high test error = overfitting.**
* For classification:

  * Can use loss (logistic cost).
  * More common: use **misclassification rate** (fraction of wrong predictions).

---

##  Summary

* Splitting data into **train/test** is the foundation of systematic evaluation.
* Training cost includes **regularization** (bias/variance trade-off).
* Train/test errors **exclude regularization** (measuring pure predictive performance).
* Evaluation method depends on problem type:

  * Regression → squared error.
  * Classification → logistic loss or misclassification rate.
* This procedure is the **first step** toward automatically selecting models (e.g., polynomial degree, feature set).


Perfect — this is **Week 3, Lecture 3** on **Model Selection and Cross-Validation**. Let’s break it down tutorial-style:

---

#  Week 3 – Lecture 3: Model Selection & Cross-Validation

##  Why We Need More Than Train/Test

* **Training error** ≠ reliable measure of generalization.

  * Often very low (sometimes near zero).
* **Test error** is better, but…

  * If you **use the test set to pick hyperparameters** (e.g., polynomial degree $d$), you make it an **optimistic estimate** of performance.
  * This is because test data is indirectly influencing the choice.

 Flaw: Choosing models directly based on test error → **biased estimate of generalization error.**

---

## 1. Model Selection Example

* Task: Predict housing prices using polynomial regression.
* Candidate models:

  * $d=1$ → linear.
  * $d=2$ → quadratic.
  * … up to $d=10$.
* Naïve approach:

  * Fit each degree on training set.
  * Compute $J_{\text{test}}$.
  * Pick the model with lowest $J_{\text{test}}$.
* Problem:

  * You used the **test set to decide $d$**.
  * Now $J_{\text{test}}$ is no longer a fair estimate of true generalization.

---

## 2. The Correct Procedure: Train / Dev / Test Split

Instead of just 2 sets, split data into **3 sets**:

1. **Training set** (e.g., 60%) → fit parameters $w, b$.
2. **Cross-validation (CV) set** (a.k.a. validation or dev set, e.g., 20%) → used for **model selection** (choose $d$, architecture, etc.).
3. **Test set** (e.g., 20%) → final unbiased estimate of performance.

### Notation

* $J_{\text{train}}$ → error on training set.
* $J_{\text{cv}}$ → error on cross-validation set.
* $J_{\text{test}}$ → error on test set.
* All exclude the regularization term (measure pure predictive performance).

---

## 3. How Model Selection Works

* For each candidate model (e.g., $d=1 \dots 10$):

  * Fit parameters on training set.
  * Compute $J_{\text{cv}}$.
* Pick the model with lowest $J_{\text{cv}}$.
* Finally, report generalization performance using $J_{\text{test}}$ of the chosen model.

 This ensures:

* No leakage of test set into model selection.
* $J_{\text{test}}$ remains a fair, unbiased estimate of generalization.

---

## 4. Neural Network Example

* Choosing between architectures:

  * Small network ($w_1, b_1$).
  * Medium network ($w_2, b_2$).
  * Large network ($w_3, b_3$).
* Procedure:

  * Train each on training set.
  * Compute $J_{\text{cv}}$ (e.g., misclassification rate).
  * Select architecture with lowest $J_{\text{cv}}$.
  * Finally, estimate generalization with $J_{\text{test}}$.

---

##  Best Practices

* **Never use test set** to choose hyperparameters or architectures.
* Use **training + cross-validation** for all decision-making.
* Only use test set once, at the very end, to report unbiased performance.
* Common terminology:

  * Cross-validation set = validation set = dev set.
* Personally, “dev set” is the fastest shorthand (Andrew Ng’s preference).

---

##  Summary

* Training error is overly optimistic → doesn’t reflect generalization.
* Using test set for model selection also makes test error optimistic.
* Solution: Split into **Train / Dev / Test**:

  * Train → fit parameters.
  * Dev → choose model/hyperparameters.
  * Test → final unbiased evaluation.
* Works for regression (polynomial degree) and classification (NN architecture, depth, hidden units).
* This procedure is called **model selection**, and it’s a standard ML workflow.






