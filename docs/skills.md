# Engineering skills demonstrated

All items below are supported by the private project. No code is included.

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
