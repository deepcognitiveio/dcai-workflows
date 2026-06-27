# dcAI API Quickstart

**Base URL:** `https://api.deepcognitive.io`  
**Auth:** Bearer token (JWT)  
**Docs:** [api.deepcognitive.io/docs](https://api.deepcognitive.io/docs)

---

## Authentication

### Register
```bash
curl -X POST https://api.deepcognitive.io/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "you@company.com",
    "password": "yourpassword",
    "name": "Your Name",
    "company": "Your Company",
    "agreed_tos": true
  }'
```

### Login
```bash
curl -X POST https://api.deepcognitive.io/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email": "you@company.com", "password": "yourpassword"}'

# Response
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

Use this token in all subsequent requests:
```bash
export DCAI_TOKEN="your_jwt_token_here"
```

---

## Connectors

### List connected integrations
```bash
curl https://api.deepcognitive.io/api/connectors \
  -H "Authorization: Bearer $DCAI_TOKEN"
```

### Connect an integration
```bash
curl -X POST https://api.deepcognitive.io/api/connectors \
  -H "Authorization: Bearer $DCAI_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "connector": "hubspot",
    "api_key": "your_hubspot_api_key"
  }'
```

---

## Webhooks

### Register a webhook endpoint
```bash
curl -X POST https://api.deepcognitive.io/api/webhooks/register \
  -H "Authorization: Bearer $DCAI_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "source": "stripe",
    "signing_secret": "whsec_your_stripe_webhook_secret"
  }'

# Response — use this URL in your Stripe dashboard
{
  "webhook_url": "https://api.deepcognitive.io/api/webhooks/stripe/YOUR_TENANT_ID",
  "endpoint_id": "wh_abc123"
}
```

### Inbound webhook receiver
```bash
# This is the URL you give to Stripe / HubSpot / GitHub etc.
POST https://api.deepcognitive.io/api/webhooks/{source}/{tenant_id}

# Example: Stripe calls this automatically on payment
POST https://api.deepcognitive.io/api/webhooks/stripe/YOUR_TENANT_ID
```

---

## RAG / HiveMind

### Save a healing pattern
```bash
curl -X POST https://api.deepcognitive.io/api/rag/save \
  -H "Authorization: Bearer $DCAI_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "root_cause": "HubSpot expects phone in E.164 format (+1XXXXXXXXXX)",
    "fix_rule": "Prepend +1 to 10-digit US phone numbers before sending to HubSpot"
  }'
```

### Query healing patterns
```bash
curl "https://api.deepcognitive.io/api/rag/query?q=phone+format" \
  -H "Authorization: Bearer $DCAI_TOKEN"
```

---

## Account & Quota

### Get your profile and current plan
```bash
curl https://api.deepcognitive.io/api/auth/me \
  -H "Authorization: Bearer $DCAI_TOKEN"
```

### Check quota usage
```bash
curl https://api.deepcognitive.io/api/quota \
  -H "Authorization: Bearer $DCAI_TOKEN"

# Response
{
  "plan": "builder",
  "runs_used": 342,
  "runs_limit": 5000,
  "reset_date": "2026-07-01"
}
```

---

## Rate limits

| Plan | Requests/min | Runs/month |
|---|---|---|
| Sandbox | 10 | 100 |
| Builder | 30 | 5,000 |
| Scale | 100 | 50,000 |
| Enterprise | Custom | Unlimited |

---

## SDKs

Coming soon: Python, Node.js, Go SDKs.

In the meantime, use the REST API directly or [open an issue](https://github.com/deepcognitiveio/dcai-workflows/issues) to request an SDK.

---

**Full interactive docs:** [api.deepcognitive.io/docs](https://api.deepcognitive.io/docs)
