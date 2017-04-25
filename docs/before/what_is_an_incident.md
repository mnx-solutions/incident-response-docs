Before we can define our incident response process, we should first define what an incident (and a major incident) is.

![Incident](../assets/img/headers/server_incident.png)

## What is an incident?
Any unplanned disruption or degradation of service that is actively affecting customers ability to use/connect to their servers, websites, applications, etc...

## What is a major incident?
Any incident that requires a severe downtime or possible data loss (IE, corrupted MySQL database, server crash and data loss, etc...)

## What triggers our incident response process?
Our incident response process should be initiated for any incident that draws a page. It provides a framework for effectively responding and reaching a fast resolution time. Our incident response process can be triggered one of two ways, either via automated monitoring and alerting, or manually via human action/Zendesk ticket created by a customer.

### Automated Monitoring
Throughout our system, we monitor various metrics to determine if our system is in a state which would require a co-ordinated human response in order to resolve. To determine which metrics we monitor, and what to monitor them for, we ask ourselves these questions. If the answer to any is "No", then we should trigger our incident response process.

1. Can customers hit their websites/applications?
1. If a Application/Service goes down, would things still run smoothly.
    * e.g. If cron jobs fail, or people not able to connect or view certain pages, would things still be ok?

### Human Escalation
Automatic monitoring is only part of the process. We may have parts of our functionality which lack the necessary monitoring. It's important to still be able to trigger a coordinated incident response in those cases. For example, if a customer has a issue connecting to a website/server or pulling up something specific/important (maybe firewall rule or even web issue only directly related to that customer), they still need to have the power to trigger a page (this can only be done by customers through the [Support Portal](https://support.mnxsolutions.com) and by setting the new ticket priority or updating a previous ticket priority to High/Urgent) to get some help/assistance. *NOTE: If it is a mnx.io customer, they would submit this through the [OPS Portal](https://ops.mnx.io) by navigating to helpdesk page at the top right and then by checking the (is your server down check box).

## Incident Severity
Our [severity definitions](/before/severity_levels.md) determine how severe we _think_ an incident is, based on some pre-defined guidelines. The intent is to guide responders on the type of response they can provide. For example, the higher the severity, the riskier the decisions you can take to return the system to normal.

Severities are useful to quickly determine whether something requires a more complex response, or whether it requires a co-ordinated response at all. However, they are not a black and white definition of what constitutes a major incident. If something is not covered by our severity definitions, but you think it requires incident response, then it requires incident response. We only need to know one thing: "Is this a major incident?". The severity level can be determined later, and isn't a requirement of triggering our response process.
