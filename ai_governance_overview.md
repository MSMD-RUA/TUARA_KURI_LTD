# AgenticRail — AI Governance Overview (v2)

Operator: TUARA KURI LIMITED  
System: AgenticRail  
Date: 2026-05-01

---

## 1. One-Line Definition

AgenticRail is a deterministic AI execution control system that enforces whether an action is allowed to occur before it executes.

AI can propose actions.  
AgenticRail decides what is permitted.

---

## 2. System Architecture

Signal / Input  
→ Policy Mapping (MSMD Engine)  
→ Function Selection  
→ AgenticRail Gate  
→ Policy Validation  
→ ALLOW / DENY / HALT

Key capabilities (as of May 2026):

- 1M enforcement requests validated with zero errors (April 2026)
- 114,096 sealed sequences with cryptographic receipt chains
- Public verification portal: report.agenticrail.nz (no API key needed for demo sequences)
- Compliance matrix: 60+ frameworks across 4 continents (agenticrail.nz/compliance)
- Workflow Builder: industry-specific payload generation (agenticrail.nz/builder)
- Self-onboarding: Stripe → webhook → API key → welcome email (fully automated)
- Data Processing Agreement: agenticrail.nz/dpa
- EU AI Act Articles 9, 10, 11, 12, 13, 14, 72 directly satisfied
- South Korea AI Basic Act, DORA, US state AI employment laws covered
- Pricing: Free ($0), Growth ($299/mo), Scale ($799/mo), Enterprise (custom)
- Rate limits: 300/min demo, 3,000/min Growth, 30,000/min Scale
- Receipt retention: 7 days (Free), 30 days (Growth), 1 year (Scale), multi-year (Enterprise)
  
→ Execution (if allowed)  
→ Receipt / Audit Log

The system operates on structure, not content.

---

## 3. Governance Model

AgenticRail separates:

- **Policy Definition Layer** (MSMD Engine)
- **Execution Enforcement Layer** (AgenticRail)

This ensures:

- No AI system can act outside defined rules
- No action executes without validation

---

## 4. AI Lifecycle Enforcement

AgenticRail enforces a fixed 8-step decision sequence:

1. intake  
2. disruption  
3. instability  
4. state_read  
5. internal_driver  
6. execution  
7. boundary  
8. settle  

Rules:

- Steps cannot be skipped  
- Steps cannot be reordered  
- Each step must match a valid function  
- Each function allows only specific actions  

Any violation results in DENY or HALT.

---

## 5. Risk Management

AgenticRail prevents unsafe AI behaviour through:

- Strict allowlist validation of actions
- Deterministic step-by-step enforcement
- Boundary-stage interruption capability
- Fail-closed design (default = DENY or HALT)

If a condition is unclear or invalid:

→ The system halts execution

---

## 6. Audit & Traceability

AgenticRail maintains a full audit trail for every action:

- sequence_id  
- step / function  
- action_type  
- timestamp  
- decision outcome (ALLOW / DENY / HALT)  
- nonce (replay protection)

Additional properties:

- Replay attacks blocked via nonce validation  
- Completed sequences are sealed and cannot be reused  

This creates a tamper-resistant execution record.

---

## 7. Data Governance

AgenticRail follows strict data minimisation:

- Does not rely on user content
- Does not process prompts or AI outputs
- Operates on structural metadata only

Collected data is limited to:

- sequence identifiers  
- timestamps  
- action types  
- system outcomes  

Clients control all submitted data.

---

## 8. Roles & Responsibilities

- **System Owner**  
  TUARA KURI LIMITED  
  Responsible for system operation and governance

- **Risk Owner**  
  Defines policy maps and allowed behaviours

- **Security Owner**  
  Responsible for infrastructure, access control, and system integrity

- **Client (Controller of Use Case)**  
  Responsible for:
  - purpose of AI system
  - data submitted to the system
  - regulatory compliance of their application

AgenticRail does not determine AI purpose.

---

## 9. Security Model

Security controls include:

- TLS encryption in transit  
- Access control on system logs  
- Nonce-based replay protection  
- Deterministic validation before execution  

AgenticRail does not store sensitive data and is not designed as a storage system.

---

## 10. Continuous Improvement

System performance is monitored through:

- audit logs  
- error tracking  
- latency metrics  

Periodic review improves:

- policy accuracy  
- risk detection  
- system reliability  

---

## 11. Compliance Position

AgenticRail aligns with:

- ISO/IEC 42001 (AI Management Systems)
- GDPR (data minimisation & processing control)
- EU AI Act (risk control layer separation)

AgenticRail enforces compliance at the execution level, not just documentation.

---

## 12. Core Principle

If an action cannot be validated against policy:

→ It must not execute.

---

## 13. Closing Statement

AgenticRail does not attempt to make AI systems smarter.

It ensures AI systems act only within defined, auditable, and enforceable boundaries.