# Architecture and trust boundaries

This is a **prompt-driven, , tool-aware workflow**, , not a standalone deployed API service.

1. **User request** defines project, , reporting horizon and scope.
2. **Orchestrator instructions** select between user-uploaded synthetic files, , SOPs and authorized connected tools.
3. **Data retrieval** supplies source issue records; pagination and access limitations must be checked.
4. **Analysis** derives task counts, , statuses, , due dates, , blockers and risk observations.
5. **Management summary** distinguishes evidence, , assessment, , recommended actions and leadership decisions.

## Guardrails

- All initial integrations must be read-only. Natural-language safety instructions are not a substitute for restricted connector permissions.
- Avoid storing third-party credentials, , keys, , project exports or personal data in this repository.
- Each user connects their own permitted tools; a plugin does not transfer its creator's GitLab permissions to others.
- If source data is missing, , incomplete or stale, , flag this; do not guess.
- Model-generated risk ratings are advisory and do not replace governance approval.

## Definitions used in the synthetic test

- **Completed:** `workflow_status == done`.
- **Open/incomplete:** any workflow status other than `done`.
- **Blocked:** `blocked == Yes` AND incomplete.
- **Overdue:** due date before report date AND incomplete.
- **High/critical outstanding:** priority `high` or `critical` AND incomplete.
- **No baseline:** do not claim schedule slippage is proven merely from 25% completion.
