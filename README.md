# Decentralised-stable-coin
# Decentralized Stable Coin

A decentralized, overcollateralized stablecoin protocol built on Ethereum. This project allows users to deposit approved collateral tokens, mint stablecoins against their collateral, burn stablecoins, redeem collateral, and maintain protocol health through liquidation mechanisms.

## Overview

The Decentralized Stable Coin (DSC) project is designed to create a crypto-backed stablecoin system that aims to maintain stability through overcollateralization. Users can lock supported crypto assets as collateral and mint DSC tokens based on the USD value of their deposited assets.

The protocol ensures that every minted stablecoin is backed by more value than it represents. If a user's collateral value falls below the required threshold, their position can be liquidated to protect the system.

## Features

- Deposit approved collateral tokens
- Mint decentralized stablecoins
- Burn stablecoins to reduce debt
- Redeem collateral after burning DSC
- Health factor calculation for user positions
- Liquidation mechanism for undercollateralized positions
- Price feed integration using Chainlink oracles
- Built with Solidity and tested using Foundry

## Tech Stack

- **Solidity** for smart contract development
- **Foundry** for testing, scripting, and deployment
- **Chainlink Price Feeds** for collateral valuation
- **OpenZeppelin** for secure token standards and utilities

## Project Structure

```bash
├── src
│   ├── DecentralizedStableCoin.sol
│   ├── DSCEngine.sol
│   ├── interfaces/
│   ├── libraries/
│   └── ...
├── script
│   ├── DeployDSC.s.sol
│   └── HelperConfig.s.sol
├── test
│   ├── unit/
│   ├── fuzz/
│   └── ...
├── lib
└── foundry.toml

How It Works
1. Deposit Collateral

Users deposit approved ERC20 collateral tokens such as WETH or WBTC into the protocol.

2. Mint DSC

Based on the USD value of the deposited collateral, users can mint DSC while staying above the minimum collateralization threshold.

3. Maintain Health Factor

Each account has a health factor that determines the safety of its position. If the health factor goes below the minimum required value, the position becomes eligible for liquidation.

4. Burn DSC and Redeem Collateral

Users can burn their DSC tokens to reduce debt and redeem their collateral.

5. Liquidation

If a user's position becomes undercollateralized, liquidators can repay part of the user's debt and receive collateral in return, often with a liquidation bonus.

Core Contracts
DecentralizedStableCoin.sol

The ERC20 stablecoin contract responsible for minting and burning DSC tokens.

DSCEngine.sol

The main protocol logic contract that handles:

collateral deposits

minting and burning DSC

redeeming collateral

health factor checks

liquidation process

Key Concepts
Overcollateralization

The system requires users to deposit more collateral value than the value of DSC they mint. This helps maintain protocol solvency.

Health Factor

The health factor is used to determine whether a user's position is safe. A low health factor indicates that the user's collateral may no longer sufficiently back their minted stablecoins.

Liquidation Threshold

The liquidation threshold defines how much DSC a user can safely mint relative to their collateral value.

Installation
Prerequisites

Make sure you have the following installed:

Foundry

Git
