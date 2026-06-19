# Sprint 1 Plan - FinConnect Core API Integrations

*   **Sprint Cycle**: Sprint 1 (2-Week Cycle)
*   **Start Date**: 2026-06-01
*   **End Date**: 2026-06-12
*   **Sprint Goal**: Implement and verify core Plaid API OAuth authentication flow and checking/savings balance aggregation endpoints.
*   **Target Velocity**: 24 Story Points (Sized Backlog: 29 SP, with 5 SP stretch goal).
*   **Scrum Master / Agile Project Lead**: **Syed Imon Rizvi** (MBA, PMP, PSM II, PAL I)

---

## 👥 Scrum Team Allocation & Capacity
Our cross-functional team comprises 5 members. Available capacity for Sprint 1 is **72 net engineering hours** per developer (accounting for sprint ceremonies and team buffer).

*   **Scrum Master / Agile Project Lead**: Syed Imon Rizvi (Coaches team on self-management, facilitates ceremonies, removes organizational bottlenecks)
*   **Product Owner**: Elena Vance (Owns value optimization, backlog priority, and stakeholder communications)
*   **Tech Lead / Backend**: David Chen (Focus on core database schema scaffolding, KMS encryption vault, and Plaid client wrappers)
*   **Full Stack Developer**: Sarah Jenkins (Focus on Balance aggregation API logic and Developer Dashboard frontend elements)
*   **QA Engineer**: Marcus Brody (Focus on automated integration suites, API contract testing, and regression pipelines)

---

## 🛡️ PMP-Aligned Project Risk Register

To ensure project governance (PMP alignment), I establish and track this Sprint 1 Risk Register:

| Risk ID | Risk Description | Probability | Impact | Proximity | Mitigation Strategy | Owner | Status |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :---: |
| **R-1.1** | Plaid API rate-limiting in sandbox environments (`FIN-104`). | High | High | Immediate | Implement automated batch polling with backoff logic and queueing scheduler. | David Chen | **Active** |
| **R-1.2** | Key developer unavailability during critical setup phase. | Low | High | Medium | Cross-train Sarah on database scaffolding and Plaid configuration. | Syed Imon | **Mitigated** |
| **R-1.3** | Access token credential leaks in staging databases or log outputs. | Low | Critical | Ongoing | Enforce AES-256 vault encryption (`FIN-105`) and run static code analysis. | Marcus Brody | **Active** |
| **R-1.4** | Scope creep mid-sprint from business stakeholder request. | Medium | Medium | Immediate | Enforce formal Change Request Log (`CR-001`) and protect active sprint. | Syed Imon | **Active** |

---

## 📋 Sprint 1 Backlog Sizing

| JIRA Key | Summary | Story Points | Assignee | Priority | Strategic Value Alignment (MBA / PAL I) |
| :--- | :--- | :---: | :--- | :---: | :--- |
| **FIN-101** | Microservice Scaffolding & DB Setup | 5 | David Chen | High | Establishes infrastructure baseline; impacts Time-to-Market (T2M). |
| **FIN-102** | Plaid API Secure OAuth 2.0 Integration | 5 | David Chen | High | Key customer acquisition enabler; impacts Current Value (CV). |
| **FIN-103** | Account Balance Aggregation | 3 | Sarah Jenkins | High | Core retention feature driving Daily Active Users (DAU); impacts CV. |
| **FIN-104** | Transaction Sync Engine (Stretch Goal) | 5 | David Chen | High | Data analytics driver; unlocks premium revenue. (Rolled Over) |
| **FIN-105** | Secure Vaulting of User Access Tokens | 3 | David Chen | High | Risk compliance baseline; prevents CCPA/GDPR regulatory fines. |
| **FIN-106** | Developer Dashboard for Connection Status | 5 | Sarah Jenkins | Medium | Decreases support triage times by 40% (A2I). |
| **FIN-107** | Custom Logging & Traceability Framework | 3 | David/Sarah | Medium | Decreases system MTTR by 50%; impacts T2M. |

*Total Sized Work: 29 SP*  
*Sprint 1 Target Commitment: 24 SP*

---

## 🤝 Scrum Values Enablement (PSM II)

As a PSM II Scrum Master, I actively facilitate the team's commitment to the five Scrum Values during Sprint 1:
*   **Commitment**: The team commits to delivering the 24 SP core sprint goal, and I commit to shielding them from external distractions.
*   **Focus**: We limit work-in-progress (WIP) by enforcing developers to focus on core integration elements (`FIN-101` and `FIN-102`) before pulling in dashboard features (`FIN-106`).
*   **Openness**: In daily standups, developers openly share technical hurdles, specifically sandbox rate limits, enabling immediate peer assistance.
*   **Respect**: We respect individual capacity boundaries, setting sizing estimations collaboratively without top-down management pressure.
*   **Courage**: The team has the courage to reject stakeholder scope requests that threaten sprint stability and to roll over incomplete stories to maintain quality standards rather than releasing buggy code.

---

## 🏁 Definition of Done (DoD)
A backlog item is declared "Done" only when:
1.  **Code Quality**: Clean build, static code analysis (SonarQube) passes with zero critical defects.
2.  **Review**: Code review completed and approved by at least one peer developer.
3.  **Testing**: Unit test coverage exceeds **80%**, and automated API integration runs pass in Jenkins.
4.  **Security**: Cryptographic verification of access tokens in transit and storage (AES-256).
5.  **Documentation**: Swagger API docs updated, and developer setup guides added to Confluence.
6.  **Deployment**: Successfully merged into `main` branch and smoke tested in the staging environment.
