# Week 1 Practice — What is design quality? (2 h)

**Course:** Analysis and Assessment of Design Quality (MSc Software Engineering)  
**Pairs with:** `../sources/01-week01-lecture.tex`  
**Materials:** English · bring paper or a shared doc

---

## Goals

- Distinguish *evaluable* design artifacts from decorative ones  
- Separate taste / preference from evidence-based quality claims  
- Map stakeholders and conflicting quality pressures for a short brief  

---

## Part A — Evaluability ranking (35 min)

Read the four short packs below (A–D). Rank them **1 = most evaluable** to **4 = least**.

| ID | Pack summary |
|----|----------------|
| **A** | 40 unnamed boxes, no legend, title “Cloud Native vNext” |
| **B** | Context + container view, three quality scenarios with response measures, one ADR (monolith vs split) |
| **C** | Bullet list: Kafka, K8s, GraphQL, “AI-powered”, no structure |
| **D** | Module sketch with named boundaries + dependency arrows, but goals only say “scalable and secure” |

**Deliverable:** ranking + 2–3 sentences justifying #1 and #4.

---

## Part B — Taste vs evidence (30 min)

Label each claim **T** (taste/preference), **E** (evidence-based quality claim), or **U** (underspecified / not yet evaluable). Rewrite every **U** into a stronger **E** form.

1. “I don’t like microservices.”  
2. “Given weekly VAT rule changes, three packages must change together on this sketch.”  
3. “The diagram colours are inconsistent.”  
4. “This is not enterprise-grade.”  
5. “p95 checkout ack exceeds 800 ms at peak in the stated scenario because payment is synchronous on the request path.”  
6. “Real engineers always use event sourcing.”

**Deliverable:** labels + rewritten U→E sentences.

---

## Part C — Stakeholder conflict map (40 min)

**Brief:** University course-registration system. Peak at semester start. Product wants new waitlist rules each term. Ops wants minimal downtime at peak. Security wants strict role checks on every write. Students care about clear errors and mobile UX.

1. List at least **five** stakeholder viewpoints.  
2. For each, note the **top quality pressure**.  
3. Draw a small conflict matrix (who vs who, over which attribute).  
4. Write one sentence: *As evaluator, I will judge designs by…*

**Deliverable:** viewpoint table + conflict matrix + stance sentence.

---

## Done checklist

- [ ] Ranking A–D with justification  
- [ ] Six claims labelled; U items rewritten  
- [ ] Stakeholder / conflict map  
- [ ] Personal evaluation stance sentence  
- [ ] Lecturer checkpoint (2 min)

---

## Stretch (if time)

Find a public architecture blog post; extract **one** testable quality scenario or explain why you cannot.
