# Architecture

This document describes the high-level architecture of Aletheia Vault.

---

## Core services

- **Auth & Identity Service**
  - User registration, login, and profile management.
  - Role-based and attribute-based access control (RBAC/ABAC).
  - Organization linking (companies, labs, schools).

- **Invention Registry Service**
  - Accepts invention submissions with metadata and attachments.
  - Timestamps and hashes records, storing digests in a tamper-evident ledger.
  - Handles visibility settings and version history.

- **Metadata & Search Service**
  - Indexes inventions for search and discovery.
  - Supports filters by domain, license, stage, and more.
  - Powers lineage and evolution views.

- **Licensing & Contracts Service**
  - Manages license templates and contract parameters.
  - Orchestrates request → negotiate → accept workflows.
  - Stores signed license artifacts; optionally mirrors terms in smart contracts.

- **Dividend & Payments Service**
  - Receives usage reports from licensees (manual or via API).
  - Computes royalties according to contract terms.
  - Prepares payout schedules and routes payments to inventors.

- **Investor, Franchise, and Public Crypto Market Services**
  - Provide specialized flows and data models for each market type.
  - Integrate with licensing and payouts.
  - Forward a 2% share of weekly gross flows to the JARVONDIS Reserve.

- **Governance & Policy Engine**
  - Applies content and usage policies.
  - Manages dispute resolution workflows.
  - Supports governance council decisions and voting.

---

## Data storage

- **Primary Relational Database**
  - Users, organizations, inventions, licenses, payouts, market transactions.

- **Object Storage**
  - Large files such as drawings, diagrams, supporting documents.

- **Tamper-Evident Ledger**
  - Append-only store of invention record hashes and key state changes.
  - Can be anchored periodically to a public blockchain.

- **Analytics & Logs**
  - Operational metrics, usage stats, sandbox hardening metrics.

---

## Security Diamond Firewall

A layered approach:

- **Network Edge**
  - API gateway, WAF, TLS, rate limiting.

- **Application Layer**
  - RBAC/ABAC, input validation, secure session handling.

- **Data Layer**
  - Encryption at rest, field-level encryption for sensitive fields, tamper-evident ledger.

- **Governance Layer**
  - Audit logs, external audits, transparent incident reporting.

See `security-diamond-firewall.md` for details.

---

## Markets and flows

- **Investor Market**
  - Inventions can be listed for funding.
  - Investors can purchase revenue-share positions, recorded as digital contracts.
  - Transactions flow through the licensing and payouts systems.

- **Franchise Market**
  - Regional and sector-specific rights based on franchise licenses.
  - Multi-tier royalty routing (inventor, franchisee, platform).

- **Public Crypto Market**
  - Optional layer with utility tokens and smart-contract-enforced licenses.
  - Focused on transparency and automation rather than speculation.

Each market contributes 2% of weekly gross transaction volume to the JARVONDIS Reserve.

---

## JARVONDIS Reserve integration

- Weekly batch job:
  - Aggregates gross flows from all three markets.
  - Calculates 2% reserve contribution.
  - Credits the JARVONDIS Reserve account in the accounting system.
  - Optionally triggers on-chain transfers to a reserve contract address.

See `jarvondis-reserve.md` and `sandbox-hardening-report.md` for reserve behavior and simulations.
