AgenticRail — Privacy Policy (v2.2)

Last updated: 2026-05-01

Operator: TUARA KURI LIMITED
Trading as: AgenticRail
Address: 431 Omanaia Road, RD 3, Kaikohe 0473, New Zealand
Email: hello@agenticrail.nz

1. Overview

This Privacy Policy explains how AgenticRail collects, uses, and handles data when you use the System.

AgenticRail is designed as a deterministic execution gate, not a data processing or storage platform.
We minimise data collection and avoid reliance on user content wherever possible.

2. What We Collect
2.1 Metadata (Primary)

We collect operational metadata required to run the System, including:

Sequence identifiers (IDs you provide or we generate)
Nonce values (unique random values per request)
Timestamps (milliseconds since epoch)
Step names and action types
System outcomes (ALLOW / HALT / DENY)
Request counts (for billing and usage)
2.2 Technical Data (Limited)

We may also collect:

IP addresses (processed transiently for security and debugging purposes and not retained beyond what is necessary for those functions)
Request headers (standard HTTP)
Error logs
Latency and performance metrics
2.3 What We Do NOT Intentionally Collect

AgenticRail is designed to avoid collecting personal data except where necessary (e.g., account email).
We do not rely on personal data for core system operation.

We do not intentionally collect:

Prompt content
Agent messages or responses
User-generated data payloads

Important: Clients control what they send to the System.
If you submit personal or sensitive data, it may pass through system infrastructure. You are responsible for avoiding this.

2.4 Sensitive Data Guidance

The System is not designed for processing sensitive personal data, including:

health data
financial account data
biometric or identity data

Clients must not submit such data unless they have implemented appropriate safeguards and legal basis.

3. How We Use Data

We use collected data to:

enforce sequence and policy rules
operate the execution gate
prevent replay attacks (nonce validation)
maintain system integrity
debug errors and improve performance
measure usage for billing

We do not use your data to:

train AI models
profile users
sell or share personal data for marketing

Legal basis (GDPR):

Legitimate interest (operating and securing the Service)
Contract performance (where account data such as email is provided)
4. Data Minimisation Principle

AgenticRail follows a strict principle:

If the System does not need the data to enforce a rule, it should not store it.

The System is designed to operate on structure (step, function, action_type) rather than content.

5. Data Retention
Technical logs (API calls) are retained for 90 days, then automatically deleted
Account information (email address, optional name) is retained while the account is active, plus a reasonable period for legal or security purposes

You may request deletion of your account data at any time (see Section 11).

6. Data Security

We implement reasonable technical and organisational measures, including:

Encryption in transit (TLS)
Access controls on logs and systems
Regular security reviews

However:

No system is completely secure.

Clients should not rely on AgenticRail for storage of sensitive data.

7. Data Breach Notification

In the event of a data breach affecting personal data, AgenticRail will notify affected users and relevant authorities where required by law.

8. Client Responsibility

Clients are solely responsible for:

ensuring they do not submit unnecessary personal data
complying with applicable privacy laws (e.g., NZ Privacy Act 2020, GDPR)
implementing safeguards for sensitive data

AgenticRail acts as a processor of structure, not a controller of user data.

9. International Use & Data Transfers

AgenticRail is operated from New Zealand but uses Cloudflare’s global network, which may process data in multiple countries.

By using the Service, you consent to this transfer.

For EU users, we rely on Cloudflare’s compliance mechanisms, including Standard Contractual Clauses.

10. EU AI Act & Privacy Context

AgenticRail does not determine the purpose of AI systems.

The Client is responsible for:

classification of their AI system
handling of personal data
compliance with privacy and AI regulations (including the EU AI Act)

AgenticRail provides enforcement logic, not data governance.

11. Your Rights (Including GDPR)

Depending on your jurisdiction, you may have the right to:

access your personal data
correct inaccurate data
request deletion (“right to be forgotten”)
restrict or object to processing
data portability

Because AgenticRail stores minimal personal data, these rights may be limited in practice.

To exercise your rights, contact:

📧 hello@agenticrail.nz

We aim to respond within 30 days.

New Zealand users may contact the Office of the Privacy Commissioner:
https://www.privacy.org.nz

12. Third-Party Services & Subprocessors

AgenticRail uses the following infrastructure providers:

Provider	Purpose	Privacy Policy
Cloudflare	API hosting, Durable Objects, R2 storage, KV, D1, networking	https://www.cloudflare.com/privacy
DeepSeek	AI compliance narrative generation (deepseek-chat, report worker only; processes enforcement summary statistics, not payload data)	https://www.deepseek.com/privacy
Stripe	Payment processing for subscription plans	https://www.stripe.com/privacy
Resend	Transactional email delivery (welcome emails, API key delivery)	https://www.resend.com/privacy

These providers process data only under contractual obligations and appropriate safeguards.

We do not sell or share user data for marketing.

A Data Processing Agreement (DPA) incorporating Standard Contractual Clauses is available at https://agenticrail.nz/dpa. The DPA takes effect automatically upon your first paid API call — no separate signature required.

13. Changes to This Privacy Policy

We may update this Privacy Policy at any time.

Material changes will be communicated via email (if provided) or through the Service.

Continued use of the System constitutes acceptance of updates.

14. Contact

AgenticRail — TUARA KURI LIMITED
431 Omanaia Road, RD 3, Kaikohe 0473, New Zealand
Email: hello@agenticrail.nz

By using AgenticRail, you acknowledge that you have read and understood this Privacy Policy.