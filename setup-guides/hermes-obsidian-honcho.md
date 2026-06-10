# Setup Guide: Hermes Agent + Obsidian + Honcho

## Goal

Get a fully local second brain running with:
- **Obsidian** as the human-owned knowledge vault
- **Honcho** as the agent memory layer (peer cards, conclusions, semantic search)
- **Hermes Agent** as the connecting runtime
- **AgentMail** for email context capture

**Target user**: Technical operator comfortable with CLI, Python, and PostgreSQL.

**Tested on**: macOS (Apple M1, 16 GB RAM), Python 3.11 (Hermes venv)

---

## Prerequisites

| Component | Version tested | Install |
|-----------|---------------|---------|
| macOS | 15.x | — |
| Homebrew | 4.x | `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` |
| PostgreSQL 16+ | 16.x | `brew install postgresql@16` |
| Redis | 7.x | `brew install redis` |
| Python 3.11 | 3.11.x | `brew install python@3.11` |
| Hermes Agent | 0.16.0 | `pip install hermes-agent` |
| Obsidian | 1.7+ | Download from obsidian.md |

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

```bash
# Install Honcho SDK
pip3 install honcho-ai

# Sign up at https://honcho.dev and create a workspace
# Get your API key from the dashboard

# Verify the SDK works
python3 -c "
from honcho import Honcho
client = Honcho(api_key='your-api-key', environment='production')
print('Honcho client created successfully')
"
```

For production use with persistent storage, configure PostgreSQL:

```bash
# Create database
createdb honcho

# Set connection string
export HONCHO_DATABASE_URL="postgresql://localhost:5432/honcho"
```

---

## Step 3: Install and Configure Hermes Agent

```bash
# Install
pip install hermes-agent

# Initialize config
hermes setup

# Verify
hermes --version
```

Configure Honcho integration in `~/.hermes/config.yaml`:

```yaml
memory:
  provider: honcho
  memory_enabled: true
  user_profile_enabled: true

honcho:
  # Uses HONCHO_DATABASE_URL env var or defaults to local storage
```

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

## Step 5: Install and Configure AgentMail

```bash
# Install AgentMail SDK (can be in system Python or a separate venv)
pip3 install agentmail

# Sign up at https://console.agentmail.to/ and create an inbox
# Generate an API key from the console

# Store key in Hermes config
# Edit ~/.hermes/config.yaml:
#   agentmail:
#     api_key: "am_us_..."

# Verify
python3 -c "
from agentmail import AgentMail
import yaml
with open('/Users/saint/.hermes/config.yaml') as f:
    cfg = yaml.safe_load(f)
client = AgentMail(api_key=cfg['agentmail']['api_key'])
print(client.inboxes.list())
"
```

---

## Step 6: Verify the Full Stack

### 6a. Honcho memory works

Ask Hermes: "Remember that my name is Alex and I live in Jamaica."

Then ask: "What do you know about me?"

Hermes should query Honcho and return the stored fact.

### 6b. Obsidian vault is accessible

Ask Hermes: "Create a page in my Obsidian vault called 'Test Page' with the content 'Hello from Hermes.'"

Verify the file exists: `ls ~/Documents/Obsidian\ Vault/`

### 6c. AgentMail works

Send a test email from your personal email to your agent inbox.

Ask Hermes: "Check my agent inbox for new emails."

Hermes should list the test email.

---

## Known Failure Modes

| Problem | Fix |
|---------|-----|
| Honcho can't connect to PostgreSQL | Verify `HONCHO_DATABASE_URL` is set and `createdb honcho` was run |
| Redis connection refused | `brew services restart redis` |
| Hermes can't find Honcho tools | Ensure `memory.provider: honcho` in config.yaml |
| AgentMail 403 errors | Verify API key has permissions at console.agentmail.to |
| Obsidian vault not found | Check `WIKI_PATH` env var or vault location in Hermes config |

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
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Obsidian: https://obsidian.md/help
- AgentMail: https://agentmail.to/
- Live deployment reference: github.com/SaintChris
