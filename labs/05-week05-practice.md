# Week 5 Practice — Light metrics as signals (2 h)

**Course:** Analysis and Assessment of Design Quality (MSc SE)  
**Pairs with:** `../sources/05-week05-lecture.tex`

---

## Goals

- Compute the same metrics on two designs  
- Interpret under a fixed brief  
- Write explicit caveats  

---

## Brief

**System:** internal **ExpenseApprovals** app (employees submit; managers approve; finance exports).  
**Top scenarios:**

1. **M1 Maintainability:** add a new approval policy field with ≤2 modules touched.  
2. **R1 Reliability:** if export service is down, approvals still work.  
3. **S1 Security:** employee cannot read another’s receipts via API.

---

## Two sketches (summaries)

### Design A — Modular monolith

Modules: `Submit`, `Approve`, `Policies`, `Export`, `Authz`.  
Deps: Submit→Policies, Approve→Policies, Approve→Authz, Export→Approve (read model).  
No cycles. Export is async queue consumer. Sample change “new policy field”: touches Policies (+ tests); Approve reads via API of Policies.

### Design B — Five “services”, one DB

Services: Submit, Approve, Policies, Export, Authz — all share one Postgres with cross-FKs.  
Sync HTTP: Submit→Approve→Policies→Authz on each submission.  
Export service joins all tables directly. Sample change “new policy field”: Submit, Approve, Policies, Export, Authz (+ migration).

---

## Part A — Metric sheet (50 min)

Compute for **A and B**:

| Signal | Design A | Design B |
|--------|----------|----------|
| Touch count for “new policy field” | | |
| Fan-in of Policies (approx.) | | |
| Fan-out of Approve (approx.) | | |
| Optional: instability \(I\) for Policies | | |

Show your counting assumptions.

---

## Part B — Interpretation (40 min)

1. Which design better supports M1 / R1 / S1? Cite structure, not only numbers.  
2. Where could metrics **mislead**?  
3. Write a **5-line caveats** paragraph for the report template.

---

## Part C — Finding draft (20 min)

Write one Major finding in Observation→Risk→Ask form, using a metric as *supporting* evidence.

---

## Done checklist

- [ ] Metric sheet for A and B  
- [ ] Interpretation vs scenarios  
- [ ] Caveats paragraph  
- [ ] One Major finding draft  
- [ ] Lecturer checkpoint
