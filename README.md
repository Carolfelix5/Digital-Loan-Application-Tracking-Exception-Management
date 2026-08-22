# Digital Loan Application, Tracking & Exception Management
### A Business Analysis Portfolio Case Study — FinNova Digital Finance (Fictional)

**Author:** Carol Felix, Business Analyst
**Methodology:** Agile/Scrum · Status: In Progress (Sprint 1 of pilot)

---

## About This Project

This is a self-directed case study built to practice the end-to-end business analyst lifecycle on a realistic FinTech scenario, applying BABOK's Core Concept Model (BACCM) and six Knowledge Areas throughout. FinNova Digital Finance, all stakeholders, and all data in this repository are fictional. Every artifact — requirements, business rules, test results, and defects — was self-authored to demonstrate business analysis process and documentation skill, not the output of a production deployment.

This case study is presented **in progress, not completed** — the pilot is mid-sprint, several requirements are not yet built, and the primary success metric isn't measurable yet. That's intentional

---

## The Problem

FinNova's digital loan platform captures applications digitally, but everything downstream is manual: document validation, exception handling, SLA monitoring, and customer communication. This isn't just slow — applications can genuinely stall without anyone noticing, since a missing document, an unresolved exception, and a simple queue backlog all look identical from the outside today. Two consequences drove this project: inconsistent, undocumented exception handling, and customers with zero visibility into where their application stands.

Full context: [`01_Business_Case.docx`](./01_Business%20Case.pdf) · [`02_Project_Charter.docx`](./02_Project%20Charter.pdf)

---

## The Solution: Four Connected Capabilities

| Pillar | What It Solves |
|---|---|
| **1. Application Tracking** | Real-time, centralized status — for Operations and customers — replacing fragmented spreadsheets |
| **2. SLA Tracking** | Per-stage SLA timers and proactive at-risk alerts, replacing an unverified "48h estimate" |
| **3. Document Management** | Automated detection and follow-up on missing documents, replacing informal one-off emails |
| **4. Exception Management** | Rules-based classification and assignment, with a mandatory, immutable audit trail |

This framing came directly out of elicitation — the original scope draft centered too narrowly on exception handling alone; stakeholder interviews surfaced that tracking, SLA visibility, and document follow-up were equally significant, unaddressed problems. See [`04_Elicitation_Notes.docx`](./04_Elicitation%20Notes.pdf) for how that reframing happened.

---

## Repository Structure

```
/docs
  01_Business_Case.docx
  02_Project_Charter.docx
  03_Stakeholder_Register.xlsx
  04_Elicitation_Notes.docx
  05_AsIs_Process_Diagram.png
  06_Pain_Points_Root_Cause.xlsx
  07_ToBe_Process_Diagram.png
  08_Gap_Analysis.xlsx
  09_BRD.docx
  10_FRD.docx
  11_Business_Rules_Document.xlsx
  12_User_Stories_and_Acceptance_Criteria.xlsx
  13_Prioritization_MoSCoW.xlsx
  14_Jira_Board_Mock.png
  15_RTM.xlsx
  16_UAT_Test_Cases.xlsx
  17_Defect_Log.xlsx
  18_Solution_Evaluation.docx
  19_KPI_Report.xlsx
/README.md   <- this file
```

---

## Process Flow

**AS-IS (Current State)**
![AS-IS Process](./05_AS-%20IS%20Process.drawio.pdf)

**TO-BE (Target State)**
![TO-BE Process](./07_TO-%20BE%20Process.drawio.pdf)

---

## Current Status (Sprint 1, Personal Loan Pilot)

| | |
|---|---|
| User stories completed | 4 / 13 |
| User stories in active testing | 2 / 13 |
| UAT test cases passed | 4 / 13 |
| Defects logged | 5 (3 resolved, 2 open) |
| Primary KPI (48h → 24h TAT) | Not yet measurable — SLA Tracking pillar still in development |

Full sprint board: [`14_Jira_Board_Mock.png`](./14_Jira%20Screenshot.png) · Full KPI detail: [`19_KPI_Report.xlsx`](./19_KPI%20Reports%20-%20BRD%20KPI%20Reports.pdf))

**What's validated so far:** the two capabilities most directly tied to the original business problem — automated completeness checking and mandatory exception audit trail — are both built, tested, and passing. **What isn't yet:** anything depending on SLA Tracking, which is the least mature pillar and the dependency for the project's headline metric. Full detail in [`18_Solution_Evaluation.docx`](./18_Solution%20Evaluation.pdf).

---

## What Made This a Real BA Exercise, Not Just Documentation

- **A genuine stakeholder disagreement** surfaced in elicitation (Operations Manager wanted auto-assignment of exceptions by workload; Credit Analyst wanted self-selection) and had to be escalated and resolved via a joint follow-up session before requirements could be finalized. The resolution — auto-assign with a 2-hour analyst override window — became a formal business rule.
- **An unresolved dependency** (Product Manager wants detailed exception reasons shown to customers; Compliance wants review before anything goes live) is still open and explicitly tracked as a blocker on one requirement (BR-13), rather than quietly resolved for narrative convenience.
- **Testing found real issues**, three of which were fixed during UAT (a validation gap that let whitespace-only audit reasons pass, a document request that defaulted to a generic label instead of naming the specific missing item, a duplicate entry in a missing-items list) — logged in [`17_Defect_Log`](./17_Defect%20Log%20-%20Defect%20Log.pdf).
- **One finding (DEF-02) wasn't a bug at all** — the system correctly falls back to manual review for unclassified exceptions, but nothing yet prompts a human to convert a recurring fallback pattern into a new formal rule. That's a process-design gap surfaced through testing, and it's carried forward as a recommendation rather than force-fit into a code fix.

---

## Business Analysis Approach

Requirements were elicited from four primary stakeholders (Operations Manager, Credit Analyst, Compliance, Product Manager), each assigned deep elicitation based on their role in the Stakeholder Register — other stakeholders (Operations Officer, Customer Support, Customer) were represented through those four sessions rather than interviewed separately, matching how influence and engagement actually work on a real project.

This project explicitly maps to BABOK's Business Analysis Core Concept Model and six Knowledge Areas — see for the full mapping from Change/Need/Solution/Stakeholder/Value/Context through to specific project artifacts.

Every requirement traces end-to-end: Pain Point → Gap Analysis → Business Requirement → Functional Requirement → User Story → Test Case, documented in the [`15_RTM.xlsx`](./15_Requirements%20Traceability%20Matrix.pdf).

---

## Contact

Carol Felix — Business Analyst
