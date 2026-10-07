# Awesome Agent Protocols

> Curated protocols, SDKs, and tools for AI agent communication — email, MCP, webhooks, and inter-agent messaging.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Add Email to your agent](https://img.shields.io/badge/email%20for%20agents-commune.email-blue)](https://commune.email?ref=awesome-agent-protocols)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

### [Add Email to your AI Agent — commune.email](https://commune.email?ref=awesome-agent-protocols)

> Give your agent a real inbox in 4 lines · [Python](https://github.com/shanjairaj7/commune-python) · [TypeScript](https://github.com/shanjairaj7/commune-ai) · [MCP](https://github.com/shanjairaj7/commune-mcp) · [Examples](https://github.com/shanjairaj7/email-for-agents)

---

## Contents

- [Email](#email)
- [MCP Servers](#mcp-servers)
- [Webhooks and Event Delivery](#webhooks-and-event-delivery)
- [Inter-Agent Protocols](#inter-agent-protocols)
- [Real-Time Messaging](#real-time-messaging)
- [Message Queues](#message-queues)
- [Notification Routing](#notification-routing)
- [Agent-to-Human Communication Patterns](#agent-to-human-communication-patterns)

---

## Email

Tools and protocols for giving AI agents full email capability — send, receive, thread management, webhooks.

### SDKs and APIs

- **[Commune](https://commune.email?ref=awesome-agent-protocols)** — Purpose-built email API for AI agents. Programmatic inboxes, webhook delivery, thread continuity, structured data extraction, prompt injection detection. `pip install commune-mail` / `npm install commune-ai` / `uvx commune-mcp`
- **[Nylas](https://nylas.com)** — Email and calendar API with IMAP/SMTP abstraction. Supports Gmail, Outlook, Exchange, Yahoo. Not agent-native but widely used in agent stacks for reading existing inboxes.
- **[Resend](https://resend.com)** — Developer-first transactional email API. React Email templates, inbound email parsing, webhook delivery. Clean REST API.
- **[Inbox Zero](https://www.inboxzero.com)** — Open-source AI email management. GitHub: [elie222/inbox-zero](https://github.com/elie222/inbox-zero). Self-hostable.
- **[SendGrid](https://sendgrid.com)** — Twilio's email API. Transactional + marketing. SMTP relay and HTTP API. Not agent-native.
- **[Postmark](https://postmarkapp.com)** — Transactional email API with inbound processing. Known for fastest delivery.
- **[AWS SES](https://aws.amazon.com/ses)** — Email sending + receiving at scale. SNS integration for inbound webhooks. Used by Commune's infrastructure.

### Protocols

- **[SMTP](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol)** — Standard protocol for sending email. Agents use SMTP directly via `smtplib` (Python) or `nodemailer` (Node.js).
- **[IMAP](https://en.wikipedia.org/wiki/Internet_Message_Access_Protocol)** — Protocol for reading/organizing email. Used for agents polling existing inboxes.
- **[MIME](https://en.wikipedia.org/wiki/MIME)** — Email format standard. Attachments, HTML/text multipart, encoding.

### Parsers and Tools

- **[mail-parser](https://github.com/nicedoc/mail-parser)** — Python email parsing library.
- **[email-reply-parser](https://github.com/github/email_reply_parser)** — Extract just the reply portion from threaded email (GitHub's version).
- **[flanker](https://github.com/mailgun/flanker)** — Mailgun's email address + MIME parsing library (Python).
- **[postal-mime](https://github.com/postalsys/postal-mime)** — Email parser for Cloudflare Workers and browsers.

---

## MCP Servers

Model Context Protocol (MCP) enables LLMs to use tools via a standardized interface. Servers expose tools to Claude Desktop, Cursor, Windsurf, and any MCP client.

### Email and Communication

- **[Commune MCP](https://github.com/shanjairaj7/commune-mcp)** — Email for Claude Desktop, Cursor, Windsurf. Create inboxes, send email, read threads. `uvx commune-mcp`
- **[Gmail MCP](https://github.com/google-a2a/gmail-mcp)** — Official Gmail MCP server by Google. Read, send, search Gmail.
- **[Outlook MCP](https://github.com/modelcontextprotocol/servers)** — Microsoft Outlook via MCP. Part of official MCP reference servers.

### Web and Research

- **[Firecrawl MCP](https://github.com/firecrawl/mcp-firecrawl)** — Web scraping and crawling via MCP. Fetch any URL as markdown.
- **[Browserbase MCP](https://github.com/browserbase/mcp-browserbase)** — Browser automation via MCP. Navigate, click, extract from websites.
- **[Tavily MCP](https://github.com/tavily-ai/tavily-mcp)** — Real-time web search via MCP.
- **[Exa MCP](https://github.com/exa-labs/exa-mcp-server)** — Semantic web search via MCP.

### Code Execution

- **[E2B MCP](https://github.com/e2b-dev/mcp-server)** — Secure code execution in sandboxes via MCP. `npx @smithery/cli install e2b --client claude`

### Storage and Databases

- **[Supabase MCP](https://github.com/supabase/mcp-server-supabase)** — Official Supabase MCP. Query databases, manage tables, run edge functions.
- **[GitHub MCP](https://github.com/github/github-mcp-server)** — Official GitHub MCP. Read/write repos, issues, PRs, search code.

### Registries

- **[Smithery](https://smithery.ai)** — Primary MCP server registry. Install any server with `npx @smithery/cli install <id> --client claude`
- **[MCP.so](https://mcp.so)** — MCP server directory and marketplace.
- **[Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers)** — Community curated list. 10,000+ stars.

---

## Webhooks and Event Delivery

Infrastructure for reliable webhook ingestion and delivery to agents.

- **[Svix](https://svix.com)** — Webhook sending service-as-a-service. Retries, signatures, portal, replay. Used by OpenAI, Clerk, Resend.
- **[Hookdeck](https://hookdeck.com)** — Webhook ingestion and processing platform. Retry, replay, filter, transform incoming webhooks.
- **[Inngest](https://inngest.com)** — Durable background jobs triggered by events. Retries, fan-out, human-in-the-loop.
- **[Trigger.dev](https://trigger.dev)** — Event-driven background tasks for TypeScript. Long-running agent steps without timeouts.
- **[QStash](https://upstash.com/qstash)** — HTTP message queue and scheduler for serverless. Exactly-once delivery, cron, deduplication.
- **[Temporal](https://temporal.io)** — Durable workflow execution. Long-running agent pipelines that survive failures. Used by OpenAI.
- **[Soketi](https://soketi.app)** — Open-source, self-hosted Pusher-compatible WebSocket server. Real-time events for agents.

---

## Inter-Agent Protocols

Protocols and frameworks for agents to communicate with other agents.

### Standards

- **[A2A (Agent-to-Agent)](https://github.com/google-deepmind/agent-to-agent)** — Google DeepMind's open protocol for AI agents to communicate. Agent discovery, capability negotiation, task handoff.
- **[ANP (Agent Network Protocol)](https://github.com/agent-network-protocol/ANP)** — Open protocol for decentralized agent communication. JSON-LD, W3C DID-based identity.
- **[MCP (Model Context Protocol)](https://modelcontextprotocol.io)** — Anthropic's standard for LLM-tool integration. Increasingly used for agent-to-tool and agent-to-agent comms.
- **[Voidly Agent Relay](https://voidly.ai/agents)** — A2A v0.3.0 Agent Card plus an agent relay protocol. The SDK encrypts message content on the client (Double Ratchet, X3DH, ML-KEM-768 hybrid); the relay stores sender and recipient DIDs, and legacy relay-key routes are relay-readable. Published spec, `@voidly/agent-sdk` on npm.

### Orchestration Frameworks

- **[LangGraph](https://langchain.com/langgraph)** — Stateful multi-agent graphs. Agents pass structured state through graph edges. Persistent memory.
- **[CrewAI](https://crewai.com)** — Role-based multi-agent crews. Agents collaborate with defined responsibilities and goals.
- **[AutoGen / AG2](https://github.com/microsoft/autogen)** — Microsoft's conversational multi-agent framework. Agents exchange messages to solve tasks.
- **[OpenAI Agents SDK](https://openai.github.io/openai-agents-python)** — Handoffs, guardrails, sessions. Production-ready multi-agent coordination.
- **[smolagents](https://github.com/huggingface/smolagents)** — Minimal agent framework with code-first inter-agent communication.

### Message Passing

- **[Redis Pub/Sub](https://redis.io/docs/manual/pubsub/)** — Message broadcasting between agent instances.
- **[RabbitMQ](https://rabbitmq.com)** — Message broker for agent task queuing and distribution.
- **[NATS](https://nats.io)** — Lightweight messaging for distributed agent systems. Sub-millisecond delivery.
- **[BullMQ](https://bullmq.io)** — Redis-based job queue for Node.js. Reliable background task handling for agents.
- **[Celery](https://celeryq.dev)** — Distributed task queue for Python agents. Widely used in CrewAI/LangChain deployments.

---

## Real-Time Messaging

### Channels

- **[Slack SDK](https://github.com/slackapi/python-slack-sdk)** — Official Python SDK for Slack. Agents read/post to channels, respond to mentions.
- **[Discord.py](https://github.com/Rapptz/discord.py)** — Discord bot framework. Agents in Discord servers.
- **[Telegram Bot API](https://core.telegram.org/bots/api)** — Telegram bots for agent interaction. Widely used for personal agents.
- **[Matrix](https://matrix.org)** — Open, decentralized real-time communication protocol. End-to-end encrypted. Growing agent adoption.
- **[WhatsApp Business API](https://developers.facebook.com/docs/whatsapp)** — WhatsApp for business-grade agent messaging.

### Push Notifications

- **[Apple Push Notification Service (APNs)](https://developer.apple.com/documentation/usernotifications)** — Push for iOS agents.
- **[Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging)** — Cross-platform push. Used for agent-to-mobile-app notifications.
- **[OneSignal](https://onesignal.com)** — Multi-channel push: web, mobile, SMS, email. Widely used for agent notification routing.
- **[Novu](https://novu.co)** — Open-source notification infrastructure. Multi-channel (email, SMS, push, chat, in-app). GitHub: [novuhq/novu](https://github.com/novuhq/novu) — 35k+ stars.

---

## Message Queues

Reliable task and message delivery infrastructure for agent pipelines.

- **[BullMQ](https://bullmq.io)** — Redis-based queue for Node.js. Retries, rate limiting, delayed jobs, concurrency. Widely used in AI backends.
- **[Celery + Redis/RabbitMQ](https://docs.celeryq.dev)** — Python distributed task queue. Standard for LangChain/CrewAI production deployments.
- **[AWS SQS](https://aws.amazon.com/sqs)** — Managed message queue. Standard FIFO or best-effort ordering. Used at massive scale.
- **[Google Cloud Pub/Sub](https://cloud.google.com/pubsub)** — Real-time message streaming. Global, serverless.
- **[Apache Kafka](https://kafka.apache.org)** — High-throughput event streaming. Agent event sourcing at enterprise scale.
- **[NATS JetStream](https://docs.nats.io/nats-concepts/jetstream)** — Persistent messaging for distributed agent systems.

---

## Notification Routing

Multi-channel alert and notification infrastructure.

- **[Novu](https://novu.co)** — Open-source notification orchestration. Multi-step, multi-channel. 35k+ GitHub stars.
- **[Courier](https://courier.com)** — Multi-channel notification routing: email, SMS, push, in-app, Slack. Smart routing based on user preferences.
- **[Knock](https://knock.app)** — Notification infrastructure with user preferences, templates, batching, digest.
- **[PagerDuty](https://pagerduty.com)** — On-call alerting and incident management. Used by agents for critical alerts.
- **[OpsGenie](https://opsgenie.com)** — Alert management and on-call scheduling. Agent integration for incident response.

---

## Agent-to-Human Communication Patterns

Design patterns for how AI agents communicate with humans.

- **Email-first agents** — Agent has a real email inbox; humans can reply by email. Thread context is preserved. Recommended for async, non-urgent tasks. See: [Commune email-for-agents examples](https://github.com/shanjairaj7/email-for-agents?ref=awesome-agent-protocols)
- **Webhook-reactive agents** — Agent is dormant until an event fires (new email, new message, scheduled trigger). No polling. More efficient, lower latency.
- **Approval-gate agents** — Agent generates output, sends for human review via email/Slack before acting. Common in financial and legal workflows.
- **Digest agents** — Agent batches updates and sends periodic summaries (daily/weekly). Reduces notification fatigue.
- **Escalation chains** — Agent handles simple cases autonomously; escalates to human on uncertain/high-stakes decisions. Configurable confidence thresholds.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding entries.

Tools must:
- Be publicly documented with a URL
- Have a clear agent communication use case
- Be actively maintained (last commit within 12 months)

---

## License

[MIT](LICENSE) · Maintained by [Commune](https://commune.email?ref=awesome-agent-protocols)
