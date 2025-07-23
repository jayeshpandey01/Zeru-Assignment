# 📈 Wallet Score Analysis

This document presents a detailed analysis of the credit scores assigned to wallets based on their transaction activity on the Aave V2 protocol.

---

## 🧠 Score Distribution

The credit scores range from 0 to 1000. Below is the histogram distribution across score bands:

| Score Range | Number of Wallets                    |
| ----------- | ------------------------------------ |
| 0 - 100     | ██▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ (High Risk) |
| 100 - 200   | ██▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉                    |
| 200 - 300   | ██▉▉▉▉▉▉▉▉                           |
| 300 - 400   | █▉▉▉▉▉▉▉▉                            |
| 400 - 500   | █▉▉▉▉                                |
| 500 - 600   | █▉                                   |
| 600 - 700   | █                                    |
| 700 - 800   | ▉                                    |
| 800 - 900   | ▉                                    |
| 900 - 1000  | ▉ (Excellent Reliability)            |

---

## 🔍 Observations

### Low Score Wallets (0-300):

* High number of `liquidationCall` events.
* Borrowed more frequently without repayment.
* Very few `repay` actions.
* Typically show irregular or bot-like behavior.

### Medium Score Wallets (400-600):

* Balanced borrowing and repayment behavior.
* Infrequent liquidations.
* Consistent but not high-value activity.

### High Score Wallets (700-1000):

* Regular depositors and timely repayments.
* Zero or minimal liquidation events.
* Demonstrate responsible usage of the protocol.
* Often have higher volume transactions and consistent engagement.

---

## 📊 Example Graphs

Visualizations (can be generated from the notebook):

* Score distribution histogram
* Box plot of transaction volume vs. score
* Count of liquidations by score range

---

## 📌 Conclusion

The scoring methodology successfully captures and differentiates behavior patterns across wallet types. High-risk users are accurately flagged by their transaction traits, and responsible wallets are rewarded with high scores. This system could support lending decision-making and risk assessment in decentralized finance platforms.
