A summary of expectations and helpful information for being on-call.

![Alert Fatigue](../assets/img/misc/alert_fatigue.png)

## What is On-Call?
Being on-call means that you are able to be contacted at any time in order to investigate and fix issues that may arise for the system you are responsible for. For example, if you are on-call, should any alarms be triggered for that service, you will receive a "page" (an alert on your mobile device, email, phone call, or SMS, etc.) giving you details on what has broken and how to fix it. You will be expected to take whatever actions are necessary in order to resolve the issue and return the service to a normal state.

On-call responsibilities extend beyond normal office hours, and if you are on-call you are expected to be able to respond to issues, even at 2am. This sounds horrible (and it can be), but it is what we were hired to do! Remember that on-call can be tiresome and a burden but these are the times that our customers are the most vulnerable (in the early hours when no one is around), and in need of the best support. These problems can often escalate beyond the original issue if not handled appropriately and quickly. The important part to remember, you are human and can only handle so much (especially when you are half asleep), so don't be afraid to escalate or wake someone else up if needed.

## Responsibilities

1. **Prepare**
    * Have your laptop and Internet with you (office, home, a MiFi dongle, a phone with a tethering plan, etc). We understand that you have a life and can't always be at home to handle these alerts, so plan accordingly.
        * If you are hading out, make sure you have a phone charger, have a way to charge your MiFi device, or have someone on standby during those times in case you hit a snag in your schedule.
    * Team alert escalation happens within 15 minutes, set/stagger your notification timeouts (push, SMS, phone...) accordingly.
	* The recommended setup is: Push/Email: Immediately, SMS: 1, 5, 13 minutes after incident is opened. Phone: 3, 7, 12 minutes after incident is opened. While people don't like phone calls, they are crucial in the night hours when you might not hear the SMS ding of your phone.
        * Make sure PagerDuty texts and calls can [bypass your "Do Not Disturb" settings](https://support.pagerduty.com/hc/en-us/articles/202828870-Phone-numbers-notifications-are-sent-from).
    * Be prepared ([VPN access to the office works](https://vpn.mnxsolutions.com), you can access manage.checkstr.com, you have your phone for 2FA, able to connect to [Lastpass](https://www.lastpass.com), your credentials for third-party services are current and so on...)
    * Read our Incident Response documentation (that's this!) to understand how we handle serious incidents, what the different roles and methods of communication are, etc.
    * Be aware of your upcoming on-call time (primary, backup) and arrange swaps around travel, vacations, appointments etc.

1. **Triage**
    * Acknowledge and act on alerts whenever you can (see the first "Not responsibilities" point below)
    * Determine the urgency of the problem:
        * Is it something that should be worked on right now or escalated into a major incident? ("production server on fire" situations. Security alerts) - do so.
        * Is it some tactical work that doesn't have to happen during the night? (for example, disk utilization high watermark, but there's plenty of space left and the trend is not indicating impending doom) - snooze the alert until a more suitable time (working hours, the next morning...) and get back to fixing it then.
    * Check Slack for current activity. Often (but not always) actions that could potentially cause alerts will be announced there.
    * Check the Maintenance calendar, there may be a scheduled maintenance someone is working on that they forgot to disable alerts or cause another dependency alert to trigger that they weren't expecting.
    * Does the alert and your initial investigation indicate a general problem or an app side issue that the customer's developers or some other team should handle? We should do everything in our power to get the service, website, application, etc... up and running but if it is something outside of our control, don't hesitate to lookup the Customer's Escalation Policy and get in contact with them to get things back up and running sooner.

1. **Fix**
    * You are empowered to dive into any problem and act to fix it.
    * Involve other team members as necessary: do not hesitate to escalate if you cannot figure out the cause within a reasonable timeframe or if the service / alert is something you have not tackled before. Especially in the beginning, there will be a learning curve, make sure you do a little investigation of the problem before waking someone else up (like anyone, we all like our sleep and week(s) off of being on-call)
    * If the issue is not very time sensitive and you have other priority work, create a ticket to keep a track of it (with an appropriate severity). If the problem is apart of a longer term project, fix the initial issue, and create/check that there is a Asana Card for the project and appropriate timeframe.

1. **Improve**
    * If a particular issue keeps happening; if an issue alerts often but turns out to be a preventable non-issue – perhaps improving this should be a short-term ticket (if able to be handled during the week) or longer-term Asana task (if it isn't a top priority that will have to wait a week or will take or be longer than a week).
        * Disks that fill up, logs that should be rotated, noisy alerts...
    * If information is difficult / impossible to find, write it down. Constantly refactor and improve our [knowledge base and documentation](https://mnxsolutions.itglue.com). Add redundant links and pointers if your mental model of the wiki / codebase does not match the way it is currently organized.

1. **Support**
    * When your on-call "shift" ends, let the next on-call know about issues that have not been resolved yet and other experiences of note.
	* IE, if you put in a fix but not sure that it is totally fixed/might happen again. You are awaiting customer feedback or fully fix the problem. A ticket is opened for a issue that keeps popping up (from a customer perspective, it is very annoying when two techs from the same company are working on the same problem and they don't even know about it).
    * If you are making a change that impacts the schedule (adding / removing yourself, overrides, for example), let others know so they are aware and everyone can adjust their schedule accordingly.
    * If you have a major maintenance that might limit your ability to handle pages during that time, make sure you have someone override you or schedule a backup person that you can page that can assist if things come in at the wrong time.
    * Support each other: when doing activities that might generate plenty of pages, it is courteous to "take the page" away from the on-call by notifying them and scheduling an override for the duration. (Just be careful scheduling a override during a maintenance period where you will be consumed during that time and not able to properly handle other pages.)


## Not Responsibilities

1. No expectation to be the first to acknowledge _all_ of the alerts during the on-call period.
    * Commute (and other necessary distractions) are facts of life, and sometimes it is not possible to receive or act on an alert before it escalates. That's what we have the backup on-call and schedule for. Just communicate in advanced so that others can adjust and be free as needed.

1. No expectation to fix all issues by yourself.
    * No one knows everything. Your whole team is here to help. There is no shame, and much to be learned, by escalating issues you are not certain about. "Never hesitate to escalate" if you need.
    * If documentation is lacking, make sure we make a note of this so the appropriate person can update it or if we need to request that information from the customer (credentials, knowledge, etc...) we do so quickly so that we aren't without this the next time we get alerted. 

## Recommendations
While this on-call rotation works, we know that it might not be the best/ideal. Thats why we are always looking for inprovements and better ways to handle the on-call rotation. Below is what every process should include but if we have any ideas how to make it better, by any means, lets improve it.

* Always have a backup schedule. Yes, this means two people being on-call at the same time, however it takes a lot of the stress off of the primary if they know they have a specific backup they can contact, rather than trying to chose a random member of the team.
    * A backup shift should generally come directly after a primary shift. It gives chance for the previous primary to pass on additional context which may have come up during their shift. It also helps to prevent people from sitting on issues with the intent of letting the next shift fix it.

* The third-level of your escalation (after backup schedule) should probably be your entire team. This should hopefully never happen, but when it does, it's useful to be able to just get the next available person.

![Escalation](../assets/img/misc/escalation.png)

* Team managers can (and should) be part of your normal rotation. It gives a better insight into what has been going on.

* New members of the team should shadow your on-call rotation during the first few weeks. They should get all alerts (during office hours), and should follow along with what you are doing. (All new employees shadow the Operations team for one week of on-call, but it's useful to have new team members shadow your team rotations also. Just not at the same time).

* We recommend you set your escalation timeout to 15 minutes. This should be plenty of time for someone to acknowledge the incident if they're able to. If they're not able to within 15 minutes, then they're probably not in a good position to respond to the incident anyway.

* When going off-call, you should provide a quick summary to the next on-call about any issues that may come up during their shift. A service has been flapping, an issue is likely to re-occur, etc. If you want to be formal, this can be a written report via email, but generally a verbal summary is sufficient.

### Notification Method Recommendations
You are free to set up your notification rules as you see fit, to match how you would like to best respond to incidents. If you're not sure how to configure them, the Operations team has some recommendations,

![Mobile Alerts](../assets/img/misc/mobile_alerts.png)

* Use Push Notification and Email as your first method of notification. Most of us have phones with us at all times, so this is a prudent first method and is usually sufficient.
* Use Phone and/or SMS notifications a minute/two after the Push/Email notification and staggered every couple minutes after till the escalation timeout. Sometimes (like when you are sleeping) Push/SMS isn't enough for you to hear (like during the evening), so make sure have a couple Phone calls in there as backups if that should be the case. 

## Etiquette

* If the current on-call comes into the office at 12pm looking tired, it's not because they're lazy. They probably got paged in the night. Cut them some slack and be nice.

* Don't acknowledge an incident out from under someone else unless you contact them about it first (it is annoying to get a page for something and start investigating just to have someone else resolve it for you without tell you causing you to waste time and possibly step over their toes). If you didn't get paged for the incident, then you shouldn't be acknowledging it. Add a private comment in the ticket with your notes instead.

![Acknowledging](../assets/img/misc/ack.png)

* If you are testing something, or performing an action that you know will cause a page, it's customary to "take the pager" for the time during which you will be testing. Notify the person on-call that you are taking the pager for the next hour while you test.

* "Never hesitate to escalate" - Never feel ashamed to rope in someone else if you're not sure how to resolve an issue. Likewise, never look down on someone else if they ask you for help.

* Always consider covering an hour or so of someone else's on-call time if they request it and you are able. We all have lives which might get in the way of on-call time, and one day it might be you who needs to swap their on-call time in order to have a night out with your friend from out of town.

* If an issue comes up during your on-call shift for which you got paged, you are responsible for resolving it. Even if it takes 3 hours and there's only 1 hour left of your shift. You can hand over to the next on-call if they agree, but you should never assume that's possible.
