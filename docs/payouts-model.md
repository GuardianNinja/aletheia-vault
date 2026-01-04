# Payouts model

This document describes how payouts (royalties and dividends) are calculated,
scheduled, and used to support sustainable, community-centered economics.

---

## Goals of the payouts model

- Pay inventors fairly and transparently.
- Handle different business models (licenses, franchises, investments).
- Provide predictable payout schedules.
- Use reserves to smooth out volatility when possible.
- Keep the system understandable for both individuals and organizations.

---

## Core payout flows

There are several primary sources of payouts:

1. **Revenue-Share Commercial Licenses**
   - Royalties based on revenue, profit, or usage units.

2. **Franchise Licenses**
   - Multi-tier payouts to:
     - Inventors.
     - Franchise operators.
     - Platform (as fee).

3. **Investor Market Positions**
   - Revenue-share portions directed to investors who funded inventions.

4. **Public Crypto Market Mechanisms (Optional)**
   - On-chain royalties routed by smart contracts.
   - Utility tokens used to represent certain rights or usage.

---

## Calculation model

### 1. Inputs

From each license or contract:

- **Royalty base**
  - Gross revenue.
  - Net revenue.
  - Units sold.
  - Subscription seats.
  - API or usage metrics.

- **Rate**
  - Percentage (e.g., 10%).
  - Per-unit amount (e.g., $0.10 per unit).

- **Frequency**
  - Monthly.
  - Quarterly.
  - Custom (e.g., every two months).

### 2. Processing

1. Licensee uploads or sends usage data:
   - CSV upload.
   - API integration.
   - On-chain usage triggers.

2. System validates data:
   - Basic sanity checks.
   - Anomaly detection (sudden drops or inconsistencies).
   - Cross-references with past trends where possible.

3. Royalty engine computes:
   - Per-license amount owed.
   - Shares for:
     - Inventors.
     - Franchisees (if any).
     - Investors (if applicable).
     - Platform fee.
     - JARVONDIS Reserve contribution (via market-level 2% rule).

---

## Scheduling and distribution

- Each contract specifies its payout schedule.
- The system aggregates all royalties due to each inventor or investor.
- On payout date:
  - Payments are triggered through supported channels:
    - Bank transfers.
    - Payment processors.
    - Optional on-chain payouts.

- Users have a **Payouts Dashboard**:
  - Upcoming payouts.
  - Historical payouts.
  - Breakdown by invention and license.

---

## JARVONDIS Reserve interaction

The **2% weekly reserve mechanism** is applied at the market level:

- From:
  - Investor Market.
  - Franchise Market.
  - Public Crypto Market.

- How:
  - 2% of gross transaction volume each week is routed into the JARVONDIS Reserve.
  - This happens before final distribution of platform fees.

- Use:
  - When payouts would otherwise sharply drop due to external shocks:
    - The reserve can be used to partially stabilize inventor payouts.
  - Governance defines thresholds and rules for when this is allowed.

---

## Long-term sustainability

The payouts model supports sustainability by:

- Encouraging **recurring royalties** rather than one-time sell-offs.
- Allowing **investors** to support inventors and share in long-term success.
- Allowing **franchise operators** to participate in local or sector growth.
- Building a **JARVONDIS Reserve** that:
  - Mitigates risk and volatility.
  - Protects against downturns.
  - Reinforces trust in the system.

The intention is that people who create and people who help grow the ecosystem
can all see clear, fair, and predictable flows of value over time.

---

## Limitations and transparency

- Payouts depend on:
  - Honest reporting by licensees.
  - Economic conditions.
  - Adoption of the platform.

- The system uses:
  - Anomaly detection.
  - Audits (as policy allows).
  - Clear dashboards.

to keep the community informed and to align expectations with reality.

The model is open by design so that it can be questioned, improved, and adapted
by the community it serves.
