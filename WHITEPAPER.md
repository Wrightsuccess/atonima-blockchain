# Atonima Control Documentation

## Overview

Atonima Control is an AI governance and financial controls platform that helps businesses safely connect existing AI agents to financial systems.

The platform is designed to sit between AI agents and payment infrastructure, enforcing permissions, policies, approvals, attribution, and auditability before financial actions are executed.

## Core Problem

As AI agents become capable of initiating payments, managing treasury operations, interacting with stablecoins, and automating financial workflows, businesses need a way to control what those agents are allowed to do.

Without a governance layer, organizations face risks such as unauthorized payments, policy violations, unclear accountability, and limited auditability.

## Core Product

Atonima Control provides:

### Agent Registry

Businesses can register existing AI agents and assign each agent an owner, purpose, wallet, permissions, and status.

### Policy Engine

Organizations can define financial rules for agents, including transaction limits, approved recipients, approval thresholds, restricted actions, and time-based restrictions.

### Human Approval Workflows

High-risk actions can require human review before execution.

### Human vs Agent Attribution

Atonima identifies whether an action was initiated by a human or an AI agent.

Example labels:

`hu_tx` = human initiated transaction
`ai_tx` = agent initiated transaction

### Audit Dashboard

Every action is logged with details such as agent identity, requested action, policy decision, timestamp, approver, and transaction status.

## Initial Stellar Use Case

Atonima Control is initially being developed for Stellar-powered financial workflows.

Example:

A company uses an AI treasury agent to pay approved vendors through Stellar.

Before the transaction is executed, Atonima checks:

* Is the agent registered?
* Is the recipient approved?
* Is the payment under the allowed limit?
* Does the action require human approval?
* Should the transaction be approved or blocked?

If approved, the transaction proceeds. If not, the action is blocked and logged.

## Long-Term Vision

Atonima is designed to become chain agnostic.

Future integrations may include Stellar, Ethereum, Base, Solana, XRP Ledger, banking APIs, treasury tools, and enterprise AI systems.
