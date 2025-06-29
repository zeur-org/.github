<h1 align="center">Zeur Protocol</h1>

<h3 align="center">A <code>Zero-Interest</code> Loan Protocol for the Real Economy</h3>

<p align="center">
  <a href="https://www.zeur.org/dashboard" style="color: #a77dff">Zeur Platform</a> | <a href="https://youtu.be/Ubt-k-e2Hw4" style="color: #a77dff">Demo Video</a> | <a href="https://www.figma.com/deck/CmaR3CCAjsUcXbZdqYWKfq" style="color: #a77dff">Pitchdeck</a> | <a href="https://zeur.gitbook.io/zeur/" style="color: #a77dff">Docs</a> | <a href="https://github.com/zeur-org/zeur-core/tree/master/docs/Deployments" style="color: #a77dff">Core contract lists</a>
</p>

<h2 align="center">Sponsor (Click on the logo)</h2>

<p align="center">
<a href="https://github.com/zeur-org#avalanche" height="5" width="10" target="_blank">
	<img src="https://github.com/user-attachments/assets/debeb0c3-c752-4347-b103-63f7e18c7895" width="100" height="100">
<a><a href="https://github.com/zeur-org#chainlink" height="5" width="10" target="_blank">
	<img src="https://github.com/user-attachments/assets/2298459f-4579-4545-8b81-d9c3ea8b7523" width="90" height="100">
<a><a><a href="https://github.com/zeur-org#elizaos" height="5" width="10" target="_blank">
	<img src="https://github.com/user-attachments/assets/9155c079-210e-46d0-bb11-865e2e90f68e" width="100" height="100">
<a></p>

## Overview

> Zeur blends DeFi lending with staking to let users borrow EUR stablecoins while earning yield on their crypto collateral.

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

## Key Features

* **Collateralized Lending:** Secure loans using ETH/LINK with customizable LTV ratios
* **Auto Staking:** Collateral is staked in protocols like Lido and Morpho to earn yield
* **EUR Loans:** Use EURC/EURI, improving access to euros over USD
* **Liquidation Protection:** Automated systems ensure safety and stability with real-time monitoring

## Architecture Overview

![image](https://github.com/user-attachments/assets/9057d1eb-29cf-4c09-8592-e367b041c279)

> Overall Flow Summary
- **Pool**: entry contract for users (supply, withdraw, borrow, repay, liquidate)
- **Vaults**: manage user deposited asset through Pool, interact with routers to stake asset in LST protocol.
- **StakingRouter**: plug-and-play contract that have the same interface, but different logics for each LST protocol (Lido, Etherfi, RocketPool, StakeLink or lending like Morpho)
- **Tokenization**: ColEURC/DebtEUR represent the user's supply/debt of EUR stablecoins, ColToken represents the user's collateral
- **ChainlinkOracleManager**: to get price of asset through Chainlink price feeds
- **VaultManager**: dedicated contract with harvest/distribute yield and rebalance portfolio logics
- **Chainlink Automation**: time-based keeper that execute distribute yield
- **ElizaOS**: offchain "brain" to monitor position, create strategy, execute rebalance

## How to integrate the sponsor?

### [Avalanche](https://github.com/zeur-org/zeur-core)
We provide users with multi-network convenience (Ethereum, Avalanche). We choose the networks based on the availability of EUR stablecoins (MICA-compliant as EURC) and liquid staking protocols. On Avalanche, borrowers can deposit AVAX, which is automatically deposited in Benqi staked AVAX (sAVAX). Lenders can deposit their EURC (present on Avalanche) and earn yield.

This is a win-win situation:
- AVAX holders can borrow EURC with zero cost while keeping their AVAX.
- EURC holders on Avalanche can earn organic, stable yield from sAVAX.
- Avalanche network becomes more secure with more AVAX participating in the liquid staking protocol (Benqi).

- **[Avalanche Fuji deployments](https://zeur.gitbook.io/zeur/deployments/avalanche-fuji)**

### [Chainlink](https://github.com/zeur-org/zeur-core)
We build a novel kind of lending market - zero interest lending, that lives entirely on-chain, unlocking crypto liquidity for everyday spending.
It is a combination of lending market, liquid staking, yield aggregator, AI agent for strategy optimization.
Collateral is simultaneously staked in liquid-staking platforms that secure Layer-1 chains (Ethereum, Chainlink, Avalanche), so assets earn yield even while backing loans.
By weaving these Chainlink services together, we demonstrate how verifiable data, autonomous execution, and native staking can power the next generation of secure, transparent financial products that bridge on-chain value with real-world spending.
Unlock cash, keep your crypto. Zero interest. Real Euros.

The protocol’s security and automation rely on the full Chainlink stack:

- Chainlink Price Feeds deliver real-time asset prices for safe LTV calculations, borrow/withdraw limits, and liquidations in the Pool contract.
  - [ChainlinkOracleManager](https://github.com/zeur-org/zeur-core/blob/master/src/chainlink/ChainlinkOracleManager.sol)
  - [Pool](https://github.com/zeur-org/zeur-core/blob/master/src/pool/Pool.sol)

- Chainlink Automation runs scheduled yield-harvest and distribution cycles, keeping payouts transparent and on time.
  - [ProtocolVaultManager](https://github.com/zeur-org/zeur-core/blob/master/src/pool/manager/ProtocolVaultManager.sol)

- Chainlink Staking lets users post staked LINK as collateral, adding a new utility layer for the LINK community while reinforcing network security.
  - [VaultLINK](https://github.com/zeur-org/zeur-core/blob/master/src/pool/vault/VaultLINK.sol)
  - [StakingRouterLINK](https://github.com/zeur-org/zeur-core/blob/master/src/pool/router/StakingRouterLINK.sol)

### [ElizaOS](https://github.com/zeur-org/zeur-elizaos)
In Zeur, an ElizaOS agent automates collateral management by:
- Tracking the current vault composition and LST balances
- Fetching APRs from Lido, EtherFi, Rocket Pool, and Morpho
- Assessing performance, risk, and available liquidity
- Determining optimal allocations and strategies
- Executing on-chain rebalancing transactions accordingly
This agent-driven approach delivers efficient, hands-off portfolio management for the protocol.
