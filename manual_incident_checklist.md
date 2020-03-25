# Manual Incident Creation Checklist

For triggering a manual production incident.

## What are manual incidents?

Manual incidents are triggered when a production outage occurs but does not set off any of our automated alerts.  Incidents are [defined in our Service Level Agreements(SLAs)](https://docs.google.com/document/d/1rLUMry-VAWsewEz2mOLfdzH-7UKxuIn35VlzZH90CcI/edit#).  They can be reported by users, or caught by our own interactions in Terra. 

If you've discover what you think is a production incident that is NOT already being investigated (check the #workbench-oncall and #workbench-resilience channels), follow the steps below to raise the flag:

## If it's after hours
- <input type='checkbox'> **Type `/pd trigger` in any Slack channel to manually trigger a PagerDuty alert.**  
    - Include any information you know about the issue: when it began, how it was discovered, what's broken, any ideas about why.
    - This will alert the on-call engineer, who is responsible for overseeing incident response

## If you're Frontline Support or one of the portals (AoU, SCP)
- <input type='checkbox'> **Contact user liason (UL) to triage severity.**  With UL, decide if it's a production issue and its category using the [SLAs](https://docs.google.com/document/d/1rLUMry-VAWsewEz2mOLfdzH-7UKxuIn35VlzZH90CcI/edit#) 
- <input type='checkbox'> **UL makes a ticket on the PROD board with details on the issue**
	- Set the priority to "Blocker" if the issue is a blocker, and "Critical" if the issue is critical
- <input type='checkbox'> **UL begins remediating following the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) (skipping the PagerDuty steps).** If they don't have time or can't help, they should contact the on-call engineer or someone else to remediate


## If you're a developer and you or someone else is actively working on the issue
- <input type='checkbox'> **Make a ticket on the PROD board with details on the issue**
	- Categorize priority as either "Blocker" or "Critical" using the [SLAs](https://docs.google.com/document/d/1rLUMry-VAWsewEz2mOLfdzH-7UKxuIn35VlzZH90CcI/edit#)
	- This will automatically notify #workbench-resilience and frontline support
- <input type='checkbox'> **Follow the [incident response checklist](https://broadinstitute.github.io/checklists.github.io/incident_response_checklist.html) during remediation (skipping the PagerDuty steps)**

## If you're a developer (or anyone else) and the issue is unknown and not currently being remediated
- <input type='checkbox'> **Follow "If it's after hours"**

