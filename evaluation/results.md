## **Delivery KPI calculation table**

**Reporting date:** 25 November 2026 (`2026-11-25`)\
**Data source:** `project-issues(1).csv`\
**Scope:** All 12 issues in the uploaded CSV file.

| Metric                          | Calculation rule                                                               | Issue keys included                                                                                | Count | Denominator | Result  |
| ------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- | ----- | ----------- | ------- |
| Total issues                    | Count all unique `issue_key` values                                            | INF-01, INF-02, INF-03, INF-04, AUTH-01, AUTH-02, AUTH-03, SEC-01, SEC-02, TEST-01, REL-01, REL-02 | 12    | —           | **12**  |
| Completed issues                | `workflow_status = done`                                                       | INF-01, INF-02, AUTH-01                                                                            | 3     | 12          | **3**   |
| Completion percentage           | Completed issues / Total issues × 100                                          | INF-01, INF-02, AUTH-01                                                                            | 3     | 12          | **25%** |
| Incomplete issues               | `workflow_status != done`                                                      | INF-03, INF-04, AUTH-02, AUTH-03, SEC-01, SEC-02, TEST-01, REL-01, REL-02                          | 9     | 12          | **9**   |
| Blocked incomplete issues       | `workflow_status != done` AND (`blocked = Yes` OR `workflow_status = blocked`) | INF-03, AUTH-03, SEC-01                                                                            | 3     | 9           | **3**   |
| Overdue incomplete issues       | `workflow_status != done` AND `due_date` strictly earlier than `2026-11-25`    | INF-03, AUTH-02, AUTH-03, SEC-01                                                                   | 4     | 9           | **4**   |
| High/critical incomplete issues | `workflow_status != done` AND `priority IN (high, critical)`                   | INF-03, AUTH-02, AUTH-03, SEC-01, SEC-02, TEST-01, REL-02                                          | 7     | 9           | **7**   |

## **KPI percentage breakdown**

Completion rate

**25.00%**

3 of 12 total issues

Incomplete issue rate

**75.00%**

9 of 12 total issues

Blocked rate

**33.33%**

3 of 9 incomplete issues

Overdue rate

**44.44%**

4 of 9 incomplete issues

High/critical incomplete rate

**77.78%**

7 of 9 incomplete issues

## **Overdue calculation evidence**

| Issue key | Workflow status | Priority | Due date   | Days overdue |
| --------- | --------------- | -------- | ---------- | ------------ |
| INF-03    | blocked         | critical | 2026-11-17 | 8            |
| AUTH-03   | blocked         | high     | 2026-11-18 | 7            |
| SEC-01    | blocked         | critical | 2026-11-21 | 4            |
| AUTH-02   | in_progress     | critical | 2026-11-24 | 1            |
| **Total** |                 |          |            | **4 issues** |

## **Calculation validation**

| Validation check                                                    | Result     |
| ------------------------------------------------------------------- | ---------- |
| Total source records                                                | 12         |
| Unique issue keys                                                   | 12         |
| Duplicate issue keys                                                | 0          |
| Missing due dates                                                   | 0          |
| Missing workflow statuses                                           | 0          |
| Missing priorities                                                  | 0          |
| Issues due on reporting date                                        | 0          |
| Completed issues excluded from overdue calculation                  | Yes        |
| Completed issues excluded from blocked calculation                  | Yes        |
| Completed issues excluded from high/critical incomplete calculation | Yes        |
| Completed + incomplete = total                                      | 3 + 9 = 12 |
| Live GitLab retrieval performed                                     | No         |
| Source records modified                                             | No         |

**Calculation conventions:** Completion is determined exclusively by `workflow_status = done`, not `gitlab_state`. Blockage is identified using either the explicit blocked flag or blocked workflow status; both fields are consistent in this dataset. Blocked, overdue and high/critical categories can overlap and must not be added together to determine the total number of incomplete issues.
