# Week 3 Practice — Design smells & structural health (2 h)

**Course:** Analysis and Assessment of Design Quality (MSc SE)  
**Pairs with:** `../sources/03-week03-lecture.tex`

---

## Goals

- Annotate architecturally significant smells with evidence  
- Propose checkable mitigations  
- Identify at least one plausible **false alarm**  

---

## Design pack — “MessyMart” (provided narrative)

Draw or interpret this structure:

- **Web UI** talks to **API Gateway**  
- **GodService** handles auth, catalogue, cart, pricing, recommendations, email, and admin reports  
- **GodService** ↔ **Billing** cyclic calls (JSON over HTTP both ways)  
- **Billing** and **GodService** share one **Postgres** schema (cross-table FKs)  
- **LegacyCSV** importer writes directly into UI session store  
- New “microservice” **Reco** reads the same DB tables; no owned data  
- Config: pricing rules copied in GodService, Billing, and a spreadsheet ops edits

---

## Part A — Annotation (45 min)

Find **≥4 smells**. For each:

| Field | Content |
|-------|---------|
| Smell name | from course catalog (or precise variant) |
| Evidence | what on the sketch supports it |
| Attribute risk | which scenarios likely hurt |
| Architectural significance? | Y/N + why |

---

## Part B — Mitigations (40 min)

For each smell: **one** mitigation that is checkable in ≤2 weeks (owner, artifact change, optional automated guard).

Avoid “rewrite everything.”

---

## Part C — False alarm debate (25 min)

Pick one candidate smell that might be **over-sensitive** for a 6-person v1. Argue both sides (2 min each) in pairs; write the resolution.

---

## Done checklist

- [ ] ≥4 annotated smells with significance  
- [ ] Mitigation list (1:1)  
- [ ] False-alarm write-up  
- [ ] Lecturer checkpoint

---

## Stretch

Compute rough fan-in for GodService vs Reco; interpret in one paragraph.
