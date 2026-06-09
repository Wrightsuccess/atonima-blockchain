# Atonima Control Technical Architecture

## Architecture Overview

Atonima Control is designed as a middleware layer between AI agents and financial systems.

The system does not replace existing AI agents or payment rails. Instead, it governs how agents interact with financial infrastructure.

## High-Level Flow

External AI Agent
↓
Atonima Control API
↓
Agent Registry
↓
Policy Engine
↓
Human Approval Workflow, if required
↓
Transaction Attribution Layer
↓
Financial System or Blockchain Rail
↓
Audit Log

## Core Components

### 1. Agent Registry

Stores and manages information about approved AI agents.

Data may include:

* Agent ID
* Agent name
* Agent owner
* Agent purpose
* Connected wallet
* Status
* Permission scope
* Risk level

### 2. Policy Engine

Evaluates every requested financial action against defined policies.

Example policies:

* Maximum payment amount
* Approved recipients
* Approved wallets
* Restricted regions
* Time-based restrictions
* Approval thresholds
* Daily transaction limits

### 3. Approval Layer

Determines whether human approval is required.

Example:

* Payments under $500 can proceed automatically
* Payments over $1,000 require human approval
* Unknown wallets are blocked

### 4. Attribution Layer

Labels each action based on origin.

Examples:

* `ai_tx` for AI agent initiated actions
* `hu_tx` for human initiated actions

On existing blockchains, Atonima does not change native transaction hash formats. Instead, attribution is stored through metadata, smart contract events, memos, or off-chain audit records linked to the transaction.

### 5. Stellar Integration Layer

For the Stellar MVP, Atonima may integrate with:

* Stellar wallets
* Soroban smart contracts
* Stellar transaction memos
* Stellar payment flows
* Stellar Disbursement Platform use cases

### 6. Audit Log

Stores a complete record of every agent action.

Audit log fields may include:

* Agent ID
* Human owner
* Requested action
* Policy decision
* Approval status
* Timestamp
* Transaction reference
* Risk flag
* Reason for approval or rejection

## MVP Implementation

The first proof of concept should include:

1. Agent registration dashboard
2. Basic policy creation
3. Simulated payment request
4. Policy approval or rejection
5. Human vs agent attribution
6. Audit log dashboard
7. Stellar testnet transaction reference

## Future Architecture

Future versions may include:

* Multi-chain support
* API access for external agent platforms
* Enterprise role-based access
* Compliance reporting
* Advanced risk scoring
* ZK-based permission proofs
* Banking and treasury API integrations
