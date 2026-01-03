---
title: LC-TEST-16 — Algorithm Test (V3)
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This document trains **engineering judgment**, not syntax.

Real interviews test:
- how you **combine conditions**
- how you **eliminate wrong paths**
- how you **protect systems with logic**

If you master this → you think like a **senior Python engineer**.

---

# 🧠 Python Algorithm Thinking — 20 Advanced Logic Puzzles

Rules:
- No shortcuts
- Read carefully
- Think in **conditions**

---

## 🟢 Puzzle 1 — Smart API Throttling

API request has:
```python
requests = [
    {"user":"A","count":90,"premium":False},
    {"user":"B","count":120,"premium":True},
    {"user":"C","count":120,"premium":False},
]
```

**Rules:**
- Block if `count > 100`
- BUT allow if `premium == True`

**Task:**  
Return users that are **blocked**.

<details>
<summary>✅ Solution</summary>

```python
blocked = []

for r in requests:
    if r["count"] > 100 and not r["premium"]:
        blocked.append(r["user"])

print(blocked)
```

</details>

---

## 🟢 Puzzle 2 — Secure Login Validator

A login attempt is valid if:
- username exists
- password matches
- account is active **OR** admin override is true

```python
user = {
  "exists": True,
  "password_ok": True,
  "active": False,
  "admin_override": True
}
```

**Task:**  
Return `True / False`.

<details>
<summary>✅ Solution</summary>

```python
valid = (
    user["exists"]
    and user["password_ok"]
    and (user["active"] or user["admin_override"])
)

print(valid)
```

</details>

---

## 🟢 Puzzle 3 — Production Error Escalation

Error should be escalated if:
- severity ≥ 8
- AND (service is `"payment"` OR `"auth"`)
- AND NOT during maintenance

```python
error = {"sev":9,"service":"payment","maintenance":False}
```

<details>
<summary>✅ Solution</summary>

```python
if (
    error["sev"] >= 8
    and error["service"] in ("payment","auth")
    and not error["maintenance"]
):
    print("Escalate")
```

</details>

---

## 🟡 Puzzle 4 — Smart Cache Usage

Use cache if:
- cache exists
- AND (data fresh OR forced_cache=True)

```python
cache = {"exists":True,"fresh":False}
forced_cache = True
```

<details>
<summary>✅ Solution</summary>

```python
use_cache = (
    cache["exists"]
    and (cache["fresh"] or forced_cache)
)

print(use_cache)
```

</details>

---

## 🟡 Puzzle 5 — Fraud Detection Rule

Transaction is suspicious if:
- amount > 10_000
- OR (amount > 3_000 AND country not trusted)
- AND NOT internal_transfer

```python
tx = {"amount":5000,"trusted":False,"internal":False}
```

<details>
<summary>✅ Solution</summary>

```python
if (
    (tx["amount"] > 10000
    or (tx["amount"] > 3000 and not tx["trusted"]))
    and not tx["internal"]
):
    print("Suspicious")
```

</details>

---

## 🟡 Puzzle 6 — Multi-Level Access Control

Access granted if:
- role is `"admin"`
- OR (role `"dev"` AND env `"staging"`)
- OR (role `"viewer"` AND read_only=True)

```python
user = {"role":"dev","env":"staging","read_only":False}
```

<details>
<summary>✅ Solution</summary>

```python
if (
    user["role"] == "admin"
    or (user["role"] == "dev" and user["env"] == "staging")
    or (user["role"] == "viewer" and user["read_only"])
):
    print("Access granted")
```

</details>

---

## 🟡 Puzzle 7 — Intelligent Retry Logic

Retry request if:
- status >= 500
- AND retries < 3
- AND NOT timeout

```python
req = {"status":502,"retries":2,"timeout":False}
```

<details>
<summary>✅ Solution</summary>

```python
if (
    req["status"] >= 500
    and req["retries"] < 3
    and not req["timeout"]
):
    print("Retry")
```

</details>

---

## 🔵 Puzzle 8 — Data Pipeline Drop Rule

Drop record if:
- missing required field
- OR invalid format
- OR (late arrival AND not backfill)

```python
rec = {"missing":False,"invalid":False,"late":True,"backfill":False}
```

<details>
<summary>✅ Solution</summary>

