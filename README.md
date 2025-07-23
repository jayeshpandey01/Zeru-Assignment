
---

### 📊 Credit Score Classification from DeFi Transactions

This notebook implements a machine learning pipeline to predict a **credit score (0–1000)** for DeFi wallets based on their **transaction history** with the **Aave V2 protocol**.

#### 🔍 Problem Statement

The goal is to assess wallet reliability by analyzing behaviors such as:

* Deposits
* Borrows
* Repayments
* Liquidations
* Withdrawals

Higher credit scores indicate responsible and consistent usage, while lower scores may reflect risky, exploitative, or bot-like behavior.

---

### 📁 File

* `credit_score_classification.ipynb`: End-to-end pipeline including:

  * Data preprocessing
  * Feature engineering
  * Model training (PyTorch)
  * Evaluation metrics
  * Inference on new wallet data

---

### 🧠 Approach

* **Feature Engineering**: Derived behavioral signals like frequency, amount volatility, liquidation ratio, etc.
* **Model**: A simple neural network trained with Binary Cross Entropy Loss to classify good vs. bad users, with post-processed scores mapped between `0-1000`.
* **Evaluation**: Accuracy, loss tracking across epochs, and test-set evaluation.

---

### ⚙️ Requirements

* Python 3.8+
* `pandas`, `numpy`, `torch`, `sklearn`, `matplotlib`

Install via:

```bash
pip install -r requirements.txt
```

---

### 🚀 Run the Notebook

Open the notebook and run all cells:

```bash
jupyter notebook credit_score_classification.ipynb
```
