# SMS Messaging Platform — Software Engineering Portfolio

> **The commercial source code for this project is private.**
> This repository is a portfolio summary only. It contains no application code, configuration, data, or internal design details.

## Overview

I am the founder and developer of a commercial web application that lets a business hold two-way SMS conversations through a web dashboard. Incoming text messages arrive from a third-party telephony provider as webhook events; the application processes each event, generates and sends a reply, and records the conversation so the business owner can review it.

The project is in **active development**. It is not presented here as a launched product, and no usage, customer, or revenue figures are claimed.

## My role

- Founder and software developer
- Designed and built the web application, its backend request handling, and its integrations
- Wrote the automated tests and handled debugging, deployment fixes, and version control

## Technology (general)

| Area | Tools |
|---|---|
| Language | TypeScript |
| Web framework | Next.js (App Router), React |
| Styling | Tailwind CSS |
| Authentication | Auth.js (NextAuth) |
| Testing | Node.js built-in test runner (`node --test`) |
| Tooling | Git, ESLint, npm |
| External services | A third-party SMS/telephony API, a hosted database and file storage, a transactional email service |

Specific vendors, configuration, and infrastructure are intentionally not listed.

## Engineering skills demonstrated

- **Backend development:** server-side route handlers and server actions for authentication, account management, dashboard data, and message handling.
- **API integration:** sending messages through an external REST API and handling its responses and failures.
- **Webhook processing:** receiving inbound events from an external provider over HTTP, validating the input, and responding quickly and predictably.
- **Event-driven programming:** each inbound message triggers a processing pipeline (receive → process → reply → record) instead of a request coming from the user's browser.
- **Reliability and error handling:** fallback behavior when a step fails, per-sender usage limits, and input checks before sending, so one bad event cannot break the flow.
- **Working within protocol constraints:** SMS has strict length and character-encoding rules (for example, some characters force a more expensive encoding). Outgoing text is checked against these limits immediately before sending.
- **Testing:** unit tests for core message and dashboard logic, run with the Node.js test runner.
- **Debugging integrations:** reproducing webhook traffic locally through a tunnel to a development server, and tracking down build and deployment failures (including a framework security upgrade).
- **Frontend development:** an authenticated dashboard with live-updating conversation views (periodic refresh and refresh on tab focus) and accessible, keyboard-reachable charts.
- **Version control:** incremental, descriptive commits on a single main branch.

## Technical challenges (high level)

1. **Integrating an external event source.** Inbound messages arrive whenever the provider sends them, so the handler has to be correct on every call. That meant validating input, guarding against duplicate or abusive traffic, and answering the provider promptly.
2. **Hard output constraints.** Every outgoing message has to fit SMS length and encoding limits. Content is normalized and checked right before it is sent instead of trusting earlier steps.
3. **Testing code that depends on outside services.** Core logic is kept separate from the network calls, so it can be unit-tested without contacting the provider. End-to-end behavior is checked with real messages in a development setup.
4. **Keeping a dashboard current.** The owner's view picks up new conversations shortly after they arrive, without a manual reload.

## Status

| Area | Status |
|---|---|
| Web dashboard, authentication, account flows | Implemented |
| Inbound SMS webhook and automated replies | Implemented, in development testing |
| Automated tests for core logic | Implemented (unit level) |
| Public launch | Not yet; ongoing development |

## Architecture

A deliberately simplified, generic view of the concepts involved is in [ARCHITECTURE.md](ARCHITECTURE.md). It does not reflect the real system design.

## Source code

The application is a private commercial project, so its source code, data, and configuration are not published. I am happy to discuss the engineering in more detail in an interview.

---
© 2026 Ben Katz. All rights reserved.
