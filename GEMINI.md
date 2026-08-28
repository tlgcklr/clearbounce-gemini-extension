# ClearBounce Email Verification

This extension connects Gemini CLI to ClearBounce (https://clearbounce.net), a real-time email verification service.

## Available tools

- **verify_email** — checks whether an email address is safe to send to. Returns a result of `deliverable`, `risky`, or `undeliverable` with details (syntax, domain, mailbox checks). Costs 1 credit per verification.
- **find_email** — discovers a business email address from a person's name and company domain. Finding is free; returned candidates are unverified patterns.
- **verify_bulk** — verifies a list of 2-10,000 addresses as one background job (1 credit per unique address). Returns a jobId immediately; the job takes minutes.
- **check_bulk_status** — progress and final summary counts for a bulk job. Free.
- **check_credits** — shows the remaining credit balance for the connected account.

## Usage guidance

- When the user asks "is this email valid / real / safe to send to", use `verify_email`.
- For a list of addresses (2+), use `verify_bulk` instead of looping `verify_email` — confirm the credit cost with the user first, then poll `check_bulk_status` and report only the summary counts.
- When the user knows a name and company but not the address, use `find_email` first, then offer to verify the most confident candidate with `verify_email` (1 credit each) — verify one at a time, stopping at the first deliverable result.
- Treat `risky` results as "send with caution" (catch-all domains, greylisting) — not as invalid.
- Report credits spent and the remaining balance after verification (responses include `creditsRemaining`).

## Authentication

Requests use the `CLEARBOUNCE_API_KEY` environment variable. If it is missing or the server returns an authentication error, tell the user to create a key at https://clearbounce.net/dashboard/api-keys (new accounts include free credits) and export it:

```sh
export CLEARBOUNCE_API_KEY="cb_..."
```
