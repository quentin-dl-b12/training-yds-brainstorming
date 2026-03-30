# Debrief: What did your implementation handle?

**Reflect on both rounds.** Go through the table below — for each vulnerability, ask yourself whether your Round 1 code addressed it, and whether Round 2 did.

---

## Does your implementation handle these?

| # | OWASP | Vulnerability | Round 1 | Round 2 |
|---|-------|--------------|---------|---------|
| 1 | A07 — Auth Failures | **Token TTL** — does the reset token expire after a short window (e.g. 15 min)? | ☐ | ☐ |
| 2 | A07 — Auth Failures | **Single-use invalidation** — is the token invalidated after a successful reset? | ☐ | ☐ |
| 3 | A04 — Insecure Design | **Rate limiting** — is `/reset-password/request` protected against brute-force or flooding? | ☐ | ☐ |
| 4 | A01 — Broken Access Control | **Email enumeration** — does the endpoint reveal whether an email exists in the system? | ☐ | ☐ |
| 5 | A09 — Logging Failures | **Audit logging** — are reset requests and confirmations logged for traceability? | ☐ | ☐ |
| 6 | A02 — Cryptographic Failures | **Token storage** — is the token stored as plaintext in the DB, or hashed? | ☐ | ☐ |

---

**Discussion (5 min)**

- Which gaps did Round 1 miss that Round 2 caught?
- Which did your agent miss even in Round 2?
