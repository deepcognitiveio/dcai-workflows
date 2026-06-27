# Contributing to dcAI Workflows

Thank you for helping grow the dcAI ecosystem! Here's how you can contribute.

---

## Ways to contribute

### 1. Submit a workflow template
The easiest way. If you've built a useful workflow on dcAI, share it with the community.

**Format:** See any file in `/workflows` — JSON with `name`, `description`, `connectors`, `trigger`, and `steps`.

**Steps:**
1. Fork this repo
2. Add your template to `/workflows/your-workflow-name.json`
3. Add a row to the [workflow table](./README.md#sample-workflows) in README.md
4. Open a pull request with a short description of the use case

### 2. Add a connector
Want to see a new connector in dcAI?

- [Open a connector request issue](https://github.com/deepcognitiveio/dcai-workflows/issues/new?template=feature_request.md)
- Or if you've built an adapter, submit it via pull request to `/connectors/`

### 3. Improve documentation
- Fix typos, add examples, clarify steps
- Add a new guide under `/docs/`
- Translate docs to another language

### 4. Report bugs
- Use the [bug report template](https://github.com/deepcognitiveio/dcai-workflows/issues/new?template=bug_report.md)
- Include your AuditLog output if possible

---

## Workflow template format

```json
{
  "name": "Your Workflow Name",
  "description": "One sentence describing what it does.",
  "version": "1.0.0",
  "category": "CRM & Payments",
  "connectors": ["stripe", "hubspot"],
  "trigger": {
    "type": "webhook",
    "source": "stripe",
    "event": "payment_intent.succeeded"
  },
  "steps": [
    {
      "id": "step_1",
      "name": "Step name",
      "type": "transform | connector | condition | log",
      "connector": "hubspot",
      "action": "create_contact",
      "input": {},
      "ai_healing": true
    }
  ],
  "audit_log": true
}
```

**Step types:**
- `transform` — reshape/map data fields
- `connector` — call an external API (Stripe, HubSpot, etc.)
- `condition` — branch based on payload values
- `log` — write to AuditLog

---

## Community guidelines

- Be respectful and constructive
- Don't include real API keys or secrets in templates
- Use placeholder values like `"your_api_key_here"`
- One workflow per pull request

---

## Questions?

- Open a [GitHub Discussion](https://github.com/deepcognitiveio/dcai-workflows/discussions)
- Email: [contact@deepcognitive.io](mailto:contact@deepcognitive.io)
- Try the platform: [flows.deepcognitive.io](https://flows.deepcognitive.io)
