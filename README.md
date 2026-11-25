## Working Agent Demonstration

AI Delivery Manager is a prompt-driven, tool-aware AI workflow designed to support IT delivery health assessments, risk identification and executive reporting.

### Demonstrated capabilities

| Capability | Evidence |
|---|---|
| Project KPI analysis | [Actual agent report](demo/actual-agent-report.md) |
| Metric accuracy and evaluation | [Evaluation results](evaluation/results.md) |
| Risk and management decision analysis | [Evaluation results](evaluation/results.md) |
| Read-only safety behavior | [Evaluation results](evaluation/results.md) |
| GitLab integration | [Integration case study](demo/gitlab-integration-case-study.md) |

### How to reproduce the demonstration

1. Download the fictional project dataset from `sample-data/`.
2. Load the instructions in `prompts/agent-instructions.md` into a compatible AI assistant.
3. Upload `project-issues.csv` and `risk-register.csv`.
4. Use the prompts in `prompts/demo-questions.md`.
5. Compare the agent's results against `evaluation/test-cases.md`.

**Reference date:** 25 November 2026.

**Expected results:** 12 issues, 3 completed, 25% completion, 3 blocked and 4 overdue.

The included example data is fictional. Live GitLab integration requires an independently authorized connection.

### Reliability and limitations

Observed test outcomes are recorded in `evaluation/results.md`. This demonstration is not a production deployment, and AI-generated risk assessments require human review.
