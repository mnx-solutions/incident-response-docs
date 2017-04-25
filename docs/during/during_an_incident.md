Information on what to do during a major incident. See our [severity level descriptions](/before/severity_levels.md) for what constitutes a major incident.

!!! note "Documentation"
    Here is all the necessary channels and conference call details.

    <table class="custom-table" id="contact-summary">
      <thead>
      </thead>
      <tbody>
        <tr>
          <td><a href="#">#general</a></td>
          <td><a href="#">https://mnx.slack.com</a></td>
          <td><a href="#">+1 734 344 5885</a> Mod PIN: 967-514-999 / Par PIN: 439-998-702</td>
        </tr>
        <tr>
          <td colspan="3" class="centered">Use Slack for communication. Conference call is if needed (To be determined by on-call person)</td>
        </tr>
      </tbody>
    </table>

!!! warning "Security Incident?"
    If this is a security incident, you should follow the [Security Incident Response](/during/security_incident_response.md) process.

## Don't Panic!

1. Join Slack (see links above). If you have/need help and Chat isn't enough, feel free to suggest any/all help to jion the conference call.
    * Anyone is free to join the call or chat to observe and follow along with the incident.
    * If you wish to participate, you can investigate but any changes or implementations, should be passed through the on-call person first so he is aware of any changes that are being made so that there isn't no mis-communication.

1. Follow along with the call/chat, add any comments you feel are appropriate, but keep the discussion relevant to the problem at hand.
    * If you are not the on-call person or assigned a task to complete by the on-call person, try to filter any discussion/issues through the on-call person first. Too many people discussing at once can get overwhelming, so we should try to maintain a hierarchical structure to the call if possible.

1. Follow instructions from the On-Call Person.

## Steps for On-Call Person
Resolve the incident as quickly and as safely as possible, use other teammates as needed to assist you. Delegate any tasks to relevant experts at your discretion.

1. Determine if the page is relevant (Is this an actual outage, monitoring fluke, bad check, etc...) and how severe the outage is (Is a disk filling up but still having space to go or do we have a site outage, database corruption, etc...)
    * If the page is a monitoring fluke or temporary connection issue, open a ticket with the details and what is needing to be fixed so they can be handled the following business day or if able too, fix immediately.

1. Open a ticket with the customer letting them know about the outage and that we are looking into it. (If you have any details about the outage and a approximate ETA to fix, include that as well.)
    * If this is a MNX.io Issue (Hypervisor, OPS Portal, or network issue in CHI.), update the [status page](https://manage.statuspage.io/login). [Public Status Page Link](http://status.mnx.io/)
    * **NOTE:** When contacting customers, be sure to review the Escalation Policy. Remember if there is a major outage that their business emails may be affected so be sure to use their alternate emails if that is the case. Also, if ETA to fix is greater than an hour or you need an important decision to be made in how to handle, be sure to immediately call the customer so you don't prolong the downtime.

1. Announce in Slack that you got a page for whatever and the severity of the issue. This helps others who are free (or can be free) understand what needs to be done and if help might be needed before you ask.

1. Identify if there is an obvious cause to the incident (recent deployment, spike in traffic, etc.), delegate investigation to others as needed.
    * If there are multiple pages or no obvious cause and others there are available to help, delegate tasks to help keep order in the caios of the outage. Be aware, for major outages you might get slammed with PagerDuty alerts so be sure to account for that.
    * You may want to consider having someone be your contact with the customer so that you can concentrate on understanding/fixing the problem and not being distracted.
    * If this is off hours in the middle of the night, try to handle first before asking others and delegating tasks (Others need their sleep too). If you have to use other teammates, feel free to try to contact them and wake them up but do your due diligence first and investigate a little bit before you start contacting others.

1. If others are needed and Slack isn't enough, open the conference bridge and have them join.
    * If customers/developers are involved/needed, feel free to have them join the conference bridge if needed.

1. Identify investigation & repair actions (roll back, rate-limit services, etc) and delegate actions to others as needed. Typically something like this (obviously not an exhaustive list),
    * **Bad Deployment:** Contact the customer to have their developers fix it.
    * **Web Application Stuck/Crashed:** Do a restart and check relevent settings.
    * **Database/Service Issue:** Track down the relevent service and fix it.
    * **Data Center Outage:** Keep in contact with the Data Center or their status page (if they have one).
    * **Degraded Service Behavior without load:** Gather forensic data (heap dumps, etc), and consider doing a rolling restart.
    * **Network Outage:** Do ping and traceroute tests to confirm and contact the relevant parties.

1. Keep track of your [span of control](/training/glossary.md#span-of-control). If the response starts to become larger, or the incident increases in complexity, consider [splitting off sub-teams](/before/complex_incidents.md#spinning-off-sub-teams) in order to get a more effective response.

1. Once incident has recovered or is actively recovering, you can announce that the incident is over. This usually indicates there's no more productive work to be done for the incident right now.
    * Follow up with the customer to make sure everything is working from their end.
    * Identify any post-incident clean-up work (Ex. adding/adjusting monitoring, adding log-rotate, fixing config files, etc...).
    * You may need to perform debriefing/analysis of the underlying root cause.
    * Update [Status Page]((https://manage.statuspage.io/login)) and give the all clear.

1. Once the incident is over, you can start to follow the steps from [After an Incident](/after/after_an_incident.md).

