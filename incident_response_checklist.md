# Incident Response Checklist
For the engineer managing a production incident.

## During the incident
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If the incident originates in PagerDuty, acknowledge the event in PagerDuty and click *More Actions* -> *Create JIRA Issue* to create a ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=88&projectKey=PROD)**
    - This will create a Jira bug that includes incident start-time.  Update the summary and description as needed and assign to yourself.
    - If the incident does NOT originate in PagerDuty, confirm that a Jira bug has been made or create one. 
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Move the Jira bug to "In Progress"**
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Mention in #workbench-resilience that you are investigating the issue.** 
- <input type='checkbox'> **Notify users of the incident**
    - If it impacts many users:
        - <span style="color:darkorange">`4 hrs`</span> Daytime: Confirm that a support specialist is aware of the issue (slack #dsde-comms or @dspsupportteam in #workbench-resilience) and can put up a banner. Provide the Jira ticket and a description of the user impact.
        - <span style="color:darkorange">`8 hrs`</span> Off-hours: [Put up a banner in Terra.](https://fcprod-jenkins.dsp-techops.broadinstitute.org/job/terra-service-banner) (You will need to be on the VPN and authed in [prod jenkins](https://fcprod-jenkins.dsp-techops.broadinstitute.org/) with your github account)
            - In order to set up the banner, from the Jenkins job, click on "Build With Parameters" and you'll see a screen with free text fields and information about how to fill in banner details.        
    - Impacts a single user (the user will need to be directly contacted)
        - <span style="color:darkorange">`8 hrs`</span> Daytime: contact a support specialist for assistance (slack #dsde-comms or @dspsupportteam in #workbench-resilience). 
        - <span style="color:gold">`12 hrs`</span> Off-hours: Contact the user and cc support@terra.bio . The email should explain the time the issue occurred, how the issue is impacting the user, and any relevant Terra details (workspace/submission/notebook/etc.) The Frontline support team will follow up with the user the next work day to answer any further questions.
- <input type='checkbox'> **Update the "Users Informed" field on the Jira bug.**
- <input type='checkbox'> <span style="color:darkorange">`12 hrs`</span> (Blocker) <span style="color:gold">`48 hrs`</span> (Critical) **Oversee the remediation of the issue, returning the affected systems to normal.**  Follow steps in the [General Troubleshooting Playbook](https://docs.google.com/document/d/1KUdZBrnedzCCYQTNNmUCn_NVgTvfVKby_dyU7Laq5g0/edit#).  
    - Note that "remediation" means that the system is back "up" and affected users are unblocked, not necessarily that the underlying cause has been fixed.
    - If there are additional actions to address root cause, track them as tickets on the appropriate Jira board.

## After the incident
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Move the Jira bug to "Remediated"**
    - This will automatically create an epic to track post mortem actions and link the bug.  Link any additional remediation tasks as issues in the epic. 
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If a banner has been put up, confirm that it gets taken down.** During off-hours: [Take down the banner.](https://fcprod-jenkins.dsp-techops.broadinstitute.org/job/terra-service-banner)
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If the incident originated from PagerDuty, confirm that the PagerDuty incident was resolved or resolve it manually **
- <input type='checkbox'> <span style="color:gold">`1-2 days`</span> **Update the Jira bug with relevant information**
    - Update components/services impacted
    - Update Description:
        - Update what was the issue
        - Enter how it was resolved
        - Gather logs
    - Set Origin: Automated alerting systems such as New Relic or human (Support team, CS)
- <input type='checkbox'> <span style="color:gold">`1-2 days`</span> **Create a [new post mortem notes page](https://broadworkbench.atlassian.net/wiki/spaces/AP/pages/702021656/Post+Mortems) from the Confluence template.**
    - Set the incident summary as `description`
    - To the best of your ability, fill out `1. What happened(timeline)?` and `3. Who was involved?`
    - Link the post mortem to the new epic as a Confluence page (the drop arrow besides "Link Issue")
