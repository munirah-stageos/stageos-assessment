# stageOS Autonomous Systems Assessment

**Live Demo:** https://munirah-stageos.github.io/stageos-assessment/

**GitHub Repository:** https://github.com/munirah-stageos/stageos-assessment

---

## What Was Built

A fully functional browser-based prototype covering all required assessment areas:

| Module | Description |
|--------|-------------|
| **Dashboard** | Live operational overview with AI alerts and KPIs |
| **Event Management** | Create and manage full event lifecycle |
| **Vendor Operations** | Track vendors, KYC status, and AI risk scores |
| **stagePay Workflow** | Interactive 8-step financing simulation |
| **Approval Workflows** | Human-in-the-loop governance with audit log |
| **AI Agent Framework** | 4 autonomous agents with orchestration logic |
| **Insights & Risk** | AI-powered analytics, fraud detection, compliance |

---

## Diagram 1 — System Architecture (3 Layers)

```
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 1 — FRONTEND (User Interface)                            │
│  Browser-based prototype · GitHub Pages hosted                  │
│  ┌───────────┐ ┌────────┐ ┌─────────┐ ┌──────────┐ ┌────────┐ │
│  │ Dashboard │ │ Events │ │ Vendors │ │ stagePay │ │Approvals│ │
│  └───────────┘ └────────┘ └─────────┘ └──────────┘ └────────┘ │
└─────────────────────────────┬───────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 2 — AI AGENT ORCHESTRATION                               │
│  Four autonomous agents · Human-in-the-loop governance          │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌────────┐ │
│  │  Operations  │ │   Finance    │ │ Vendor Intel │ │Insights│ │
│  │    Agent     │ │    Agent     │ │    Agent     │ │  Agent │ │
│  │              │ │              │ │              │ │        │ │
│  │ · Scheduling │ │ · Validation │ │ · KYC        │ │ · Risk │ │
│  │ · Escalation │ │ · Financing  │ │ · Scoring    │ │ · Fraud│ │
│  │ · Monitoring │ │ · Reconcile  │ │ · Comms      │ │ · PDPL │ │
│  └──────────────┘ └──────────────┘ └──────────────┘ └────────┘ │
└─────────────────────────────┬───────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 3 — DATA & FINANCIAL INFRASTRUCTURE                      │
│  KSA-hosted · PDPL certified · Nylon Finance API                │
│  ┌────────────────┐ ┌────────────────┐ ┌──────────────────────┐ │
│  │ Events database│ │Vendor registry │ │  Nylon Finance API   │ │
│  └────────────────┘ └────────────────┘ └──────────────────────┘ │
└─────────────────────────────┬───────────────────────────────────┘
                              │
                              ▼
              ┌───────────────────────────────┐
              │     HUMAN OVERSIGHT LAYER     │
              │ High-value advances · Fraud   │
              │ alerts · KYC overrides        │
              └───────────────────────────────┘
```

---

## Diagram 2 — stagePay Workflow (8 Steps)

```
ROW 1
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  1 — CONTRACT   │────▶│   2 — OPT-IN    │────▶│ 3 — AI VALIDATES│────▶│   4 — ROUTE     │
│                 │     │                 │     │                 │     │                 │
│ Vendor signs PO │     │ 60% advance     │     │· Contract auth. │     │ To Nylon Finance│
│                 │     │ requested       │     │· Buyer credibil.│     │                 │
│                 │     │                 │     │· Operational risk│    │                 │
│                 │     │                 │     │· Vendor profile │     │                 │
└─────────────────┘     └─────────────────┘     └─────────────────┘     └────────┬────────┘
                                                                                  │
                        ┌─────────────────────────────────────────────────────────┘
                        │ (wrap — continues below)
                        ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  5 — APPROVAL   │────▶│  6 — ADVANCE    │────▶│  7 — SETTLEMENT │────▶│   8 — AUTO-SYNC │
│                 │     │                 │     │                 │     │                 │
│ Workflow        │     │ Vendor receives │     │ Buyer settles   │     │ stageOS updates │
│ executes        │     │ 60% of invoice  │     │ Nylon Finance   │     │ all records     │
│                 │     │ in 20-30 min    │     │ post-event      │     │ automatically   │
└─────────────────┘     └─────────────────┘     └─────────────────┘     └─────────────────┘

RESULT: Vendor receives 60% of invoice within 20-30 minutes
        vs. 2-3 day wait with traditional payment
        Licensed via Nylon Finance (regulated partner)
```

---

## stagePay Workflow — Step 3 Detail (AI Validation)

The AI validates **4 checks** before routing to Nylon Finance:

| Check | What It Does |
|-------|-------------|
| Contract authenticity | Verifies the PO/contract is genuine and unaltered |
| Buyer credibility | Scores the event organiser's payment history and reliability |
| Operational risk | Assesses event timeline risk and vendor mobilisation risk |
| Vendor profile strength | Reviews vendor history, KYC status, and past performance |

All 4 must pass → auto-approved and routed to Nylon Finance
Any failure → escalated to human review

---

## AI Agent Framework

| Agent | Responsibilities |
|-------|-----------------|
| **Operations Agent** | Scheduling, escalation management, operational monitoring |
| **Finance Agent** | Payment validation, financing workflows, reconciliation |
| **Vendor Intelligence Agent** | KYC, supplier scoring, communication workflows |
| **Insights & Risk Agent** | Forecasting, bottleneck detection, fraud alerts |

### Governance — What Requires Human Approval

| Scenario | AI Role | Human Required |
|----------|---------|----------------|
| stagePay — low-value, verified vendor | Full auto-approve | No |
| stagePay — high-value advance | Validate + route | Yes |
| KYC failed vendor | Block + alert | Yes |
| Fraud risk alert | Freeze account | Mandatory |
| Automated communications | Send directly | No |

---

## Technology Choices

**Single-file HTML/CSS/JS** — chosen deliberately:
- Zero dependencies, zero build step
- Runs anywhere: browser, GitHub Pages, any server
- Demonstrates clean architecture without tooling complexity
- Aligns with stageOS's need for rapid iteration

---

## Assumptions Made

1. Nylon Finance integration is simulated (production would use real webhook)
2. KYC validation shown as real-time (production uses async background processing)
3. Risk scores are seeded with realistic data (production pulls from live vendor history)
4. PDPL compliance is architecturally designed in but not enforced at prototype level

---

## AI Usage Disclosure

| Area | AI Tool Used | Human Judgment Applied |
|------|-------------|----------------------|
| System architecture design | Claude (Anthropic) | Yes — reviewed all agent logic and governance rules |
| Workflow logic | Claude (Anthropic) | Yes — validated against real event industry constraints |
| UI/UX implementation | Claude (Anthropic) | Yes — adjusted layout and interactions |
| Business logic (stagePay rules) | Human-led | AI assisted with edge case thinking |

**Where AI should NOT be fully autonomous:**
- Any high-value financing decision
- Fraud alerts and account freezes
- KYC override decisions
- Contract disputes

**What I would automate next:**
- Auto-outreach to replacement vendors when gaps detected
- Nylon Finance API real webhook integration
- Real-time vendor score recalculation after each event

---

## What I Would Build Next (Production Roadmap)

1. **Backend API** — Node.js / FastAPI with PostgreSQL (KSA-hosted)
2. **Real AI agents** — LangChain / Anthropic API for live decision-making
3. **Nylon Finance integration** — Real webhook-based disbursement
4. **stagePassport CRM sync** — Pull vendor profiles from live CRM
5. **Mobile app** — On-site event operations via React Native

---

*Submitted for stageOS Autonomous Systems Assessment*
