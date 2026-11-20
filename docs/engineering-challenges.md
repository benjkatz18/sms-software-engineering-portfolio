# Engineering challenges (high level)

Described at a conceptual level only; implementation details are private.

1. **Integrating an external event source.** Inbound messages arrive whenever the provider sends them, so the handler has to be correct on every call. That meant validating input, guarding against duplicate or abusive traffic, and answering the provider promptly.
2. **Hard output constraints.** Every outgoing message has to fit SMS length and encoding limits. Content is normalized and checked right before it is sent instead of trusting earlier steps.
3. **Testing code that depends on outside services.** Core logic is kept separate from the network calls, so it can be unit-tested without contacting the provider. End-to-end behavior is checked with real messages in a development setup.
4. **Keeping a dashboard current.** The owner's view picks up new conversations shortly after they arrive, without a manual reload.
