AgenticRail — Terms of Service (v1.4)

Last updated: 2026-05-02

Operator: TUARA KURI LIMITED
Trading as: AgenticRail
Address: 431 Omanaia Road, RD 3, Kaikohe 0473, New Zealand
Email: hello@agenticrail.nz

1. Overview

AgenticRail is a deterministic execution control system that validates, sequences, and either allows or halts actions submitted by clients.

AgenticRail does not generate actions.
AgenticRail does not guarantee correctness.
AgenticRail only enforces whether an action is allowed to proceed.

Use of the System constitutes acceptance of these Terms.

2. Definitions
Term	Definition
System	AgenticRail (wrapper + gate + core + sequence enforcement)
Client	Any user, service, or application sending requests to the System
Sequence	An ordered set of steps enforced by the System
Action	A proposed operation submitted for validation
ALLOW	The System permits the Action to proceed
DENY	The System blocks the Action due to a policy or sequence constraint; the Sequence may continue from a valid state
HALT	The System stops execution due to a sequence violation, invalid state, or terminal error; the Sequence cannot proceed
Policy	The rule set used to validate Actions (e.g., MSMD policy maps)
3. Nature of the System

AgenticRail is:

a deterministic validation layer
an execution gate
a policy enforcement engine

AgenticRail is not:

an advisor
a decision-maker
a guarantee of correctness
a substitute for human judgement
4. No Guarantee of Outcomes

AgenticRail does not guarantee:

correctness of any Action
safety or suitability of any Action
completion of any Sequence

An Action being ALLOWED does not mean it is correct, safe, or appropriate.
It only means the Action passed the current Policy constraints.

5. Client Responsibility

The Client is solely responsible for:

all inputs submitted to the System
all Actions executed after an ALLOW decision
all consequences arising from those Actions

The Client must:

validate outputs independently
ensure compliance with applicable laws (including the EU AI Act)
ensure safe execution in their own environment
6. Deterministic Enforcement

AgenticRail enforces:

strict step ordering
function / Action matching
allowed Action types
replay protection (nonce)
sequence sealing after completion

If any rule is violated, the System will HALT or DENY the Action.
No override is available.

7. Sequence Rules
Sequences must follow the defined order
Steps cannot be skipped, repeated, or reordered
Once a Sequence reaches the final state (“settle”), it is sealed
Sealed Sequences cannot be reused

Violations will result in error codes such as:

SEQUENCE_VIOLATION
REPLAY_NONCE
SEALED_SEQUENCE
ACTION_NOT_ALLOWED
STALE_TIMESTAMP
8. Action Validation

All Actions must:

include a valid function
match the current step
use an allowed action_type
conform to the active Policy

Invalid Actions will be rejected.
The System may return an error without detailed explanation.

9. Denial Behaviour — Fail Closed

AgenticRail may:

deny requests
halt Sequences
return errors
stop execution without recovery

Denial may occur due to:

invalid structure
policy mismatch
sequence violation
replay detection
system constraints

The System is designed to:

fail closed, not fail open.

10. Logging and Records

AgenticRail is designed to minimise collection of personal data.

The System primarily logs metadata required for operation, including:

Sequence IDs
timestamps
action types
outcomes (ALLOW / HALT / DENY)

AgenticRail does not rely on logging user content for normal operation.

However, Clients must not rely on the System as a secure or confidential storage mechanism.
Clients should avoid submitting sensitive personal, financial, or regulated data unless appropriate safeguards are in place.

Receipt retention periods per plan tier:

Free: 7 days | Growth: 30 days | Scale: 1 year | Enterprise: multi-year (contractual)

Clients may request deletion of their account data by contacting hello@agenticrail.nz. Enforcement receipts are retained for the duration of the plan's retention period to enable compliance reporting and chain verification.

A Data Processing Agreement (DPA) incorporating Standard Contractual Clauses is available at https://agenticrail.nz/dpa. The DPA takes effect automatically upon your first paid API call — no separate signature required.

Logs exist to:

maintain system integrity
provide traceability
support debugging and analysis

The Client should assume interactions are recorded for operational purposes.

11. Misuse and Adversarial Testing

The Client must not:

intentionally bypass sequence rules
attempt to exploit policy gaps
flood or degrade the System
submit malformed or malicious payloads

Adversarial testing is only permitted if:

explicitly authorised in writing
conducted within defined boundaries
12. Availability

AgenticRail:

may change without notice
may be unavailable at any time
may evolve policy definitions

No uptime guarantees are provided. AgenticRail uses reasonable efforts to maintain availability but does not commit to any specific uptime target or response time.

13. Pricing and Fees

Pricing for the System is published on the AgenticRail website and notified to Clients before any charges apply. The website (agenticrail.nz) is the authoritative source for current pricing, plans, and tiers.

AgenticRail may change pricing at any time. Material changes will be notified at least 30 days in advance.

All fees are exclusive of GST or other taxes.
Clients are responsible for any applicable taxes.

14. Limitation of Liability

To the maximum extent permitted by New Zealand law:

AgenticRail’s total liability arising out of or related to these Terms or the System is limited to the greater of:

the fees paid by the Client in the 12 months preceding the event; or
NZ$100

AgenticRail is not liable for:

indirect, incidental, special, consequential, or punitive damages
loss of profits, data, or business interruption

AgenticRail is not liable for any claims arising from use of the System in high-risk contexts without adequate safeguards.

15. No Warranties

The System is provided “as is” and “as available.”

AgenticRail makes no warranties, express or implied, including:

fitness for a particular purpose
reliability or availability
accuracy of outcomes

Use of the System is at the Client’s own risk.

16. High-Risk Use & EU AI Act

The Client is the deployer of any AI system using AgenticRail.

The Client is solely responsible for determining whether their use constitutes a high-risk AI system under applicable laws (including the EU AI Act).

The Client must implement appropriate:

human oversight
risk management
compliance controls

AgenticRail:

is a general-purpose enforcement tool
does not provide legal or compliance advice

AgenticRail must not be used as the sole control mechanism in any system where failure could result in:

harm to individuals
financial loss
legal or regulatory impact

By using the System, the Client accepts full responsibility for compliance.

17. Indemnification

The Client agrees to indemnify, defend, and hold harmless AgenticRail and its directors, employees, and agents from any claim arising out of:

breach of these Terms
violation of any law or regulation
use of the System in high-risk contexts without safeguards
infringement of third-party rights
18. Intellectual Property — No Training

The Client retains ownership of their inputs and data.

AgenticRail retains all rights to:

the System
source code
algorithms
documentation

The Client may not:

reverse engineer or decompile the System
extract source code
use the System to build or train competing products
19. Suspension and Termination

AgenticRail may suspend or terminate access to the System at any time:

for misuse
for breach of these Terms
to protect system integrity

Termination may occur without prior notice where necessary.

20. Governing Law & Jurisdiction

These Terms are governed by the laws of New Zealand.

Any disputes shall be resolved in the courts of New Zealand.

For Clients in the European Union, mandatory consumer protections still apply.

21. Modifications

These Terms may be updated at any time.

Material changes will be notified at least 30 days in advance.

Continued use of the System constitutes acceptance of updated Terms.

22. Governing Principle

AgenticRail enforces structure, not truth.

The System controls whether an Action is allowed.
The Client remains responsible for what happens next.

23. Contact

AgenticRail — TUARA KURI LIMITED
431 Omanaia Road, RD 3, Kaikohe 0473, New Zealand
Email: hello@agenticrail.nz

By using AgenticRail, you acknowledge that you have read, understood, and agree to be bound by these Terms.