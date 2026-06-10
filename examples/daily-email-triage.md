# Example: Daily Email Triage with AgentMail + Obsidian + Honcho

## Scenario

Alex runs a daily email triage routine. The agent:
1. Checks the agent inbox for new emails
2. Categorizes them by priority
3. Logs important items to the Obsidian daily journal
4. Updates Honcho with any new facts about contacts or projects

## Workflow

### Morning: Agent checks email

Alex asks: "Check my agent inbox for new emails."

Hermes runs:
```bash
python3 ~/.hermes/scripts/agentmail_cli.py triage
```

Result: 2 unread emails.
- From: recruiter@company.com — Subject: "Interview request for AI Engineer role"
- From: alerts@tradingview.com — Subject: "MNQ1 alert triggered"

### Agent categorizes

Hermes identifies:
- Interview request → URGENT (time-sensitive response needed)
- Trading alert → FYI (informational, no action required)

### Agent logs to Obsidian

Hermes creates/updates the daily log:
```markdown
## 2026-06-10

### Email Triage
- 🔴 URGENT: Interview request from recruiter@company.com — AI Engineer role
- 🟢 FYI: MNQ1 alert triggered (TradingView)
```

### Agent updates Honcho

Hermes stores a conclusion about the contact:
```
honcho_conclude: "Recruiter from company.com reached out about AI Engineer role on 2026-06-10"
```

### Agent responds to urgent email

Hermes drafts a reply via AgentMail:
```bash
python3 ~/.hermes/scripts/agentmail_cli.py reply hermes876@agentmail.to "<message_id>" \
  "Hi, thanks for reaching out. I'm interested in learning more. What's the best time for a call this week?"
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

Next time Alex asks "did that recruiter follow up?", Hermes can search Honcho for the conclusion and check the Obsidian daily log for the timeline.

## Related Pages

- Solution profile: [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md)
- Setup guide: [Hermes + Obsidian + Honcho Setup](hermes-obsidian-honcho.md)
- Capability: [Data capture](../capabilities/data-capture.md)
- Capability: [Dreaming / consolidation](../capabilities/dreaming-consolidation.md)
