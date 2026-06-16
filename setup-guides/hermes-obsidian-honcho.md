# Setup Guide: Hermes Agent + Obsidian + Honcho

## Goal

Get a local-first second brain running with:
- **Obsidian** as the human-owned knowledge vault
- **Honcho** as the agent memory layer (peer cards, conclusions, semantic search)
- **Hermes Agent** as the connecting runtime
- **AgentMail** for email context capture

**Target user**: Technical operator comfortable with CLI, Python, and PostgreSQL.

---

## Architecture: Local vs Hosted Components

This stack combines locally-run components with hosted services. Understand the boundary before starting:

| Component | Runs locally | Requires hosted account/service |
|-----------|-------------|-------------------------------|
| Obsidian vault | Yes: local Markdown files | No |
| Hermes Agent gateway | Yes: local process | No (but requires model API key, e.g. OpenRouter) |
| Honcho memory layer | Yes: self-hosted FastAPI + PostgreSQL + Redis | Optional: managed Honcho service is an alternative to self-hosting |
| AgentMail inbox | No: email is received and stored on AgentMail servers | Yes: AgentMail account and API key required |

Core knowledge (Obsidian vault) and agent runtime (Hermes) run on your hardware. Honcho can be self-hosted or used as a managed service. AgentMail is a hosted email API, and emails pass through AgentMail infrastructure.

---

## Prerequisites

| Component | Install |
|-----------|---------|
| macOS | 15.x (other platforms supported; see [Hermes docs](https://hermes-agent.nousresearch.com/docs/getting-started/installation)) |
| Homebrew | `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` |
| PostgreSQL 16+ | `brew install postgresql@16` (only needed for self-hosted Honcho) |
| Redis | `brew install redis` (only needed for self-hosted Honcho) |
| Hermes Agent | `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash` |
| Obsidian | Download from obsidian.md |

---

## Step 1: Start PostgreSQL and Redis

```bash
# Start services
brew services start postgresql@16
brew services start redis

# Verify
psql postgres -c "SELECT 1"
redis-cli ping  # should return PONG
```

---

## Step 2: Install and Configure Honcho

Honcho can be self-hosted (local FastAPI server) or used via the managed service. Both paths require an API key.

```bash
# Install Honcho SDK
pip3 install honcho-ai

# Verify the SDK works
python3 -c "
from honcho import Honcho
client = Honcho(api_key='your-api-key')
print('Honcho client created successfully')
"
```

**Get an API key:**
- Managed service: sign up at https://app.honcho.dev and get an API key from the dashboard
- Self-hosted: follow the [Honcho self-hosting guide](https://honcho.dev/docs/v3/contributing/self-hosting), then configure Hermes to point at your instance

**Configure Hermes to use Honcho:**
```bash
hermes memory setup   # select "honcho", enter your base URL
```

Or create `~/.hermes/honcho.json`:
```json
{
  "baseUrl": "http://localhost:8000",
  "hosts": {
    "hermes": {
      "enabled": true,
      "aiPeer": "hermes",
      "peerName": "your-name",
      "workspace": "hermes"
    }
  }
}
```

For self-hosted use with persistent storage, configure PostgreSQL:

```bash
# Create database
createdb honcho

# Set connection string
export HONCHO_DATABASE_URL="postgresql://localhost:5432/honcho"
```

See the [Honcho docs](https://honcho.dev/docs/v3/documentation/introduction/overview) and [Hermes + Honcho integration guide](https://honcho.dev/docs/v3/guides/integrations/hermes) for details.

---

## Step 3: Install and Configure Hermes Agent

```bash
# Install (macOS / Linux / WSL2)
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash

# Reload shell, then verify
source ~/.zshrc
hermes --version
```

After install, run the setup wizard:
```bash
hermes setup   # full setup wizard
```

Or use the fastest path with Nous Portal (one OAuth covers model + tool gateway):
```bash
hermes setup --portal
```

See the [Hermes Agent installation docs](https://hermes-agent.nousresearch.com/docs/getting-started/installation) for all platforms and options.

---

## Step 4: Set Up Obsidian Vault

```bash
# Create vault directory (or use existing)
mkdir -p ~/Documents/Obsidian\ Vault

# Open in Obsidian: "Open folder as vault" → select the directory
```

Create the vault structure:

```bash
cd ~/Documents/Obsidian\ Vault
mkdir -p entities concepts comparisons queries shared/handoffs shared/outputs _archive
```

Create `SCHEMA.md` (vault conventions), `index.md` (content catalog), and `log.md` (action log). See the [Obsidian/Logseq solution profile](../solutions/obsidian-logseq.md) for schema guidance.

---

## Step 5: Configure AgentMail

AgentMail is a hosted email API. You need an account and API key.

```bash
# Install AgentMail SDK
pip3 install agentmail

# Sign up at https://console.agentmail.to/ and create an inbox
# Generate an API key from the console
```

Verify the SDK works using the [AgentMail quickstart](https://docs.agentmail.to/quickstart):

```python
from agentmail import AgentMail

client = AgentMail(api_key="your-api-key")

# Create an inbox
inbox = client.inboxes.create(username="hello", domain="agentmail.to")
print(f"Inbox created: {inbox.inbox_id}")

# Send a test email
client.inboxes.messages.send(
    inbox.inbox_id,
    to="your-email@example.com",
    subject="Test from setup guide",
    text="AgentMail is working."
)
```

See the [AgentMail docs](https://docs.agentmail.to/) for full API reference, webhooks, and WebSocket setup.

---

## Step 6: Verify the Full Stack

### 6a. Honcho memory works

Ask Hermes: "Remember that I prefer Python and work in fintech."

Then ask: "What do you know about my preferences?"

Hermes should query Honcho and return the stored fact.

### 6b. Obsidian vault is accessible

Ask Hermes: "Create a page in my Obsidian vault called 'Test Page' with the content 'Hello from Hermes.'"

Verify the file exists: `ls ~/Documents/Obsidian\ Vault/`

### 6c. AgentMail works

Send a test email from your personal email to the AgentMail inbox you created in Step 5.

Ask Hermes: "Check my AgentMail inbox for new emails."

Hermes should list the test email. See the [AgentMail quickstart](https://docs.agentmail.to/quickstart) for how to receive and list messages via the SDK.

---

## Known Failure Modes

| Problem | Fix |
|---------|-----|
| Honcho can't connect to PostgreSQL | Verify `HONCHO_DATABASE_URL` is set and `createdb honcho` was run |
| Redis connection refused | `brew services restart redis` |
| Hermes can't find Honcho tools | Run `hermes memory setup` and select "honcho" |
| AgentMail 403 errors | Verify API key has permissions at console.agentmail.to |
| Obsidian vault not found | Open the vault folder in Obsidian via "Open folder as vault" |

---

## Setup Time Estimate

| Step | Time |
|------|------|
| PostgreSQL + Redis | 5 min |
| Honcho | 10 min |
| Hermes Agent | 10 min |
| Obsidian vault | 15 min |
| AgentMail | 10 min |
| Verification | 10 min |
| **Total** | **~60 min** |

---

## Sources

- Hermes Agent docs: https://hermes-agent.nousresearch.com/docs
- Hermes Agent installation: https://hermes-agent.nousresearch.com/docs/getting-started/installation
- Hermes Agent + Honcho integration: https://honcho.dev/docs/v3/guides/integrations/hermes
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Honcho quickstart: https://honcho.dev/docs/v3/documentation/introduction/quickstart
- Obsidian: https://obsidian.md/
- AgentMail: https://agentmail.to/
- AgentMail quickstart: https://docs.agentmail.to/quickstart
