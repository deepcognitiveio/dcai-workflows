<div align="center">

<img src="./assets/logo.svg" alt="dcAI Workflow OS" width="320"/>

<br/>

**The AI-native iPaaS — self-healing workflows, 60+ connectors, RAG memory**

<br/>

[![Try Free](https://img.shields.io/badge/Try%20Free-flows.deepcognitive.io-6366f1?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyek0xMCAxN2wtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTkgMS40MSAxLjQxTDEwIDE3eiIvPjwvc3ZnPg==)](https://flows.deepcognitive.io)
[![Website](https://img.shields.io/badge/Website-deepcognitive.io-f59e0b?style=for-the-badge)](https://deepcognitive.io)
[![API Docs](https://img.shields.io/badge/API%20Docs-api.deepcognitive.io-4ade80?style=for-the-badge)](https://api.deepcognitive.io/docs)
[![License: MIT](https://img.shields.io/badge/License-MIT-white?style=for-the-badge)](LICENSE)

<br/>

[![GitHub Stars](https://img.shields.io/github/stars/deepcognitiveio/dcai-workflows?style=social)](https://github.com/deepcognitiveio/dcai-workflows/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/deepcognitiveio/dcai-workflows?style=social)](https://github.com/deepcognitiveio/dcai-workflows/network/members)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](CONTRIBUTING.md)
[![Contributors](https://img.shields.io/github/contributors/deepcognitiveio/dcai-workflows)](https://github.com/deepcognitiveio/dcai-workflows/graphs/contributors)

</div>

---

## What is dcAI Workflow OS?

**dcAI** is an AI-native integration platform that connects your apps, APIs, and data — and **automatically heals broken workflows** using Claude AI.

Unlike Zapier, Boomi, or MuleSoft — dcAI doesn't just execute workflows. It **thinks**.

```
Traditional iPaaS:   Step fails → Error notification → Developer fixes manually → Re-run
dcAI Workflow OS:    Step fails → AI diagnoses → Fix applied in real-time → Run continues ✓
```

> **"The first iPaaS that fixes itself."**

---

## Platform features

| Feature | Description | Status |
|---|---|---|
| **dcAI Flow Builder** | Visual drag-and-drop workflow builder | ✅ Live |
| **dcAI ConnectForge** | 60+ pre-built connectors | ✅ Live |
| **dcAI HiveMind** | RAG memory — healing patterns persist across runs | ✅ Live |
| **dcAI AutoTest** | AI-generated test cases + UAT sign-off | ✅ Live |
| **dcAI SandboxMode** | Safe testing with mock APIs + fault injection | ✅ Live |
| **dcAI AuditLog** | Full run history with AI decision trail | ✅ Live |
| **dcAI FlowKit** | 50+ ready-to-deploy workflow templates | ✅ Live |
| **dcAI Webhooks** | Inbound webhook receiver for any source | ✅ Live |
| **dcAI PulseGuard** | Real-time monitoring + alerting | 🔜 Soon |
| **dcAI Scheduler** | Time-triggered workflows | 🔜 Soon |

---

## Quick start (60 seconds)

```bash
# 1. Sign up free — no credit card needed
open https://flows.deepcognitive.io

# 2. Connect your first integration via API
curl -X POST https://api.deepcognitive.io/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email": "you@company.com", "password": "yourpassword"}'

# 3. List your connectors
curl https://api.deepcognitive.io/api/connectors \
  -H "Authorization: Bearer YOUR_TOKEN"
```

Or pick a template from [`/workflows`](./workflows) and deploy in one click from the platform.

---

## Workflow templates

| Template | Connectors | Category |
|---|---|---|
| [Stripe → HubSpot sync](./workflows/stripe-to-hubspot.json) | Stripe, HubSpot | CRM & Payments |
| [Webhook → Multi-destination router](./workflows/webhook-trigger.json) | Webhook, Slack, HubSpot | Webhooks |
| [New signup → Full onboarding](./workflows/new-signup-sequence.json) | dcAI, HubSpot, Jira, Slack | Onboarding |
| [Workflow failure → Slack alert](./workflows/slack-alert-on-failure.json) | dcAI, Slack | Monitoring |

**👉 [Browse all templates →](./workflows)**

**Have a workflow to share?** [Submit a pull request](CONTRIBUTING.md) — we'd love to include it.

---

## How AI self-healing works

```
Workflow step fails
        │
        ▼
┌─────────────────────┐
│  dcAI HiveMind RAG  │  ← "Have we seen this error before?"
│  queries memory     │
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│   Claude AI         │  ← Analyzes error + context
│   diagnoses error   │
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│   Fix applied       │  ← In-memory, zero downtime
│   Step retried      │
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│   Pattern saved     │  ← Never fails the same way again
│   to HiveMind       │
└─────────────────────┘
```

[Read the full self-healing guide →](./docs/self-healing.md)

---

## Connector catalog

**60+ connectors across every category:**

<table>
<tr>
<td valign="top">

**CRM & Sales**
- Salesforce
- HubSpot
- Pipedrive
- Close CRM

**Payments**
- Stripe
- PayPal
- Square
- QuickBooks

**Communication**
- Slack
- Gmail
- Twilio
- SendGrid

</td>
<td valign="top">

**ERP**
- SAP
- NetSuite
- Oracle ERP
- MS Dynamics

**E-commerce**
- Shopify
- WooCommerce
- Magento
- BigCommerce

**Developer Tools**
- GitHub
- Jira
- Linear
- PagerDuty

</td>
<td valign="top">

**Data & Databases**
- PostgreSQL
- MySQL
- MongoDB
- Snowflake

**AI & ML**
- Claude (Anthropic)
- OpenAI
- Pinecone
- Weaviate

**Productivity**
- Google Sheets
- Notion
- Asana
- Monday.com

</td>
</tr>
</table>

[See full connector catalog →](./connectors/README.md)

---

## Contribute

**dcAI is community-powered.** Here's how to get involved:

### 🔧 Submit a workflow template
Built something useful? Share it with the community.
```bash
git clone https://github.com/deepcognitiveio/dcai-workflows
cp connectors/TEMPLATE.json workflows/your-workflow.json
# Fill in the template, open a PR
```

### 🔌 Request or build a connector
Missing a connector? [Open a request →](https://github.com/deepcognitiveio/dcai-workflows/issues/new?template=feature_request.md)

Want to build one? Use the [connector template](./connectors/TEMPLATE.json) and submit a PR.

### 💬 Join the discussion
- [GitHub Discussions](https://github.com/deepcognitiveio/dcai-workflows/discussions) — questions, ideas, feedback
- [Open an issue](https://github.com/deepcognitiveio/dcai-workflows/issues) — bug reports, feature requests

### ⭐ Star this repo
Helps other developers find dcAI. Takes 1 second.

[**Read the full contribution guide →**](CONTRIBUTING.md)

---

## Pricing

| Plan | Price | Runs/month | Connectors |
|---|---|---|---|
| **Sandbox** | Free forever | 100 | 5 |
| **Builder** | $149/mo | 5,000 | 10 |
| **Scale** | $499/mo | 50,000 | Unlimited |
| **Enterprise** | Custom | Unlimited | Unlimited + on-prem |

[Start free — no credit card required →](https://flows.deepcognitive.io)

---

## API reference

Full REST API with interactive docs at [api.deepcognitive.io/docs](https://api.deepcognitive.io/docs)

[Quickstart guide →](./docs/api-quickstart.md)

---

## Roadmap

- [ ] Python SDK
- [ ] Node.js SDK
- [ ] dcAI PulseGuard — real-time monitoring
- [ ] dcAI Scheduler — time-triggered workflows
- [ ] dcAI MapStudio — visual data mapper
- [ ] dcAI HumanLoop — human-in-the-loop approvals
- [ ] AWS / Azure Marketplace listing

**Vote on features or suggest new ones** → [GitHub Discussions](https://github.com/deepcognitiveio/dcai-workflows/discussions)

---

<div align="center">

**Built by [Deep Cognitive LLC](https://deepcognitive.io)**

[Website](https://deepcognitive.io) · [Platform](https://flows.deepcognitive.io) · [API Docs](https://api.deepcognitive.io/docs) · [contact@deepcognitive.io](mailto:contact@deepcognitive.io)

<br/>

*If dcAI saves you time, give us a ⭐ — it helps other developers find us.*

</div>
