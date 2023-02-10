# Manual Incident Creation Checklist

For creating a manual production incident.

### What are manual incidents?

Manual incidents are triggered when a production outage occurs but does not set off any of our on-call alerts.  They can be reported by users, found in test runs, or caught by our own interactions in Terra. 

**We define [production incidents](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) in our incident response SLA.**  Production incidents need to be remediated in accordance to our SLA (meaning in a timely manner).  Use the definitions to judge if the issue you're seeing is a production incident.  As a rule of thumb, incidents are _actively_ blocking users from functionality we have already delivered. 

If you think you've discovered what is or could be an incident, follow the steps below:

## If it's after hours
- <input type='checkbox'> **Visit [broad.io/terra-incident](https://broad.io/terra-incident) to manually trigger a PagerDuty alert.**  
    - Include any information you know about the issue: when it began, how it was discovered, what's broken, any ideas about why.
    - This will alert the on-call engineer, who is responsible for overseeing incident response

## If you're Frontline Support or one of the portals (AoU, SCP)
- <input type='checkbox'> **Make a ticket on the [PROD board](https://broadworkbench.atlassian.net/jira/software/c/projects/PROD/boards/88) with details on the issue**
	-  To the best of your ability, fill in the *Date Incident Identified* field with the date and time the issue was declared and *Priority* according to the [SLA](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=380034970).
	-  Set the *Teams* field to the team that is responsible for the affected part of the platform (best guess).
	-  Add whatever information you have about the issue to the *Description* field. **If the issue is particularly urgent**, you can get in contact with the appropriate team or oncall engineer before you fill this in.
- <input type='checkbox'> **If obviously a PROD incident, ping the sprint captain for the relevant team.** Tag them in the thread for the PROD ticket in #workbench-resilience. Let them know all of the information you have about the issue, or that you will be adding the details to the PROD ticket description.
- <input type='checkbox'> **If ambiguous, contact Tier 3 Support to triage severity.**  With Tier 3, decide if it's a production incident and its category using the [incident definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) 
	- <input type='checkbox'> If it's an incident **Tier 3 Support can escalate to the engineering team that can resolve the issue.** If no one responds, if they don't have time or can't help, contact the on-call engineer by following the instructions under “If it’s after hours”.
- <input type='checkbox'> **Prepare to work on user comms.** Use the [Terra/Firecloud Service Notification Process](https://broadworkbench.atlassian.net/wiki/spaces/FS/pages/2599780388/Terra+Firecloud+Service+Notification+Process).

## If you're a developer and you're investigating the issue
- <input type='checkbox'> **Check if Frontline Support made a ticket on the [PROD board](https://broadworkbench.atlassian.net/jira/software/c/projects/PROD/boards/88).  If not, make a PROD ticket with details on the issue.**
	- This will automatically notify #workbench-resilience
	- To the best of your ability, fill in the *Incident Start Time* field with the date and time the issue began. The *Date Incident Identified* field can be set to the time the ticket was raised.
- <input type='checkbox'> **During investigation, use the [incident definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) to classify the issue.**
	- If it's an incident, set the ticket's *Priority* as "Blocker" or "Critical"
	- Otherwise, move the ticket to the Support board or another Jira project
- <input type='checkbox'> If it's an incident, **follow the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) during remediation (skipping the PagerDuty steps)**

## If you're a developer (or anyone else) and you don't know what to do
- <input type='checkbox'> **Follow "If it's after hours"**

