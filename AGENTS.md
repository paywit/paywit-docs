# Paywit docs

Documentation site for Paywit, built on Mintlify. Pages are MDX with YAML frontmatter, configuration is `docs.json`, the API reference is generated from `api-reference/openapi.json`.

## What this documents

- The public merchant API: create payment, get payment, webhooks. Nothing else.
- The hosted checkout, sandbox testing, going live.
- The JavaScript and Flutter SDKs.

## What this must not document

- Dashboard endpoints (auth, apps, keys, settlement accounts, payment listing).
- Checkout internals (wallet-link, wallet-submit, Solana Pay routes).
- Protocol endpoints (Stellar auth, stellar.toml).

## Source of truth

- Endpoint shapes come from the API's OpenAPI output. `api-reference/openapi.json` is the public subset; update it when the API changes, never invent fields.
- Webhook signing: `Paywit-Signature: t=<unix>,v1=<hex HMAC-SHA256(secret, "<t>.<raw body>")>`.
- SDK pages follow the package READMEs in `paywit-js`, `paywit-js-sdk` and `paywit_flutter_sdk`.

## Style

- Second person, active voice, sentence case headings.
- Short sentences. Say what to do, then why, in that order.
- Code for file names, commands and field names. Bold for UI elements.
- Amounts are USDC. Sandbox URLs unless a page is specifically about mainnet.
