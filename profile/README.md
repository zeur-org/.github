<h1 align="center">Zeur Protocol</h1>

<h3 align="center">A <code>Zero-Interest</code> Loan Protocol for the Real Economy</h3>

<p align="center">
  <a href="https://www.zeur.org/dashboard" style="color: #a77dff">Zeur Platform</a> | <a href="" style="color: #a77dff">Demo Video</a> | <a href="https://www.figma.com/deck/CmaR3CCAjsUcXbZdqYWKfq" style="color: #a77dff">Pitchdeck</a> | <a href="https://zeur.gitbook.io/zeur/" style="color: #a77dff">Docs</a> | <a href="https://github.com/zeur-org/zeur-core/tree/master/docs/Deployments" style="color: #a77dff">Core contract lists</a>
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
- Borrower: Deposits collateral and borrows zero-interest EUR stablecoins.
- Lender: Deposits EUR stablecoins to provide liquidity and earn yield.
- VaultManager: Manages collateral, rebalances portfolios, handles staking, and distributes yield.
- ElizaOS + Chainlink Automation: Executes automated strategies and rebalances based on real-time data.

## How to integrate the sponsor?

### [Avalanche](https://github.com/zeur-org/zeur-core/tree/master/script)
By providing cross-chain services on the Ethereum and Avalanche networks, we provide users with multi-network convenience.
We automatically deposit the sAVAX assets entrusted by the borrower as collateral into the Benqi DeFi protocol based on the Avalanche network with high yields and stable staking pools through AI agents to generate profits, provide 0% lending interest, and provide a % of the profit-earning assets to the lender as additional profits.
At this time, the EURC provided to the lender is also provided based on the Avalanche network, providing users with the convenience of utilizing both Ethereum and Avalanche networks.

### [Chainlink](https://github.com/zeur-org/zeur-core/tree/master/script)
Zeur provides a zero-interest lending protocol based on the Euro stable coin EURC, focusing on the European market.
Borrowers can borrow EURC by collateralizing stETH or LINK, and the stETH and LINK deposited as collateral are deposited in the most stable and profitable Vault services, such as AAVE, LIDO, Ether.fi, and Chainlink staking services, through AI agents to earn interest. 
This is done through real-time monitoring, and the agent automatically analyzes and deposits efficient strategic areas, while utilizing Chainlink automation and data streams to manage the assets deposited in the Vault.
Since the assets deposited as collateral are earning profits on their own, the lending interest is provided as zero, and additional EURC profits are earned for the lenders who provided EURC. This is a % provided on the profits earned through collateral.

### [ElizaOS](https://github.com/zeur-org/zeur-elizaos)
In the Zeur protocol, AI agents are responsible for managing the yield strategy, monitoring staking services (Vaults) on various DeFi protocols such as AAVE, LIDO, Ether.fi, and Chainlink, analyzing yields, and providing automated deposit and portfolio management services to deposit in the most stable and efficient pools to generate profits.
