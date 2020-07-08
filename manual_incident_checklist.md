# Manual Incident Creation Checklist

For creating a manual production incident.

## What are manual incidents?

Manual incidents are triggered when a production outage occurs but does not set off any of our automated alerts.  Incidents are defined in our Service Level Agreements(SLAs).  They can be reported by users, found in test runs, or caught by our own interactions in Terra. 


## Step 1
**Use the [SLA Definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) to identify if the issue is a production incident.**

If you would define the issue as "Blocker" or "Critical" and it is NOT already being investigated (check the #workbench-oncall and #workbench-resilience channels), follow the steps below:

## If it's after hours
- <input type='checkbox'> **Type `/pd trigger` in any Slack channel to manually trigger a PagerDuty alert.**  
    - Include any information you know about the issue: when it began, how it was discovered, what's broken, any ideas about why.
    - This will alert the on-call engineer, who is responsible for overseeing incident response

## If you're Frontline Support or one of the portals (AoU, SCP)
- <input type='checkbox'> **Contact user liason (UL) to triage severity.**  With UL, decide if it's a production issue and its category using the [SLAs](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288) 
- <input type='checkbox'> **UL makes a ticket on the PROD board with details on the issue**
	- Set the priority to "Blocker" if the issue is a blocker, and "Critical" if the issue is critical
- <input type='checkbox'> **UL begins remediating following the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) (skipping the PagerDuty steps).** If they don't have time or can't help, they should contact the on-call engineer or someone else to remediate


## If you're a developer and you or someone else is actively working on the issue
- <input type='checkbox'> **Make a ticket on the PROD board with details on the issue**
	- Set Priority as either "Blocker" or "Critical" using the [SLAs](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=1440345288)
	- This will automatically notify #workbench-resilience and frontline support
- <input type='checkbox'> **To the best of your ability, fill in the "PagerDuty incident start time" field with the date and time the incident began**
- <input type='checkbox'> **Follow the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) during remediation (skipping the PagerDuty steps)**

## If you're a developer (or anyone else) and the issue is unknown and not currently being remediated
- <input type='checkbox'> **Follow "If it's after hours"**

