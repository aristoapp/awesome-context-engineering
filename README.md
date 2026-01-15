

<div align="center">

# Awesome Context Engineering

[![Context Engineering Banner](assets/context-engineering-banner.png)](https://membase.so/?utm_source=github&utm_medium=awesome-context-engineering)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

</div>

> A curated list of resources for making AI agents **truly understand you** through **Context Engineering**.

---

## What is Context Engineering?

**Context Engineering** is the practice of systematically providing AI with information about yourself—your preferences, documents, history, and workflows—to transform a generic AI assistant into one that truly understands you.

### The Problem

Every time you start a conversation with AI, it knows nothing about you:
- It doesn't know your coding style or tech stack
- It doesn't remember what you discussed yesterday
- It can't access your notes, documents, or data
- It treats you the same as millions of other users

### The Solution

Context Engineering solves this by injecting **your personal context** into AI interactions:

```
Your Context (what makes AI understand YOU)
├── Instructions: "I prefer TypeScript, be concise"
├── Background: Your role, expertise, current projects
├── Documents: Your notes, files, code
├── Memory: Facts AI learned about you over time
└── Connected Apps: Your Notion, Slack, email, calendar
```

### Key Resources

- [Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) - Anthropic's engineering blog
- [Context Engineering in Agents: Memory Patterns](https://medium.com/agenticais/context-engineering-in-agent-982cb4d36293) - Memory patterns guide
- [Building Personal Context](https://www.reddit.com/r/ClaudeAI/comments/1j6q49b/building_an_ai_agent_with_a_bank_of_personal/) - Reddit discussion

---

## Contents

- [Level 1: Platform Settings](#level-1-platform-settings)
  - [ChatGPT](#chatgpt)
  - [Claude](#claude)
  - [Cursor](#cursor)
  - [GitHub Copilot](#github-copilot)
  - [Gemini](#gemini)
- [Level 2: Connecting Your Data](#level-2-connecting-your-data)
  - [Model Context Protocol (MCP)](#model-context-protocol-mcp)
  - [Browser Extensions](#browser-extensions)
  - [Automation](#automation)
- [Level 3: Personal Memory](#level-3-personal-memory)
  - [Built-in Memory Features](#built-in-memory-features)
  - [Personal Memory Services](#personal-memory-services)
  - [Self-Hosted Personal Memory](#self-hosted-personal-memory)
  - [Knowledge Management with AI](#knowledge-management-with-ai)
- [Level 4: Personal AI Stack](#level-4-personal-ai-stack)
  - [Personal AI Assistants](#personal-ai-assistants)
  - [Local LLM Solutions](#local-llm-solutions)
  - [Personal Knowledge Base](#personal-knowledge-base)
  - [Document Processing](#document-processing)
- [All-in-One Solution](#all-in-one-solution)
- [Papers](#papers)
- [Resources](#resources)

---

## Level 1: Platform Settings

> Basic personalization using built-in features. Takes 5 minutes.

### ChatGPT
- [Custom Instructions Guide](https://help.openai.com/en/articles/8096356-custom-instructions-for-chatgpt) - Official guide for personalization
- [Memory Feature FAQ](https://help.openai.com/en/articles/8590148-memory-faq) - How ChatGPT remembers you
- [Custom GPTs](https://help.openai.com/en/articles/8554397-creating-a-gpt) - Build personalized GPT
- [Awesome ChatGPT Prompts](https://github.com/f/awesome-chatgpt-prompts) - 1000+ prompt templates
- [ChatGPT AutoExpert](https://github.com/spdustin/ChatGPT-AutoExpert) - Custom instructions for better responses
- [Mr. Ranedeer AI Tutor](https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor) - Personalized learning GPT

### Claude
- [Claude Projects](https://support.anthropic.com/en/articles/9519177-how-can-i-create-and-manage-projects) - Project-based context
- [Custom Instructions](https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features) - Personalization features
- [Claude Prompt Library](https://docs.anthropic.com/en/prompt-library/library) - Official prompt examples
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) - Official examples and recipes
- [Claude Engineer](https://github.com/Doriandarko/claude-engineer) - Engineering assistant setup

### Cursor
- [Rules for AI](https://docs.cursor.com/context/rules-for-ai) - Official documentation
- [Context Guide](https://docs.cursor.com/context/) - Understanding cursor context
- [cursor.directory](https://cursor.directory/) - 1000+ community cursor rules
- [Awesome CursorRules](https://github.com/PatrickJS/awesome-cursorrules) - Curated rules collection
- [Cursor Rules by Pontus](https://github.com/pontusab/cursor.directory) - Source for cursor.directory
- [Cursor Rules Collection](https://github.com/sanjeed5/awesome-cursor-rules) - Another curated collection

### GitHub Copilot
- [Copilot Customization](https://docs.github.com/en/copilot/customizing-copilot) - Official docs
- [Custom Instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot) - Adding instructions

### Gemini
- [Gemini Extensions](https://support.google.com/gemini/answer/13695044) - Connect Google services
- [Gems (Custom Gemini)](https://support.google.com/gemini/answer/14575153) - Create personalized Gemini

---

## Level 2: Connecting Your Data

> Give AI access to your files, notes, and apps.

### Model Context Protocol (MCP)
- [MCP Documentation](https://modelcontextprotocol.io/) - Official docs
- [MCP Announcement](https://www.anthropic.com/news/model-context-protocol) - Anthropic's blog
- [Official MCP Servers](https://github.com/modelcontextprotocol/servers) - Reference implementations
- [Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers) - Community servers list (800+)
- [MCP Hub](https://github.com/nicobailey/mcp-hub) - Another server collection
- [MCP Quickstart](https://modelcontextprotocol.io/quickstart) - Official setup guide
- [Claude Desktop MCP Config](https://modelcontextprotocol.io/quickstart/user) - Configuration for Claude Desktop

**Popular MCP Servers:**
- [Filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) - Connect your local files
- [Obsidian](https://github.com/smithery-ai/mcp-obsidian) - Your Obsidian vault
- [Obsidian Memory MCP](https://github.com/yunaga224/obsidian-memory-mcp) - Memory as markdown in Obsidian
- [Obsidian Palace](https://obsidianpalace.dev/) - Enhanced Obsidian integration
- [Notion](https://github.com/modelcontextprotocol/servers/tree/main/src/notion) - Your Notion pages
- [Google Drive](https://github.com/modelcontextprotocol/servers/tree/main/src/gdrive) - Your Drive files
- [Memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) - Personal knowledge graph

### Browser Extensions
- [Sider](https://sider.ai/) - AI sidebar with page context
- [Monica](https://monica.im/) - Browser AI with memory
- [Merlin](https://getmerlin.in/) - ChatGPT on any webpage
- [MaxAI](https://www.maxai.me/) - Multi-model browser AI

### Automation
- [Zapier](https://zapier.com/) - Connect AI to 6000+ apps (Cloud)
- [n8n](https://github.com/n8n-io/n8n) - Open-source workflow automation (Self-hosted)
- [Activepieces](https://github.com/activepieces/activepieces) - Open-source Zapier alternative (Self-hosted)

---

## Level 3: Personal Memory

> AI that remembers you across conversations.

### Built-in Memory Features
- [ChatGPT Memory](https://help.openai.com/en/articles/8590148-memory-faq) - Auto-learns from conversations
- [Claude Projects](https://support.anthropic.com/en/articles/9519177) - Persistent context per project
- [Gemini Saved Info](https://support.google.com/gemini) - Save information for Gemini

### Personal Memory Services
- [Rewind](https://www.rewind.ai/) - Records everything on Mac, AI-searchable
- [Supermemory](https://github.com/supermemoryai/supermemory) - Memory from bookmarks, tweets, articles
- [Pieces](https://pieces.app/) - Long-term memory across dev tools
- [Personal AI](https://personal.ai/) - AI that learns your knowledge
- [Granola](https://www.granola.ai/) - AI notepad for meetings
- [Memspan](https://memspan.ai/) - File-first personal memory, portable

### Self-Hosted Personal Memory
- [Jean Memory](https://www.reddit.com/r/ClaudeAI/comments/1l17qf6) - Remote personal memory for Claude
- [Sem-Mem](https://www.reddit.com/r/AIMemory/comments/1pg5fro) - Local semantic memory system
- [MemLayer](https://www.reddit.com/r/LocalLLaMA/comments/1ozbzpx) - Persistent memory for local LLMs
- [Basic Memory](https://docs.basicmemory.com/how-to/personal-knowledge) - Personal knowledge graph system
- [OpenMemory](https://github.com/CaviraOSS/OpenMemory) - Rich memory with natural decay
- [Memori](https://github.com/GibsonAI/memori) - SQL-native personal memory
- [rag-user-memories](https://github.com/skorotkiewicz/rag-user-memories) - Extract & store personal facts

### Knowledge Management with AI
- [Notion AI](https://notion.so/) - AI over your Notion workspace
- [Mem](https://mem.ai/) - AI-powered notes
- [Reflect](https://reflect.app/) - AI-native note-taking
- [Obsidian + AI](https://obsidian.md/) - Local notes with AI plugins
- [Reor](https://github.com/reorproject/reor) - Local PKM with vector search
- [Memos](https://github.com/usememos/memos) - Self-hosted, privacy-first notes

---

## Level 4: Personal AI Stack

> Self-hosted AI systems you fully control.

### Personal AI Assistants
- [Open WebUI](https://github.com/open-webui/open-webui) - ChatGPT-like UI with memory & RAG
- [Khoj](https://github.com/khoj-ai/khoj) - Personal AI for your notes/docs
- [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) - All-in-one document AI
- [Quivr](https://github.com/QuivrHQ/quivr) - Second brain with AI
- [PrivateGPT](https://github.com/imartinez/privateGPT) - Fully private document chat
- [Danswer](https://github.com/danswer-ai/danswer) - AI search over your data
- [Perplexica](https://github.com/ItzCrazyKns/Perplexica) - Personal AI search engine
- [Second Me](https://github.com/mindverse/Second-Me) - AI self with hierarchical memory
- [STING](https://stingassistant.com/) - Privacy-first desktop AI
- [Tiiny AI](https://tiinyai.com/) - Local DB from your files
- [Open WebUI Docker Setup](https://docs.openwebui.com/getting-started/) - Official setup guide
- [Khoj Self-Hosting](https://docs.khoj.dev/get-started/setup/) - Self-hosting documentation

### Local LLM Solutions
- [Ollama](https://ollama.com/) - Run LLMs locally
- [LM Studio](https://lmstudio.ai/) - Desktop LLM app
- [Jan](https://jan.ai/) - Offline AI assistant
- [GPT4All](https://gpt4all.io/) - Local LLM ecosystem
- [Llamafile](https://github.com/Mozilla-Ocho/llamafile) - Single-file LLM distribution

### Personal Knowledge Base
- [Chroma](https://github.com/chroma-core/chroma) - Easy to start vector database
- [LanceDB](https://github.com/lancedb/lancedb) - Embedded, no server needed
- [LangChain RAG Tutorial](https://python.langchain.com/docs/tutorials/rag/) - Build personal RAG
- [LlamaIndex Getting Started](https://docs.llamaindex.ai/en/stable/getting_started/concepts/) - Document AI concepts

### Document Processing
- [DocMind AI](https://github.com/BjornMelin/docmind-ai-llm) - Offline document analysis with GraphRAG
- [Marker](https://github.com/VikParuchuri/marker) - PDF to Markdown
- [Unstructured](https://github.com/Unstructured-IO/unstructured) - Multi-format processing

---

## All-in-One Solution

Building your own personalization stack is powerful but complex. If you want everything above in one solution:

### [Membase](https://membase.so/?utm_source=github&utm_medium=awesome-context-engineering) - Universal Memory for your Agnets

A personal memory layer that gives you:

- **Cross-agent sync**: Discuss plans with ChatGPT, then jump into Claude Code to build them without re-explaining context. Your memory follows you across all agents.

- **External context awareness**: Automatically pulls context from your calendar, Notion, Slack, and emails. Your AI knows what's happening in your life without you explicitly saying it.

- **Token efficient**: Instead of dumping everything into every session, Membase uses hybrid retrieval to inject only the relevant context for each request.

[Join the waitlist →](https://membase.so/)

---

## Resources

### Papers

**Foundational**
- [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) - Virtual context management with tiered memory
- [Retrieval-Augmented Generation for Knowledge-Intensive NLP](https://arxiv.org/abs/2005.11401) - The original RAG paper

**Context Engineering**
- [Google's Context Engineering Whitepaper](https://www.kaggle.com/whitepaper-context-engineering-sessions-and-memory) - Official Google whitepaper on sessions and memory
- [Context Engineering 2.0](https://huggingface.co/papers/2510.26493) - Historical & conceptual grounding of context engineering
- [Agentic Context Engineering (ACE)](https://arxiv.org/abs/2510.04618) - Evolving contexts for self-improving LLMs
- [Everything is Context](https://arxiv.org/abs/2512.05470) - File system abstraction for context engineering
- [Chain of Agents](https://research.google/blog/chain-of-agents-large-language-models-collaborating-on-long-context-tasks/) - Google's framework for long-context collaboration
- [The Complexity Trap](https://arxiv.org/abs/2508.21433) - Simple observation masking vs LLM summarization for context management

**Personal Memory & Personalization**
- [USER-LLM](https://research.google/pubs/user-llm-efficient-llm-contextualization-with-user-embedding/) - Google's user embedding for LLM personalization
- [O-Mem: Omni Memory System](https://arxiv.org/abs/2511.13593) - Hierarchical memory for personalized agents
- [CUPID](https://arxiv.org/abs/2508.01674) - Evaluating personalized alignment from interactions
- [ComMer](https://arxiv.org/abs/2501.03276) - Compressing user data for personalization

**Memory Systems**
- [Memory in AI Agents: Taxonomies & Directions](https://www.emergentmind.com/papers/2512.13564) - Systematic memory classification
- [A-MEM: Agentic Memory](https://arxiv.org/abs/2502.12110) - Dynamic memory organization with Zettelkasten-style linking
- [HiMeS](https://arxiv.org/abs/2601.06152) - Hierarchical short + long-term memory
- [Second Me](https://arxiv.org/abs/2503.08102) - AI self with hierarchical memory
- [Evo-Memory](https://arxiv.org/abs/2511.20857) - Google's benchmarking of LLM agent test-time learning with self-evolving memory

**Agent Systems & Orchestration**
- [Multi-Agent Collaboration via Evolving Orchestration](https://arxiv.org/abs/2505.19591) - Evolving multi-agent collaboration patterns
- [CodeAct: Executable Code Actions Elicit Better LLM Agents](https://arxiv.org/abs/2402.01030) - Code-based agent actions

**Evaluation & Benchmarks**
- [LOCCO](https://aclanthology.org/2025.findings-acl.1014/) - Evaluating long-term memory of LLMs
- [MemoryAgentBench](https://arxiv.gg/abs/2507.05257) - Benchmarking memory via multi-turn interactions

### Articles & Blogs

- [Context Engineering for AI Agents](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus) - Manus's lessons from building AI agents
- [Context Rot](https://research.trychroma.com/context-rot) - Chroma's research on context degradation
- [Memory in AI Agents](https://www.philschmid.de/memory-in-agents) - Engineering long-term memory
- [Agent Memory by Letta](https://www.letta.com/blog/agent-memory) - Comprehensive memory guide
- [Recursive Language Models](https://alexzhang13.github.io/blog/2025/rlm/) - New paradigm for LLM architecture

### Related Awesome Lists

- [Awesome LLM](https://github.com/Hannibal046/Awesome-LLM) - LLM resources
- [Awesome LLM Apps](https://github.com/Shubhamsaboo/awesome-llm-apps) - LLM applications
- [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents) - AI agents list
- [Awesome Local AI](https://github.com/janhq/awesome-local-ai) - Local AI resources

### Community Resources

- [r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/)
- [r/ChatGPT](https://www.reddit.com/r/ChatGPT/)
- [r/LocalLLaMA](https://www.reddit.com/r/LocalLLaMA/)
- [r/ObsidianMD](https://www.reddit.com/r/ObsidianMD/)
- [Cursor Forum](https://forum.cursor.com/)

---

## Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md).

**Looking for:**
- Real examples and templates people have created
- Personal memory projects and services
- MCP servers and integrations
- Setup guides and tutorials

---

### Join the Community

- [Join our Discord](https://discord.com/invite/vRp5Zh3HGu) - Chat with other developers personalizing agents
- [Follow on Twitter](https://x.com/mem_base) - Stay updated on new updates and features
- Questions? support@aristo.so

---

<p align="center">
  <b>Join 1,300+ developers personalizing agents</b>
</p>

<p align="center">
  <a href="https://membase.so/?utm_source=github&utm_medium=awesome-context-engineering">
    <img src="https://img.shields.io/badge/Join Waitlist-4F46E5?style=for-the-badge"/>
  </a>
</p>

---

## License

Apache License 2.0 - see [LICENSE](LICENSE).

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
