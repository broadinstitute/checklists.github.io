# Manual Incident Creation Checklist

For triggering a manual on-call incident.

## When to trigger

Manual incidents should be triggered when a production outage is occurring but has not set off any of our automated alerts.  
Incidents are [defined in our SDLC](https://docs.google.com/document/d/1rLUMry-VAWsewEz2mOLfdzH-7UKxuIn35VlzZH90CcI/edit#).  They can be reported by users, or caught by our own interactions in Terra. 

For the purpose of collecting metrics around our incident response, PagerDuty should be the source of truth for incident start time. 
Therefore, incidents should be tracked in Pagerduty BEFORE they are tracked in Jira or remediated. 

## To raise the flag
- <input type='checkbox'> **Verify that someone/something else has not triggered the incident in PagerDuty**
- <input type='checkbox'> **Type `/pd trigger` in Slack to manually trigger a PagerDuty alert.**  Include any information you know about the issue: when it began, how it was discovered, what's broken, any ideas about why.
    - This will alert the on-call engineer, who is responsible for tracking the issue and overseeing remediation, and kick off the incident response process.
