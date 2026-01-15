# Awesome Context Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, techniques, and resources for teaching AI agents to understand your personal context.

Context Engineering is the practice of customizing AI assistants (Claude, ChatGPT, Cursor, etc.) to understand your individual preferences, workflows, and requirements. This goes beyond prompt engineering—it's about creating persistent, personalized AI experiences that adapt to **you**.

## Contents

- [Platform-Specific Customization](#platform-specific-customization)
  - [Claude](#claude)
  - [Cursor](#cursor)
  - [ChatGPT](#chatgpt)
  - [VS Code Copilot](#vs-code-copilot)
- [Model Context Protocol (MCP)](#model-context-protocol-mcp)
- [Context Management Techniques](#context-management-techniques)
- [Memory & Persistence](#memory--persistence)
- [Research & Articles](#research--articles)
- [Tools & Frameworks](#tools--frameworks)
- [Contributing](#contributing)

## Platform-Specific Customization

### Claude

**Official Resources**
- [Claude Projects](https://www.anthropic.com/news/projects) - Organize work with persistent context and custom instructions
- [Understanding Claude's Personalization Features](https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features) - Official guide to custom instructions and styles
- [Creating and Managing Projects](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects) - How to set up project-specific context

**Community Resources**
- [Claude Projects Tutorial](https://www.youtube.com/watch?v=GJ5jTgcbRHA) - Getting started with Projects in Claude.ai
- [Effective Context Management in Claude Projects](https://www.reddit.com/r/ClaudeAI/comments/1gze5b9/how_do_you_effectively_manage_context_in_claudes/) - Community discussion on context strategies

### Cursor

**Official Resources**
- [Cursor Rules Documentation](https://rolloutit.net/how-to-create-ai-rules-for-cursor-ai/) - Complete guide to `.cursorrules` files
- [AI Rules for Cursor](https://forum.cursor.com/t/ai-rules-how-to-actually-force-inclusion-of-specific-files-in-context/69761) - Force-include specific files in context

**Community Resources**
- [Cursor Rules Folder Tutorial](https://www.youtube.com/watch?v=KzkXJiXGUGw) - Video guide to customizing AI behavior
- [Cursor Customization 가이드](https://tech.neordinary.co.kr/cursor-customization) - Korean guide to Cursor customization (KR)

### ChatGPT

**Official Resources**
- [ChatGPT Custom Instructions Guide](https://customgpt.ai/chatgpt-custom-instructions-template/) - Comprehensive template guide
- [Custom Instructions for Beginners](https://www.reddit.com/r/ChatGPTPro/comments/1cevlah/guide_for_beginners_custom_instructions_and/) - Reddit guide comparing custom instructions vs. memory

**Community Resources**
- [90% of Users Ignore This Feature](https://simple.ai/p/how-to-use-chatgpt-custom-instructions) - Deep dive into custom instructions
- [Custom Instructions Tutorial](https://www.youtube.com/watch?v=example) - Video walkthrough

### VS Code Copilot

**Official Resources**
- [Custom Agents in VS Code](https://code.visualstudio.com/docs/copilot/customization/custom-agents) - Configure AI personas for different development roles

## Model Context Protocol (MCP)

MCP is an open protocol by Anthropic that standardizes how LLMs connect to external data sources and tools.

**Official Resources**
- [Model Context Protocol Docs](https://modelcontextprotocol.io) - Official MCP documentation
- [Introducing MCP](https://www.anthropic.com/news/model-context-protocol) - Anthropic's announcement
- [MCP Explained - Vercel](https://vercel.com/blog/model-context-protocol-mcp-explained) - FAQ and technical overview

**MCP Servers**
- [Official MCP Servers](https://github.com/modelcontextprotocol/servers) - Reference implementations
- [Awesome MCP Servers](https://mcpservers.org) - Curated collection of MCP servers

**Available Servers**
- **Filesystem** - Secure file operations with access controls
- **Git** - Read, search, and manipulate Git repositories
- **Memory** - Knowledge graph-based persistent memory
- **Time** - Time and timezone conversion
- **Sequential Thinking** - Dynamic problem-solving through thought sequences

## Context Management Techniques

### Anthropic's Best Practices

- [Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) - Official engineering blog from Anthropic
  - Progressive disclosure strategies
  - Compaction and summarization
  - Structured note-taking (agentic memory)
  - Multi-agent architectures

### Academic & Industry Research

- [Prompt Engineering vs. Context Engineering](https://www.linkedin.com/pulse/context-all-you-need-importance-prompt-engineering-amir-amin-ph-d--0nc1c) - Evolution from prompts to context
- [Context is All You Need](https://www.linkedin.com/pulse/prompt-engineering-vs-context-ibrahem-amer-inzdf) - LinkedIn article on context importance
- [Awesome Context Engineering](https://github.com/Meirtz/Awesome-Context-Engineering) - Comprehensive survey of context engineering resources

## Memory & Persistence

### Memory Systems

- [Memory in Agents](https://www.philschmid.de/memory-in-agents) - Engineering long-term memory for AI agents
- [Agent Memory by Letta](https://www.letta.com/blog/agent-memory) - Techniques for building agents that learn
- [State Management with Long-Term Memory](https://cookbook.openai.com/examples/agents_sdk/context_personalization) - OpenAI Cookbook example

### Memory Frameworks

- [MemGPT](https://github.com/cpacker/MemGPT) - Operating system approach to LLM memory management
- [Zep](https://github.com/getzep/zep) - Long-term memory store for LLM applications
- [LangChain Memory](https://docs.langchain.com/oss/python/langchain/short-term-memory) - Customizing agent memory with LangChain

### Memory Types

- **Semantic Memory** - Facts and concepts ("user prefers Python")
- **Episodic Memory** - Past events and experiences
- **Procedural Memory** - Internalized rules and instructions

## Research & Articles

### Context Engineering

- [Best Practices for In-Context Learning](https://www.reddit.com/r/LLMDevs/comments/1g8uio9/prompt_engineering_best_practices_for_incontext/) - Reddit discussion on ICL techniques
- [Building an AI Agent with Personal Context](https://www.reddit.com/r/LLMDevs/comments/1j6q49b/building_an_ai_agent_with_a_bank_of_personal/) - Case study on context interviews

### AI Personalization Research

- [Context Aware Agents](https://customgpt.ai/introducing-context-aware-agents/) - Self-aware AI with deep user understanding
- [AI Agents that Adapt to User Preferences](https://www.arsturn.com/blog/creating-an-ai-agent-that-adapts-to-user-preferences-over-time) - Adaptive personalization techniques

## Tools & Frameworks

### Development Frameworks

- [LangChain](https://github.com/langchain-ai/langchain) - Framework for context-aware AI applications
- [LlamaIndex](https://github.com/run-llama/llama_index) - Data framework for LLM applications

### Context Tools

- [Pinecone](https://www.pinecone.io/) - Vector database for semantic search and memory
- [Weaviate](https://github.com/weaviate/weaviate) - Open-source vector search engine
- [Chroma](https://github.com/chroma-core/chroma) - AI-native embedding database

### Monitoring & Evaluation

- [Weights & Biases](https://wandb.ai/) - LLM monitoring and guardrails
- [LangSmith](https://www.langchain.com/langsmith) - Platform for production LLM apps

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
