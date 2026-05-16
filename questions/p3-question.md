# AI Customer Ticket Triage — Microservice-Based Support Automation Platform — Interview Questions

**Stack**: Node.js, TypeScript, NestJS, Next.js, React.js, GraphQL, PostgreSQL, Sequelize, Redis, BullMQ, Docker, Docker Compose, OpenTelemetry, Prometheus, Grafana

---

## Backend Tech Lead Lens

### Technical
1. You have 6+ microservices. Walk me through the service boundaries — why is each service separate rather than a monolith? What's the communication contract between them (GraphQL schema, REST contract, or message envelope)?
2. You mention both BullMQ and Kafka for async messaging. What's the use case for each in your architecture? What criteria would make you commit fully to Kafka and drop BullMQ?
3. Multi-agent AI triage with GPT-4 and Claude. How do you handle LLM failures (timeout, hallucination, rate limit)? What's your fallback strategy and how does the dead-letter queue feed into the retry logic?
4. You mention distributed tracing with OpenTelemetry. What custom spans and attributes did you define for the ticket lifecycle? How do you correlate a trace across: HTTP request → GraphQL resolver → BullMQ job → LLM API call?

### System Design
5. Design the ticket ingestion pipeline: 10k tickets/hour arrive via email, API, and chat. How does the API gateway route them? What's the queue topology (queues, exchanges, DLQ)? How do you guarantee exactly-once processing for a ticket submission?
6. Your dashboard shows "priority-sorted queues" and "SLA tracking." Design the real-time update mechanism — how does the React frontend receive a new high-priority ticket within 2 seconds of ingestion? WebSockets? SSE? Polling? What's your backpressure strategy?
7. Multi-agent AI for classification, priority prediction, smart routing, and reply suggestions. Design the prompt architecture — how do you ensure consistent output format across GPT-4 and Claude? How do you handle schema disagreements?

### Behavioral
8. This project uses present tense ("Designing", "Architecting", "Building"). What's the current status — is it deployed? Being used? What's the next milestone and what's blocking it?

---

## Full Stack Engineer Lens

### Technical
9. You have dual frontends: Next.js homepage and React+GraphQL dashboard. Why two separate apps instead of one Next.js app with both pages? What's the deployment strategy — do they share a domain?
10. Real-time WebSocket updates on the dashboard — how do you handle reconnection? What happens to the UI state when the WebSocket drops and reconnects? Do you replay missed events?

### Frontend
11. The dashboard shows priority-sorted queues with AI confidence scoring. How did you handle real-time sorting in React state when a new high-priority ticket arrives? Did you use optimistic updates? What state management tool did you choose?

---

## Product Manager Lens

### Product
12. What's the success metric for this platform? Ticket resolution time reduction? First-response SLA? Agent productivity (tickets/agent/day)? Customer satisfaction? Walk me through the north star.
13. An LLM hallucinates a reply suggestion that an agent sends to a customer. Who owns the risk — the AI platform, the agent, or the business? What's your mitigation strategy for production?

---

## HR / Talent Acquisition Lens

### Behavioral
14. This architecture is complex for a student project — 6 microservices, AI agents, observability stack. How did you learn these technologies? What was your learning path and how did you validate your architecture decisions?
15. If you were to ship this to production tomorrow, what's the one thing you'd be most worried about breaking and why?
