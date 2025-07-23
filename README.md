# DeFi Wallet Credit Scoring

## Overview

This project aims to assign a **credit score between 0 and 1000** to each wallet interacting with the Aave V2 protocol. The score is derived solely from **historical transaction behavior**, using features engineered from raw DeFi activity logs such as `deposit`, `borrow`, `repay`, `redeemunderlying`, and `liquidationcall`. The higher the score, the more responsible and reliable the wallet is assumed to be.

## Objective

The goal is to:

* Understand and quantify wallet-level behavior.
* Classify wallets based on risk using interpretable features.
* Provide a plug-and-play scoring tool that processes wallet activity data in one step.

## Dataset

The dataset consists of **100,000 transaction-level records** from the Aave V2 protocol. Each record includes:

* `userWallet`: Wallet address
* `protocol`: Protocol identifier (e.g., Aave)
* `action`: Transaction type (e.g., deposit, borrow)
* `amount`: Amount transacted
* `assetSymbol`: Token involved
* `assetPriceUSD`: USD price of the asset
* `timestamp`: Time of transaction

## Feature Engineering

The following features are extracted per wallet:

* **Total Deposits**: Sum of all deposits in USD
* **Total Borrows**: Sum of all borrows in USD
* **Total Repays**: Sum of all repays in USD
* **Liquidation Count**: Number of times a wallet has been liquidated
* **Unique Assets Interacted With**: Measures diversity
* **Average Transaction Amount**: Indicates volume consistency
* **Borrow/Deposit Ratio**: Indicates over-leveraging behavior

## Scoring Logic

Each feature is:

1. **Normalized** to a \[0, 1] scale
2. **Weighted** based on its importance (e.g., liquidations heavily reduce score)
3. **Combined** into a final score on a scale of 0 to 1000

The final score helps:

* Identify bot-like behavior or aggressive borrowing
* Flag undercollateralized, risky wallets
* Recognize stable, frequent users

## How to Use

You can score wallets using the provided script:

```bash
python score_wallets.py --input path/to/transactions.json --output scores.csv
```

## Output

A CSV with the following columns:

* `userWallet`
* `credit_score`

## Future Work

* Include time-series decay to reward consistent behavior
* Integrate on-chain credit data from multiple protocols
* Apply unsupervised learning (e.g., clustering) to detect anomalies

## Contact

For any queries, feel free to reach out.

---

This system offers an interpretable, data-driven method to evaluate wallet reliability in DeFi. Built with transparency and extensibility in mind.
