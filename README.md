# ClearBounce — Gemini CLI Extension

Verify email addresses and find business emails without leaving your terminal. This extension connects [Gemini CLI](https://geminicli.com) to the [ClearBounce](https://clearbounce.net) email verification API over MCP.

## Features

- **Verify any email address** — real-time syntax, domain, and mailbox checks with a clear `deliverable` / `risky` / `undeliverable` verdict.
- **Find business emails** — give a name and a company domain, get likely address candidates for free.
- **Check your credit balance** at any time.

## Installation

```sh
gemini extensions install https://github.com/tlgcklr/clearbounce-gemini-extension
```

## Setup

1. Create a free ClearBounce account at [clearbounce.net](https://clearbounce.net) — new accounts include free credits.
2. Create an API key at [clearbounce.net/dashboard/api-keys](https://clearbounce.net/dashboard/api-keys).
3. Export it before starting Gemini CLI:

```sh
export CLEARBOUNCE_API_KEY="cb_..."
```

## Example prompts

- "Is john.doe@acme.com a real, deliverable address?"
- "Find the email address of Jane Smith at example.com and verify the best match."
- "How many ClearBounce credits do I have left?"

## Pricing

Email finding is free. Each verification costs 1 credit. See [clearbounce.net/pricing](https://clearbounce.net/pricing) — credits never expire.

## Privacy

Email addresses you submit are processed by ClearBounce solely to perform the verification you requested. See the [ClearBounce Privacy Policy](https://clearbounce.net/privacy).

## Support

- Documentation: https://docs.clearbounce.net
- Contact: support@clearbounce.net
