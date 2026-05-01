AgenticRail — API Terms of Use (v2.3)

Last updated: 2026-05-01

Operator: TUARA KURI LIMITED
Trading as: AgenticRail
Address: 431 Omanaia Road, RD 3, Kaikohe 0473, New Zealand
Email: hello@agenticrail.nz

These API Terms govern access to and use of the AgenticRail API (“API”).
They apply in addition to the AgenticRail Terms of Service and Privacy Policy. Capitalised terms not defined here have the meanings given in the main Terms of Service.

1. Purpose of the API

The AgenticRail API provides a deterministic execution gate that:

validates incoming actions
enforces sequence order
applies policy constraints
returns ALLOW or DENY/HALT decisions

The API does not generate actions or guarantee outcomes.

2. API Keys & Account

Access to the API requires a valid API key.

You are responsible for all activity under your key
Do not share, expose, or embed keys in public code (e.g., client-side JavaScript, mobile apps)
You must promptly notify us if your key is compromised

AgenticRail may:

rotate keys
revoke keys
limit or suspend access

at any time to protect system integrity.

3. Request Contract (Required Payload)

All API requests must follow the documented structure.

Minimum required payload:

{
  "schema_version": "1.0",
  "model_id": "MSMD",
  "sequence_id": "string",
  "step": "string",
  "function": "string",
  "action_type": "string",
  "nonce": "string",
  "ts_ms": 0,
  "action": "string",
  "inputs": {}
}
Required rules:
step MUST equal function
nonce MUST be unique per request (UUID or equivalent recommended)
action_type MUST be allowed for the given step/function
sequence_id MUST be consistent within a sequence

Requests that do not meet this contract will be rejected.

4. Deterministic Enforcement

The API enforces:

strict ordered sequence (8-step spine)
function validation
action-type allowlists
nonce replay protection
sequence sealing after completion

Violations result in:

DENY
HALT
or structured error responses

The API is designed to:

fail closed, not fail open.

5. Sequence Rules
Steps must follow the defined order
Steps cannot be skipped, repeated, or reordered
Each sequence must use fresh nonces
Once a sequence reaches the final state (settle), it is sealed

After sealing:

further requests on that sequence will be rejected
6. Response Model

Responses include:

decision: ALLOW or DENY/HALT
reasons: array of reason codes
meta: validation metadata (step, action_type, etc.)

An ALLOW decision means:

the action passed current policy constraints

It does NOT mean:

the action is correct
the action is safe
the action should be executed without human review
7. Error Handling & Reason Codes

Clients must handle errors correctly.

Common reason codes:

Code	Meaning
DENY	Action not permitted by policy
HALT	Sequence violation or invalid state
REPLAY_NONCE	Nonce already used for this sequence
SEQUENCE_VIOLATION	Step order incorrect (skip or repeat)
SEALED_SEQUENCE	Sequence already completed (settle)
ACTION_NOT_ALLOWED	action_type not valid for the current function/step
STALE_TIMESTAMP	ts_ms is more than 300 seconds from server time

Clients must not assume retries will succeed without correcting the underlying issue.

8. HTTP Status Codes

The API may use standard HTTP status codes, including:

200 — Request processed successfully (ALLOW or DENY decision returned)
400 — Invalid request structure
401 / 403 — Authentication or API key issues
429 — Rate limit exceeded
500 — Internal server error

Clients must not rely solely on HTTP status codes and should always inspect the response body.

9. Rate Limits & Usage

Tier limits (as published at agenticrail.nz/#pricing):

Free tier (demo key): 10,000 requests per calendar month at no charge. 300 requests per minute per IP.
Growth tier ($299/month): 500,000 requests per calendar month. 3,000 requests per minute per key.
Scale tier ($799/month): 5,000,000 requests per calendar month. 30,000 requests per minute per key.
Enterprise: custom limits, volume discounts, and SLA guarantees — contact hello@agenticrail.nz

Rate limits are enforced by a single-threaded Durable Object per rate-limit key — no race conditions. Demo key users are rate-limited per IP address. Production key users are rate-limited per API key.

Exceeding your tier's request limit or rate limit may result in:

throttling (HTTP 429)
temporary denial
suspension of access

Tier limits reset at the start of each calendar month. Unused requests do not carry over.

We may change rate limits and pricing with reasonable notice. The AgenticRail website (agenticrail.nz) is the authoritative source for current pricing, plans, and tiers.

Self-onboarding: Growth and Scale plans are available for immediate purchase via Stripe payment links on the pricing page. Upon successful payment, an API key is generated and delivered by email automatically. No human intervention required.

10. Idempotency and Retries

Requests are not idempotent by default.

Reusing a nonce will result in REPLAY_NONCE errors
Each request must use a new nonce

Clients must:

generate unique nonces per request
design retry logic carefully
avoid blind retries
11. Client Responsibilities

Clients must:

validate all API responses before execution
implement fallback or safe failure behaviour
ensure compliance with applicable laws (including the EU AI Act)
ensure safe use in their domain

AgenticRail is a control layer, not a decision engine.

12. Prohibited Use

You must not:

attempt to bypass sequence enforcement
send malformed or adversarial payloads to break the system
reverse engineer API behaviour
use the API to build competing enforcement systems
conduct unauthorised stress testing

Violation may result in immediate suspension.

13. Security

You must:

protect API keys
rotate keys if compromised
use secure transport (HTTPS only)
avoid submitting personal or sensitive data unless appropriate safeguards and legal basis are in place

AgenticRail is not a secure data storage system.

14. Availability & Changes

The API is provided “as is” and “as available.”

We do not guarantee uptime or response times, but we use reasonable efforts to maintain availability.

The API may evolve over time, including:

new validation rules
updated payload requirements

Backward compatibility is not guaranteed.
Breaking changes will be notified with reasonable notice (at least 30 days where possible).

15. API Versioning

The API may evolve over time.

Versioning is indicated via the schema_version field
Clients are responsible for maintaining compatibility
Deprecated versions may be removed with reasonable notice
16. Suspension & Termination

We may suspend or terminate API access immediately if:

you breach these API Terms or the main Terms
your use poses a security risk
your use disrupts the API for others
you fail to pay outstanding fees within 15 days of notice

Upon termination:

API keys will be revoked
outstanding fees become immediately due
17. Limitation of Liability

These API Terms are subject to the Limitation of Liability clause in the main Terms of Service.

In summary:

liability is capped at fees paid in the previous 12 months or NZ$100 (whichever is greater)
no liability for indirect or consequential damages

Use of the API is at your own risk.

18. Governing Law

These API Terms are governed by the laws of New Zealand.
Disputes shall be resolved in the courts of New Zealand.

19. Governing Principle

The API enforces structure, not truth.

It decides what is allowed.
It does not decide what is correct.

20. Contact

For API access, key management, or questions:

📧 hello@agenticrail.nz

By using the AgenticRail API, you acknowledge that you have read, understood, and agree to be bound by these API Terms of Use, together with the Terms of Service and Privacy Policy.