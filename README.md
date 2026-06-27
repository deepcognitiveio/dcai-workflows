# dcAI Workflow OS

> **The AI-native iPaaS platform** — self-healing workflows, 60+ connectors, RAG memory, and zero manual intervention.

[![Try Free](https://img.shields.io/badge/Try%20Free-flows.deepcognitive.io-6366f1?style=for-the-badge)](https://flows.deepcognitive.io)
[![Website](https://img.shields.io/badge/Website-deepcognitive.io-f59e0b?style=for-the-badge)](https://deepcognitive.io)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## What is dcAI?

dcAI Workflow OS is an **AI-native integration platform** that connects your apps, APIs, and data sources — and automatically heals broken workflows using Claude AI.

Unlike traditional iPaaS (Zapier, Boomi, MuleSoft), dcAI:

- **Self-heals** — AI detects and fixes data format mismatches in real-time
- **Learns** — RAG memory stores healing patterns so the same error never breaks twice
- **Audits** — every run is logged with full AuditLog trail
- **Tests itself** — AutoTest generates and runs test cases automatically

---

## Platform features

| Feature | Description |
|---|---|
| **dcAI Flow Builder** | Visual drag-and-drop workflow builder |
| **dcAI ConnectForge** | 60+ pre-built connectors (Stripe, HubSpot, SAP, Salesforce, Shopify...) |
| **dcAI HiveMind** | RAG-powered memory — healing patterns persist across runs |
| **dcAI AutoTest** | AI-generated test cases + UAT sign-off |
| **dcAI SandboxMode** | Safe testing environment with mock APIs |
| **dcAI AuditLog** | Full run history with AI decision trail |
| **dcAI FlowKit** | 50+ ready-to-deploy workflow templates |
| **dcAI Webhooks** | Inbound webhook receiver for any source |

---

## Quick start

1. **Sign up free** at [flows.deepcognitive.io](https://flows.deepcognitive.io)
2. Connect your first integration (Stripe, HubSpot, Slack, etc.)
3. Pick a template from [dcAI FlowKit](https://flows.deepcognitive.io/flowkit.html)
4. Deploy in one click

No credit card required. Sandbox plan is free forever.

---

## Sample workflows

Browse the [`/workflows`](./workflows) directory for ready-to-use templates:

| Workflow | Description |
|---|---|
| [`stripe-to-hubspot.json`](./workflows/stripe-to-hubspot.json) | Sync Stripe payments → HubSpot CRM contacts |
| [`webhook-trigger.json`](./workflows/webhook-trigger.json) | Inbound webhook → process + route to any destination |
| [`slack-alert-on-failure.json`](./workflows/slack-alert-on-failure.json) | Monitor workflow runs → Slack alert on failure |
| [`new-signup-sequence.json`](./workflows/new-signup-sequence.json) | New user signup → onboarding email + CRM + Jira ticket |

---

## Connector catalog

dcAI supports 60+ connectors across CRM, payments, communication, ERP, and data:

**CRM & Sales:** Salesforce, HubSpot, Pipedrive, Close  
**Payments:** Stripe, PayPal, Square  
**Communication:** Slack, Gmail, Twilio, SendGrid  
**ERP:** SAP, NetSuite, Oracle  
**E-commerce:** Shopify, WooCommerce, Magento  
**Data:** PostgreSQL, MySQL, MongoDB, Snowflake  
**Dev tools:** GitHub, Jira, Linear, PagerDuty  
**AI:** Claude, OpenAI, Pinecone, Weaviate  

[See full connector list →](./connectors/README.md)

---

## API reference

dcAI exposes a REST API for programmatic workflow management.

**Base URL:** `https://api.deepcognitive.io`

```bash
# Authenticate
curl -X POST https://api.deepcognitive.io/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email": "you@company.com", "password": "yourpassword"}'

# List your connectors
curl https://api.deepcognitive.io/api/connectors \
  -H "Authorization: Bearer YOUR_TOKEN"

# Trigger a webhook
curl -X POST https://api.deepcognitive.io/api/webhooks/stripe/YOUR_TENANT_ID \
  -H "Content-Type: application/json" \
  -d '{"type": "payment_intent.succeeded", "data": {...}}'
```

[Full API docs →](./docs/api-quickstart.md)

---

## How AI self-healing works

When a workflow step fails (wrong data format, missing field, API error), dcAI:

1. Captures the error payload
2. Sends it to Claude AI with context from HiveMind RAG memory
3. Claude generates a fix rule
4. The fix is applied in real-time and the step retried
5. The healing pattern is stored so it never fails the same way again

[Learn more →](./docs/self-healing.md)

---

## Pricing

| Plan | Price | Runs/month | Connectors |
|---|---|---|---|
| Sandbox | Free | 100 | 5 |
| Builder | $149/mo | 5,000 | 10 |
| Scale | $499/mo | 50,000 | Unlimited |
| Enterprise | Custom | Unlimited | Unlimited + on-prem |

[Start free →](https://flows.deepcognitive.io)

---

## Contributing

This repo contains public workflow templates and documentation. To contribute a workflow template:

1. Fork this repo
2. Add your template to `/workflows` following the [template format](./docs/template-format.md)
3. Open a pull request

---

## Links

- **Platform:** [flows.deepcognitive.io](https://flows.deepcognitive.io)
- **Website:** [deepcognitive.io](https://deepcognitive.io)
- **API docs:** [api.deepcognitive.io/docs](https://api.deepcognitive.io/docs)
- **Email:** [contact@deepcognitive.io](mailto:contact@deepcognitive.io)

---

*Built by [Deep Cognitive LLC](https://deepcognitive.io)*
