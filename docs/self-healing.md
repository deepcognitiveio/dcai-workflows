# How dcAI Self-Healing Works

One of dcAI's core differentiators is its **AI self-healing engine** — workflows that automatically detect, fix, and learn from failures without human intervention.

---

## The problem with traditional iPaaS

In Zapier, MuleSoft, or Boomi — when a workflow step fails:

1. The workflow stops
2. You get an error notification
3. A developer investigates
4. They manually fix the data mapping or field format
5. They re-run the workflow

This can take hours or days. If it's a production payment flow, that means lost revenue.

---

## How dcAI heals automatically

When a step fails in dcAI:

```
Step fails
    ↓
Error captured (payload + error message + connector response)
    ↓
HiveMind RAG queried — "have we seen this error before?"
    ↓
Claude AI analyzes the failure + any matching patterns
    ↓
Fix rule generated ("convert date to ISO 8601 before sending to Salesforce")
    ↓
Fix applied in-memory
    ↓
Step retried automatically
    ↓
Success? → healing pattern saved to HiveMind
Failure? → escalate to human / Slack alert
```

---

## HiveMind RAG memory

Every healing event is stored in **dcAI HiveMind** — a vector database of healing patterns specific to your tenant, plus anonymized cross-tenant patterns.

When the same error occurs again:
- HiveMind retrieves the matching pattern instantly
- No AI call needed — the fix is already known
- Latency: ~50ms vs ~2s for a fresh AI heal

Over time, your dcAI instance becomes smarter about your specific data formats, API quirks, and integration edge cases.

---

## Example: Stripe → HubSpot phone format

**What happened:**
- Stripe sends phone as `7321234567` (10 digits, no country code)
- HubSpot rejects it — expects E.164 format: `+17321234567`

**Without dcAI:** workflow fails, developer manually adds a format step.

**With dcAI:**
1. HubSpot returns `422 Unprocessable Entity`
2. Claude AI identifies: "phone number missing country code prefix"
3. Fix applied: prepend `+1` to 10-digit US numbers
4. HubSpot call retried — succeeds
5. Pattern saved: "For HubSpot phone fields: format as +1XXXXXXXXXX"
6. Next time this runs — HiveMind catches it in 50ms, no AI call needed

---

## AuditLog — every decision is traceable

Every healing decision is logged in **dcAI AuditLog**:

```json
{
  "run_id": "run_abc123",
  "step": "Create HubSpot Contact",
  "status": "healed",
  "error": "Property 'phone' rejected: invalid format",
  "fix_applied": "Reformatted phone from '7321234567' to '+17321234567'",
  "confidence": 0.94,
  "pattern_source": "hivemind",
  "healed_at": "2026-06-24T10:23:41Z"
}
```

Full audit trail for compliance, debugging, and SOC2 readiness.

---

## Try it yourself

1. Sign up at [flows.deepcognitive.io](https://flows.deepcognitive.io)
2. Connect Stripe + HubSpot
3. Enable **"Inject Faults"** in SandboxMode
4. Watch the AI heal in real-time on the live dashboard
