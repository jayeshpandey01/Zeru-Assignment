# 📊 Credit Score Classification using Aave V2 Transaction Data

## 🔍 Overview

This project uses historical transaction-level data from the Aave V2 DeFi protocol to predict a **credit score (ranging from 0 to 1000)** for each wallet address. The main goal is to evaluate wallet behavior and classify it as responsible, risky, or bot-like using only transaction behavior features.

---

## 🔢 Methodology

### 1. **Data Source**

The model uses raw JSON transaction data that includes key actions:

* `deposit`
* `borrow`
* `repay`
* `redeemUnderlying`
* `liquidationCall`

Each row is a single wallet transaction.

### 2. **Feature Engineering**

We derived key behavioral features from the raw data:

* Total number and amount of deposits/borrows/repayments
* Liquidation count and liquidation ratio
* Average transaction amount per action
* Recency and activity frequency

### 3. **Score Bucketing**

A classification model outputs binary labels (good/bad behavior), and scores are scaled post-prediction to a **0-1000** range:

* Class 1 ➔ Score between 600-1000
* Class 0 ➔ Score between 0-600 (scaled by confidence)

### 4. **Model Architecture**

* Input: Engineered feature vector
* Hidden Layer: Fully connected (30 neurons, ReLU)
* Output Layer: 1 neuron with Sigmoid activation
* Loss: Binary Cross Entropy Loss (BCELoss)
* Optimizer: Adam

---

## 🌐 Project Files

| File                                | Description                                                             |
| ----------------------------------- | ----------------------------------------------------------------------- |
| `credit_score_classification.ipynb` | Full implementation of the data pipeline, training, and inference.      |
| `analysis.md`                       | Post-scoring analysis on wallet behavior, including distribution plots. |
| `README.md`                         | This file. Project overview, method, and structure.                     |

---

## ⚙️ Running the Code

1. Clone the repo

```bash
git clone https://github.com/yourusername/Zeru-Assignment.git
cd Zeru-Assignment
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Launch the notebook

```bash
jupyter notebook credit_score_classification.ipynb
```

---

## 🌍 Applications

* Wallet scoring for creditworthiness in DeFi platforms
* Bot/risk user identification
* Integration with lending/borrowing protocols for safer transactions

---

