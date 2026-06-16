# Example: Daily Email Triage with AgentMail + Obsidian + Honcho

## Scenario

A user runs a daily email triage routine. The agent:
1. Checks the agent inbox for new emails
2. Categorizes them by priority
3. Logs important items to the Obsidian daily journal
4. Updates Honcho with any new facts about contacts or projects

## Workflow

### Morning: Agent checks email

User asks: "Check my AgentMail inbox for new emails."

Hermes uses the AgentMail SDK to list recent messages:

```python
from agentmail import AgentMail

client = AgentMail(api_key="your-api-key")
messages = client.inboxes.messages.list(inbox_id="your-inbox-id", limit=10)
for msg in messages.messages:
    print(f"From: {msg.from_} - Subject: {msg.subject}")
```

Result: 2 unread emails.
- From: recruiter@company.com - Subject: "Interview request for AI Engineer role"
- From: alerts@service.com - Subject: "Price alert triggered"

### Agent categorizes

Hermes identifies:
- Interview request → URGENT (time-sensitive response needed)
- Service alert → FYI (informational, no action required)

### Agent logs to Obsidian

Hermes creates/updates the daily log:
```markdown
## 2026-06-10

### Email Triage
- 🔴 URGENT: Interview request from recruiter@company.com - AI Engineer role
- 🟢 FYI: Price alert triggered (Service)
```

### Agent updates Honcho

Hermes stores a conclusion about the contact:
```
honcho_conclude: "Recruiter from company.com reached out about AI Engineer role on 2026-06-10"
```

### Agent responds to urgent email

Hermes drafts a reply via AgentMail:

```python
client.inboxes.messages.send(
    inbox_id="your-inbox-id",
    to="recruiter@company.com",
    subject="Re: Interview request for AI Engineer role",
    text="Hi, thanks for reaching out. I'm interested in learning more. What's the best time for a call this week?",
    reply_to="message-id-of-original",
)
```

## Stack Interaction

```
AgentMail (collect email)
    ↓
Hermes Agent (triage, categorize, decide)
    ↓
Obsidian (log to daily journal)  ←  Honcho (update peer/contact memory)
    ↓
AgentMail (send reply)
```

## Why This Works

- **AgentMail** captures email that would otherwise live outside the second brain
- **Hermes** connects all layers with a single tool interface
- **Obsidian** keeps a human-readable daily log
- **Honcho** remembers contacts and context across sessions

Next time the user asks "did that recruiter follow up?", Hermes can search Honcho for the conclusion and check the Obsidian daily log for the timeline.

## Related Pages

- Solution profile: [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md)
- Setup guide: [Hermes + Obsidian + Honcho Setup](../setup-guides/hermes-obsidian-honcho.md)
- Capability: [Data capture](../capabilities/data-capture.md)
- Capability: [Dreaming / consolidation](../capabilities/dreaming-consolidation.md)
