EU AI Act Compliance Statement — AgenticRail (v2.1)

Last updated: 2026-04-09

Operator: TUARA KURI LIMITED
Trading as: AgenticRail
Jurisdiction: New Zealand (serving global users, including the European Union)
Contact: hello@agenticrail.nz

1. Overview

AgenticRail is a deterministic execution control system that validates, sequences, and either allows or halts actions submitted by client systems.

AgenticRail does not:

generate content or make autonomous decisions
rely on personal data for core system operation
act as a standalone high-risk AI system under the EU AI Act

AgenticRail does:

enforce step order, nonce uniqueness, and sequence sealing
provide verifiable, sealed sequence records
act as an infrastructure component used within AI systems, providing execution control and governance capabilities
2. System Classification

AgenticRail is positioned as:

an infrastructure component used within AI systems
an execution control / governance layer

AgenticRail:

does not determine the purpose of an AI system
does not define outcomes or decision logic
does not operate as a standalone AI application
3. Role Under the EU AI Act

Under the EU AI Act, AgenticRail acts as a technical enforcement layer used by the deployer of an AI system.

The Client using AgenticRail is considered the Deployer of the AI system and is responsible for regulatory classification and compliance.

AgenticRail:

is not the deployer
is not the operator of downstream AI decisions
is not responsible for domain-specific outcomes
does not place AI systems on the market or put them into service for a specific purpose

AgenticRail does not determine the purpose or risk level of your AI system.

4. Separation of Responsibility
AgenticRail responsibilities	Client responsibilities
Validating payload structure	Defining system purpose
Enforcing sequence order	Determining whether their system is high-risk
Applying policy constraints	Ensuring lawful use
Preventing invalid or out-of-order execution	Implementing human oversight
Providing verifiable sequence records	Ensuring data protection compliance (GDPR)

AgenticRail enforces structure. The Client defines meaning and use.

5. How We Support Your Compliance (EU AI Act Article Mapping)
EU AI Act Requirement	How AgenticRail Helps
Article 12 – Logging	Every action produces a verifiable, sealed sequence record
Article 14 – Human oversight	ALLOW decisions are not guarantees; client review is required
Article 17 – Quality management	Deterministic enforcement reduces unpredictability
Annex IV – Technical documentation	Logs and sequence records contribute to audit trails

AgenticRail does not replace compliance obligations.
It provides structured evidence that system actions followed a deterministic, auditable process.

6. High-Risk AI Systems — Your Obligations

If you use AgenticRail within a high-risk AI system (e.g., employment, credit scoring, critical infrastructure), you must:

conduct risk assessments
implement human oversight
ensure accuracy and robustness
maintain technical documentation
meet transparency obligations

AgenticRail:

does not provide compliance certification
does not replace required safeguards
must not be used as the sole control mechanism in high-risk contexts

AgenticRail does not accept liability for failure to comply with applicable laws.

7. Risk Mitigation by Design

AgenticRail contributes to safer AI operation through:

Mechanism	What it does
Deterministic enforcement	strict sequence validation, function/action matching, fail-closed behaviour
Execution constraints	prevents uncontrolled execution and step bypass
Replay protection	nonce validation prevents duplicate execution
Structural validation	rejects invalid or malformed actions

These mechanisms reduce:

unintended execution
inconsistent state transitions
uncontrolled system behaviour
8. Transparency and Explainability

AgenticRail provides:

explicit ALLOW / DENY / HALT outcomes
structured reason codes (e.g., REPLAY_NONCE, SEQUENCE_VIOLATION, SEALED_SEQUENCE, ACTION_NOT_ALLOWED, STALE_TIMESTAMP)
validation metadata (step, action_type, policy map references)

However:

AgenticRail does not explain domain-level decisions
AgenticRail does not interpret outcomes or assess correctness

Transparency at the application level remains the responsibility of the Client.

9. Human Oversight

AgenticRail does not replace human oversight.

Clients must:

review decisions where appropriate
implement escalation or fallback logic
ensure humans remain accountable for outcomes

AgenticRail is a control checkpoint, not a decision-maker.

10. Data Protection Alignment (GDPR)

AgenticRail is designed to:

minimise personal data processing
operate primarily on structural metadata
avoid reliance on content

As outlined in the Privacy Policy:

personal data should not be submitted unless necessary
Clients remain responsible for GDPR compliance

AgenticRail is designed to minimise personal data processing and does not rely on personal data for core system operation.

11. Prohibited and Unsafe Uses

AgenticRail must not be used:

as the sole safeguard in systems affecting health, finance, or legal outcomes
without independent validation layers
to bypass regulatory obligations

Unauthorised use may result in suspension of API access.

12. Limitations

AgenticRail:

does not assess fairness, bias, or societal impact
does not verify correctness of decisions
does not provide legal compliance guarantees

It enforces structure, not truth.

13. Ongoing Compliance Approach

AgenticRail will:

monitor developments in the EU AI Act
update policies and controls where relevant
maintain alignment with infrastructure-level obligations
publish updated versions of this statement as needed
14. Governing Principle

AgenticRail enforces structure, not meaning.
It determines whether an action is allowed.
It does not determine whether an action is correct, lawful, or appropriate.

A tool that supports compliant AI operation, not a compliance service or legal advisor.

15. Contact

For compliance-related enquiries:
📧 hello@agenticrail.nz

This statement is for informational purposes only and does not constitute legal advice.
Consult qualified legal counsel for your specific obligations under the EU AI Act and other applicable laws.