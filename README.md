# Collaborative Test Plan — Dummy (Can be used for Lab‑1, Lab‑2, and Lab‑3)

> **Document ID:** TP‑COLLAB‑001  
> **Version:** 1.0  
> **Date:** <DD‑MMM‑YYYY>  
> **Course:** STQM / Software Testing Lab  
> **Team:** <Student A> (Roll <…>), <Student B> (Roll <…>)  
> **Tool for Collaboration:** <HackMD / Google Docs / CodeCollab> (version history enabled)

---

## 1. Purpose & Objectives
This test plan exists to (a) practice collaborative authoring/merging in a real‑time editor, and (b) validate a small feature set of a dummy web app. Lab‑1 and Lab‑2 will use this same plan for planning and basic execution; Lab‑3 adds **simultaneous co‑editing** and **version‑history analysis**.

**Objectives**
- Create and maintain a shared Test Plan with clear versioning.
- Execute a minimal but meaningful set of functional test cases.
- Intentionally create edit conflicts and resolve them using the tool’s features (comments, suggestions, merge, history).
- Capture observations about conflicts, latency, and editor behavior (for Lab‑3 submission).

---

## 2. Scope
**In‑Scope Features (Dummy App):**
1. **Login** (email + password)
2. **Add to Cart** (single item)
3. **View Cart** (shows item count and total)

**Out‑of‑Scope:** Payments, multi‑currency, coupon engine, security hardening.

---

## 3. References
- Product sketch: “Minimal Shop” (hypothetical)  
- Standards: IEEE 829/29119 (informal alignment)  
- Repo: <GitHub URL or local folder>

---

## 4. Roles & Responsibilities
- **Test Lead / Editor‑1 (Student A):** Owns structure, assigns cases, merges suggestions, final sign‑off.
- **Co‑Editor / Reviewer (Student B):** Adds test cases, executes steps, raises comments, proposes edits.
- **Observer (either):** During Lab‑3, records conflict events and resolutions.

---

## 5. Collaboration Setup & Ground Rules
- Tool: <HackMD / Google Docs / CodeCollab> with **real‑time cursors** and **version history** enabled.
- Naming: Branch major edits with headings like `<<A‑Draft>>`, `<<B‑Draft>>` before merge.
- Conflict Simulation Windows (Lab‑3):
  - **C1:** Both edit the **same paragraph** in Section 7.1 at the same time.
  - **C2:** Both modify **the same test case Expected Result**.
  - **C3:** One adds a **new table row** while the other sorts the table.
- Resolution order: Prefer **Suggestion/Track‑Changes** → **Comment discussion** → **Editor‑1 decision** → **Record in Section 11**.

---

## 6. Test Environment
- Browser: Chrome/Edge latest (desktop).
- Dummy app URL: <http://localhost:3000> or <mock URL>
- Test data:
  - Valid user: `user@example.com / P@ssw0rd!`
  - Invalid user: `nouser@example.com / wrong`
  - Item: `SKU‑DUMMY‑001`, Price: ₹100

---
    
## 7. Test Approach
- **Techniques:** Positive/negative functional tests; exploratory passes on cart behavior.
- **Entry Criteria:** App reachable; test data seeded; editors have access to the doc.
- **Exit Criteria:** All P1 test cases executed; defects logged; Lab‑3 observations completed.
- **Priority:** P1 critical login/cart; P2 display/cosmetics.

### 7.1 Test Case Summary
| ID   | Title                         | Priority | Pre‑conditions | Steps                                                                 | Expected Result                           |
|:----:|-------------------------------|:-------:|----------------|-----------------------------------------------------------------------|-------------------------------------------|
| TC‑01| Login with valid credentials  |   P1    | App running    | 1) Open Login  2) Enter valid email/pass  3) Submit                   | Redirect to Home; user name visible.      |
| TC‑02| Login with invalid password   |   P1    | App running    | 1) Open Login  2) Enter valid email + wrong pass  3) Submit          | Error message shown; no session created.  |
| TC‑03| Add one item to cart          |   P1    | Logged in      | 1) Open SKU‑DUMMY‑001  2) Click **Add to Cart**                       | Cart count = 1; toast confirms add.       |
| TC‑04| View cart total               |   P1    | Item in cart   | 1) Open Cart                                                           | Shows 1 item, total ₹100.                 |
| TC‑05| Cart persists during navigation|  P2    | Item in cart   | 1) Navigate Home → Product → Cart                                     | Cart count remains 1.                     |

> **Note (for Lab‑3 conflict test):** Both editors purposely change **TC‑03 Expected Result** at the same time (e.g., count becomes 2 vs 1) and then resolve via comments/suggestions. Capture outcome in Section 11.

---

## 8. Defect Management
- Tool: <GitHub Issues / Google Sheet>  
- Fields: ID, Title, Steps, Actual vs Expected, Severity (Blocker/Critical/Major/Minor), Status, Assignee, Evidence (screenshot link).

---

## 9. Metrics & Reporting
- Planned vs Executed test cases  
- Pass/Fail/Blocked counts  
- Defects by severity  
- Collaboration metrics (Lab‑3): number of conflicts, average time to resolve, number of comments per conflict

---

## 10. Schedule & Milestones
- **Lab‑1 (Planning):** Create this Test Plan; define 5–7 core cases; set up environment.  
- **Lab‑2 (Execution):** Run test cases; log defects; update plan.  
- **Lab‑3 (Collaboration):** Perform conflict simulations C1–C3; resolve using tool; export doc + observations.

---

## 11. Collaboration Observations (Fill during Lab‑3)
**Template per conflict:**
- **Conflict ID:** C1/C2/C3  
- **What we did simultaneously:** <e.g., edited same sentence in 7.1>  
- **Tool behavior seen:** <cursor lag, auto‑merge, suggestion prompts, conflict markers>  
- **Resolution path:** <discussion → accept change X>  
- **Time to resolve:** <mm:ss>  
- **Lessons learned:** <e.g., use suggestions for high‑risk sections>

**Example (C2):** Both changed TC‑03 Expected Result. Tool showed inline suggestion threads; Editor‑1 accepted “Cart count = 1; toast confirms add.” Resolution 1m 30s. Lesson: Lock the table or use Suggest mode.

---

## 12. Risks & Mitigations
| Risk                                   | Impact        | Likelihood | Mitigation                                  |
|----------------------------------------|---------------|------------|----------------------------------------------|
| Merge overwrite due to rapid edits     | Loss of work  | Medium     | Use Suggest mode; frequent named versions.   |
| Network latency                        | Mis‑ordered edits | Medium  | Pause after each paragraph; refresh history. |
| Ambiguous ownership                    | Conflicting decisions | Low | Editor‑1 final call; document in Section 11. |

---

## 13. Deliverables
- **This Test Plan** (MD/PDF)  
- **Executed results** (updated table + check marks or a short run log)  
- **Defect log** (link)  
- **Collaboration observations** (Section 11 filled)  
- **Export & GitHub push**: `/docs/Test_Plan_Collab.pdf` and `/docs/observations.md`

---

## 14. Approval
- **Editor‑1 (Student A):** Name, Signature, Date  
- **Co‑Editor (Student B):** Name, Signature, Date

---

## 15. Version History
| Version | Date           | Author     | Description             |
|--------:|----------------|------------|-------------------------|
| 0.1     | <DD‑MMM‑YYYY>  | Student A  | Initial draft created.  |
| 0.9     | <DD‑MMM‑YYYY>  | Student B  | Added cases; reviewed.  |
| 1.0     | <DD‑MMM‑YYYY>  | Student A  | Finalized for Labs 1–3. |
    
