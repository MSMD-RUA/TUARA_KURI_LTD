MSMD × AgenticRail — HANDOFF (Post-Audit)

Date: 2026-04-16
Status: Live system, clean repo, hardened gate, entering proof + product phase
Updated: 2026-04-21 — wrapper shipped, open items resolved

1) One-line truth

AgenticRail is a working enforced system:
wrapper → gate → core → sequence → receipt is live and stable.

2) Current state

Repo health:

No TODO/FIXME debt in production files
No stubbed or incomplete handlers
Clean separation: wrapper / gate / core / dashboard / report

System flow:
Client → Wrapper (Bearer auth, D1, rate limit, executor) → Gate → Core (DO) → Policy → Enforcement → Receipt → Dashboard

Gate (public layer):

Auth (prod + demo keys)
Content-type + size validation
Canonicalization (NFKC + zero-width strip)
Poison hardening (roles, base64, YAML anchored)
Safe forward to core
ALLOW-only caching

Core (enforcement):

Strict 8-step sequence
step === function enforcement
action_type allowlist per function
Durable Object control:
order enforcement
replay protection
sealed sequence
Receipt generation + storage

Dashboard:

KV stats
R2 receipts
Verify endpoint wired to gate
UI working
3) Recent upgrades (confirmed in code)
Cache fix: only ALLOW responses cached
timingSafeEq fixed: no early return, padded compare
YAML poison check: anchored regex (no false positives)
UI cleanup: duplicate footer removed, CSS fixed
/verify handling clarified (poison skip documented)

These are real correctness + security improvements.

4) What is solid (locked)
8-step MSMD spine enforcement
Gate → core binding
Durable Object sequencing
Replay + seal guarantees
Receipt system working
Dashboard visibility working

This is a complete enforcement loop.

5) What was still open at 2026-04-16 — current status

A) Gate-level validation — OPEN (unchanged)
Core still handles unknown function / invalid action_type.
Gate HALT-before-core remains a future optimisation.

B) Proof layer — OPEN
100k load test on current deploy not yet rerun.

C) Product layer — PARTIALLY DONE
dashboard VERIFY button — SHIPPED (GATE service binding, GATE_API_KEY set)
ledger export (CSV / JSON) — still open

D) Production hardening — SHIPPED
per-key rate limiting — SHIPPED (RateLimiter Durable Object, 60 req/min demo per IP, 300 req/min prod per key)
health endpoint — available at GET /v1/health on wrapper
external logging — D1 usage_logs table writes on every request

Additional work shipped since 2026-04-16:
Wrapper (agenticrail-wrapper) deployed as public front door — Bearer auth, D1, demo key bypass, executor
Demo receipt isolation — receipts/demo/ R2 prefix, 30-day auto-purge cron
Timestamp freshness enforcement — STALE_TIMESTAMP (±300s) added to core
Report worker (slp8-report) deployed — compliance report generator, Claude narrative, chain verification
wrangler.toml compatibility_date updated to 2026-04-17 across all workers
Same-account Worker-to-Worker calls now use service bindings throughout (avoid CF error 1042)
6) What is NOT a problem

Do not spend time here:

architecture (correct)
route completeness (done)
policy/core linkage (working)
deployment structure (clean)
enforcement model (proven)

This is not a build problem anymore.

7) Working rules
Gate = fast rejection + hardening
Core = deterministic enforcement
Dashboard = visibility only

Never:

move enforcement into gate incorrectly
bypass policy maps
break step/function identity
create duplicate core paths
8) Current phase (as of 2026-04-21)

You are here:
BUILD → WORKING SYSTEM → PROOF + HARDENING → CUSTOMER READY

Wrapper is live. Rate limiting is live. Demo isolation is live. Compliance report is live.
Next phase is load proof and first customer.

9) Remaining open items
Run 100k load test on current deploy (wrapper → gate → core path)
Add gate-level HALT before core for unknown function / invalid action_type
Ledger export (CSV / JSON)

10) Summary
Repo: clean
System: working (wrapper → gate → core)
Gate: hardened
Core: enforcing
Wrapper: live (Bearer auth, D1, rate limiting, executor)
Dashboard: live (dual-mode proof + operator)
Report: live (compliance narrative, chain verification)
Risk: low
Unknowns: performance under load at wrapper layer
Final line

AgenticRail is no longer being built — it is being proven, tightened, and prepared for real use.