* Incident Management Checklist*
For on-call engineers

- [ ] Acknowledge the event in PagerDuty
- [ ] Open a Jira ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=15&projectKey=PROD&selectedIssue=PROD-324)
    - Create a new ticket with fields summary, description, CLIA Impact (TBD if not known).  Set severity based on Terra Support SLA, defaulting to “Blocker”
    - Assign to yourself if you are investigating the issue
- [ ] Report in the #workbench-oncall slack channel that you are online and investigating event
- [ ] Return the affected systems to normal.
- [ ] Move the Jira ticket to remediated
