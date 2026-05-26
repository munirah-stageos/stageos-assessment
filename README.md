# stageOS Autonomous Systems Assessment
### Submitted by: Munirah | May 2026

---

## Overview

This prototype demonstrates an AI-powered operational system for **stageOS** and **stagePay** — a financial infrastructure layer embedded directly within event management workflows.

**Live Demo:** [View on GitHub Pages](https://munirah-stageos.github.io/stageos-assessment/)

---

## What Was Built

A fully functional browser-based prototype covering all required assessment areas:

| Module | Description |
|--------|-------------|
| **Dashboard** | Live operational overview with AI alerts and KPIs |
| **Event Management** | Create and manage full event lifecycle |
| **Vendor Operations** | Track vendors, KYC status, and AI risk scores |
| **stagePay Workflow** | Interactive step-by-step financing simulation |
| **Approval Workflows** | Human-in-the-loop governance with audit log |
| **AI Agent Framework** | 4 autonomous agents with orchestration logic |
| **Insights & Risk** | AI-powered analytics, fraud detection, compliance |

---

## stagePay Workflow (Core Feature)

The prototype simulates the complete 8-step financing flow:

1. Vendor signs contract / accepts PO
2. Vendor opts into stagePay
3. **AI validates**: contract authenticity · buyer credibility · operational risk · vendor profile
4. stagePay routes request to Nylon Finance (licensed partner)
5. Approval workflow executes (human-in-the-loop for amounts > SAR 50K)
6. Vendor receives 60% advance within ~20–30 minutes
7. Buyer settles full amount with Nylon Finance post-event
8. stageOS auto-updates all operational and financial records

---

## AI Agent Framework

Four agents work together in an orchestrated system:

- **Operations Agent** — Scheduling, escalation management, stakeholder comms
- **Finance Agent** — Invoice validation, financing workflows, reconciliation
- **Vendor Intelligence Agent** — KYC, supplier scoring, onboarding
- **Insights & Risk Agent** — Forecasting, fraud detection, PDPL compliance

### Governance: What Requires Human Approval

| Scenario | AI Role | Human Required |
|----------|---------|----------------|
| stagePay < SAR 50K, verified vendor | Full auto-approve | No |
| stagePay > SAR 50K | Validate + route | Yes |
| KYC Failed Vendor | Block + alert | Yes |
| Fraud Risk Alert | Freeze account | Mandatory |
| Automated communications | Send directly | No |

---

## Technology Choices & Reasoning

**Single-file HTML/CSS/JS** — chosen deliberately:
- Zero dependencies, zero build step
- Runs anywhere: browser, GitHub Pages, any server
- Demonstrates clean architecture without tooling complexity
- Aligns with stageOS's need for rapid iteration

**No framework** — vanilla JS handles all state and interactivity cleanly at this prototype scale. A production system would use React + a backend API.

---

## Assumptions Made

1. Nylon Finance integration is simulated via mock API responses (production would use real webhook)
2. KYC validation timing shown as real-time but production uses async background processing
3. Risk scores are seeded with realistic data; production pulls from live vendor history
4. PDPL compliance is architecturally designed in (data residency, consent) but not enforced at the prototype level

---

## AI Usage Disclosure

| Area | AI Tool Used | Human Judgment Applied |
|------|-------------|----------------------|
| System architecture design | Claude (Anthropic) | Yes — reviewed all agent logic and governance rules |
| Workflow logic | Claude (Anthropic) | Yes — validated against real event industry constraints |
| UI/UX implementation | Claude (Anthropic) | Yes — adjusted layout and interactions |
| Business logic (stagePay rules) | Human-led | AI assisted with edge case thinking |

**Where AI should NOT be fully autonomous:**
- Any financing decision above SAR 50K
- Fraud alerts and account freezes
- KYC override decisions
- Contract disputes

**What I would automate next:**
- Auto-outreach to replacement vendors when gaps detected
- Nylon Finance API integration (real webhook vs simulation)
- Real-time vendor score recalculation after each event

---

## What I Would Build Next (Production Roadmap)

1. **Backend API** — Node.js / FastAPI with PostgreSQL (KSA-hosted)
2. **Real AI agents** — LangChain / Anthropic API for live decision-making
3. **Nylon Finance integration** — Real webhook-based disbursement
4. **stagePassport CRM sync** — Pull vendor profiles from live CRM
5. **Mobile app** — On-site event operations via React Native

---

*Submitted for stageOS Autonomous Systems Assessment · Deadline: June 4, 2026*
