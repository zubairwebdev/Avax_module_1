# ERC20 and Vault Smart Contracts

## Overview

This repository contains two Solidity smart contracts:

1. **ERC20** - A simplified implementation of the ERC20 token standard.
2. **Vault** - A contract to manage deposits and withdrawals of ERC20 tokens using a share-based mechanism.

These contracts are written in Solidity and are designed to work with the Ethereum blockchain. The compiler version used is `^0.8.17`.

---

## Table of Contents

- [ERC20 Contract](#erc20-contract)
  - [Description](#description)
  - [Key Features](#key-features)
  - [Core Functions](#core-functions)
  - [Events](#events)
  - [Usage Example](#usage-example)
- [Vault Contract](#vault-contract)
  - [Description](#description-1)
  - [Key Features](#key-features-1)
  - [Core Functions](#core-functions-1)
  - [Share Calculation](#share-calculation)
  - [Usage Example](#usage-example-1)
- [Prerequisites](#prerequisites)
- [Deployment](#deployment)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## ERC20 Contract

### Description
The `ERC20` contract is a simple implementation of the ERC20 token standard. It includes basic token functionalities such as transferring tokens, setting allowances, and approving spenders. Additionally, the contract supports minting new tokens and burning tokens from the holder's balance.

### Key Features
- **Token Details**:
  - Name: `Solidity by Example`
  - Symbol: `SOLBYEX`
  - Decimals: `2`
  
- **Standard ERC20 Functions**:
  - `transfer(address recipient, uint amount)`: Transfer tokens from the sender to the recipient.
  - `approve(address spender, uint amount)`: Approve a spender to spend a specific amount of tokens on behalf of the sender.
  - `transferFrom(address sender, address recipient, uint amount)`: Allow an approved spender to transfer tokens on behalf of the sender.

- **Minting and Burning**:
  - `mint(uint amount)`: Mint new tokens to the sender's account.
  - `burn(uint amount)`: Burn tokens from the sender's account.

### Core Functions
```solidity
function transfer(address recipient, uint amount) external returns (bool)
function approve(address spender, uint amount) external returns (bool)
function transferFrom(address sender, address recipient, uint amount) external returns (bool)
function mint(uint amount) external
function burn(uint amount) external

## Vault Contract


### Vault Contract
### Description
The Vault contract allows users to deposit and withdraw ERC20 tokens in a secure manner. It operates on a share-based system where the value of a user's shares represents their ownership in the vault's assets. This contract is intended for managing token deposits and withdrawals without requiring users to directly handle token balances.

Key Features
Deposits: Users can deposit ERC20 tokens into the vault, and the system will mint shares for the user based on the deposited amount.
Withdrawals: Users can withdraw ERC20 tokens by burning the corresponding amount of shares.
