# Manual Incident Creation Checklist

For creating a manual production incident.

### What are manual incidents?

Manual incidents are triggered when a production outage occurs but does not set off any of our on-call alerts.  They can be reported by users, found in test runs, or caught by our own interactions in Terra. 

**We define [production incidents](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) in our incident response SLA.**  Production incidents need to be remediated in accordance to our SLA (meaning in a timely manner).  Use the definitions to judge if the issue you're seeing is a production incident.  As a rule of thumb, incidents are _actively_ blocking users from functionality we have already delivered. 

If you think you've discovered what is or could be an incident, follow the steps below:

## If it's after hours
- <input type='checkbox'> **Type `/terraisdown` in any Slack channel to manually trigger a PagerDuty alert.**  
    - Include any information you know about the issue: when it began, how it was discovered, what's broken, any ideas about why.
    - This will alert the on-call engineer, who is responsible for overseeing incident response

## If you're Frontline Support or one of the portals (AoU, SCP)
- <input type='checkbox'> **Make a ticket on the PROD board with details on the issue**
	-  To the best of your ability, fill in the “Incident Start Time” field with the date and time the issue began and “Priority” according to the SLA.
- <input type='checkbox'> **Contact Tier 3 Support to triage severity.**  With Tier 3, decide if it's a production incident and its category using the [incident definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) 
- <input type='checkbox'> If it's an incident **Tier 3 Support can escalate to the engineering team that can resolve the issue.** If no one responds, if they don't have time or can't help, contact the on-call engineer by following the instructions under “If it’s after hours”.

## If you're a developer and you're investigating the issue
- <input type='checkbox'> **Check if Frontline Support made a ticket on the PROD board.  Otherwise, make a [PROD](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=88&projectKey=PROD) ticket with details on the issue.**
	- This will automatically notify #workbench-resilience and frontline support
	- To the best of your ability, fill in the "Incident Start Time" field with the date and time the issue began.
- <input type='checkbox'> **During investigation, use the [incident definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) to classify the issue.**
	- If it's an incident, set the ticket's priority as "Blocker" or "Critical"
	- Otherwise, move the ticket to the Support board or another Jira project
- <input type='checkbox'> If it's an incident, **follow the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) during remediation (skipping the PagerDuty steps)**

## If you're a developer (or anyone else) and you don't know what to do
- <input type='checkbox'> **Follow "If it's after hours"**

