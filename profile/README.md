## Zeur: A Zero-Interest Loan Protocol for the Real Economy

Zeur is a decentralized lending platform where users can borrow EUR-backed stablecoins (e.g., EURC) without paying interest by using crypto assets like ETH, LINK, or LSTs as collateral. Instead of charging interest, the protocol earns yield from staking/lending strategies and passes it to EURC lenders.

## The Problem We Solve

Crypto users in Europe often need liquidity for real-world purchases but don’t want to sell assets due to taxes and future price potential. Current options include:

* High-interest DeFi loans
* Slow, paperwork-heavy TradFi loans
* Other zero-interest protocols with illiquid, non-fiat stablecoins

These fail to offer simple, low-cost, real-world access to funds.

## Our Solution

Zeur offers:

* **Zero-interest, flexible repayment** for borrowers
* **High, stable yields** on EURC for lenders
* A smooth **bridge between crypto and real-world spending** using regulated, fiat-backed EURC

## Overview

Zeur blends DeFi lending with staking to let users borrow EUR stablecoins while earning yield on their crypto collateral.

## Key Features

* **Collateralized Lending:** Secure loans using ETH/LINK with customizable LTV ratios
* **Auto Staking:** Collateral is staked in protocols like Lido and Morpho to earn yield
* **EUR Loans:** Use EURC/EURI, improving access to euros over USD
* **Liquidation Protection:** Automated systems ensure safety and stability with real-time monitoring

## Architecture Overview

![image](https://github.com/user-attachments/assets/9057d1eb-29cf-4c09-8592-e367b041c279)

> Overall Flow Summary
- Borrower: Deposits collateral and borrows zero-interest EUR stablecoins.
- Lender: Deposits EUR stablecoins to provide liquidity and earn yield.
- VaultManager: Manages collateral, rebalances portfolios, handles staking, and distributes yield.
- ElizaOS + Chainlink Automation: Executes automated strategies and rebalances based on real-time data.

## [Core contract lists](https://github.com/zeur-org/zeur-core/blob/master/docs/Deployments/deployed-v1.md)