```python
if (
    rec["missing"]
    or rec["invalid"]
    or (rec["late"] and not rec["backfill"])
):
    print("Drop")
```

</details>

---

## 🔵 Puzzle 9 — Alert Noise Reduction

Send alert if:
- severity ≥ 7
- AND (new_error OR error_rate > threshold)
- AND NOT already_alerted

<details>
<summary>✅ Solution</summary>

```python
if (
    sev >= 7
    and (new_error or rate > threshold)
    and not alerted
):
    print("Alert")
```

</details>

---

## 🔵 Puzzle 10 — Smart Autoscaling Decision

Scale up if:
- cpu > 70 AND mem > 70
- OR queue > 1000
- AND NOT maintenance

<details>
<summary>✅ Solution</summary>

```python
if (
    ((cpu > 70 and mem > 70) or queue > 1000)
    and not maintenance
):
    print("Scale up")
```

</details>

---

## 🔴 Puzzle 11 — Complex Log Filtering

Keep log if:
- level is ERROR or WARN
- AND service not deprecated
- AND (env is prod OR flagged)

<details>
<summary>✅ Solution</summary>

```python
if (
    log["level"] in ("ERROR","WARN")
    and not log["deprecated"]
    and (log["env"] == "prod" or log["flagged"])
):
    kept.append(log)
```

</details>

---

## 🔴 Puzzle 12 — Deployment Gate

Allow deploy if:
- tests passed
- AND security approved
- AND (low_risk OR manager_approved)

<details>
<summary>✅ Solution</summary>

```python
if (
    tests_ok
    and security_ok
    and (low_risk or manager_ok)
):
    print("Deploy")
```

</details>

---

## 🔴 Puzzle 13 — Feature Flag Evaluation

Enable feature if:
- flag_on
- AND user_beta
- AND NOT region_blocked

<details>
<summary>✅ Solution</summary>

```python
if flag and beta and not blocked:
    enable()
```

</details>

---

## 🔴 Puzzle 14 — Dead Letter Queue Rule

Send to DLQ if:
- retries exhausted
- OR malformed payload
- AND NOT manual_override

<details>
<summary>✅ Solution</summary>

```python
if (
    (retries == 0 or malformed)
    and not manual_override
):
    send_dlq()
```

</details>

---

## 🔴 Puzzle 15 — AI Model Safety Gate

Allow response if:
- confidence > 0.9
- AND NOT hallucinated
- AND (verified_source OR human_reviewed)

<details>
<summary>✅ Solution</summary>

```python
if (
    conf > 0.9
    and not hallucinated
    and (verified or reviewed)
):
    respond()
```

</details>

---

## 🟣 Puzzle 16 — Distributed Lock Acquisition

Acquire lock if:
- lock free
- OR expired
- AND requester authorized

<details>
<summary>✅ Solution</summary>

```python
if (
    (free or expired)
    and authorized
):
    acquire()
```

</details>

---

## 🟣 Puzzle 17 — Multi-Region Failover

Failover if:
- primary down
- AND secondary healthy
- AND NOT maintenance_window

<details>
<summary>✅ Solution</summary>

```python
if primary_down and secondary_ok and not maintenance:
    failover()
```

</details>

---

## 🟣 Puzzle 18 — Abuse Detection

Block user if:
- reports > 5
- AND (spam OR harassment)
- AND NOT verified_user

<details>
<summary>✅ Solution</summary>

```python
if reports > 5 and (spam or harassment) and not verified:
    block()
```

</details>

---

## 🟣 Puzzle 19 — Financial Transaction Approval

Approve if:
- balance sufficient
- AND not frozen
- AND (trusted_merchant OR small_amount)

<details>
<summary>✅ Solution</summary>

```python
if balance >= amount and not frozen and (trusted or amount < 50):
    approve()
```

</details>

---

## 🟣 Puzzle 20 — Senior-Level Thinking

**Explain (no code):**  
Why grouping conditions incorrectly can cause:
- security bugs
- outages
- financial loss

<details>
<summary>✅ Solution</summary>

Because logical precedence mistakes (`and` / `or`) can:
- bypass security
- trigger actions unintentionally
- scale systems incorrectly

Senior engineers design logic **defensively**.
</details>

---

## 🏁 Final Truth

If you master **logic composition**,  
you master **engineering power**.

Teach this.
Spread this.
Make engineers better.

---