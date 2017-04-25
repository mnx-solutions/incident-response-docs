We manage how we get alerted based on a simple principle, **an alert is something which requires a human to perform an action**. Anything else is a notification, which is something that we cannot control, and for which we cannot make any action to affect it. Notifications are useful, but they shouldn't be waking people up under any circumstance.

!!! warning "High Priority Alerts"
    Anything that wakes up a human in the middle of the night should be **immediately human actionable**. If it is none of those things, then we need to adjust the alert to not page at those times.

| Priority | Alerts | Response | SLA |
| -------- | ------ | -------- | --- |
| Critical | Critical-Priority PagerDuty Alert 24/7/365. | Requires **immediate human action**. | 1 hour response, target is 15 minute response |
| High | High-Priority PagerDuty Alert 14/7/365. | High Priority, Need Emergency Support | 4 hour response.
| Medium | Ticket Based Event | Requires human action at some point. | 8 hour business hour response |
| Low | Ticket Based Event. | No response required. Informational only. | 1-2 business day response |

If you're setting up a new alert/notification, consider the chart above for how you want to alert people. Be mindful of not creating new critical/high-priority alerts if they don't require an immediate response, for example.

## Examples

#### "Production service is failing for 75% of requests, automation is unable to resolve."_
This would be a **Critical** priority page, requiring immediate human action to resolve.

#### "Production server is having a issue executing a cron job or a SQL query isn't properly executing because the tables don't exist.
This would be a **High** priority page, while the service isn't down or causing issues, not being able to run that cron job or execut that SQL query could cause a issue later in the day and take down the server/service so fixing this now would prevent a major outage later in the day (or worse, at 3am).

#### "Production server disk space is filling, expected to be full in 48 hours. Log rotation is insufficient to resolve."
This would be a **Medium** priority ticket with a 8 hour response but an expected solution figured out and implemented prior to this escalating to high/critical.

#### "An SSL certificate is due to expire in one month."
This would be a **Low** priority ticket, requiring human action some time soon but not an immediate urgency.

#### "A backup was successful."
This would be a **Notification**, and should be sent as a suppressed event. It provides useful context should an incident occur, but does not require notifying a human. Usually we try not to send emails unless there is a problem but sometimes it is helpful to see these.
