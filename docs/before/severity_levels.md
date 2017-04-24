The first step in any incident response process is to determine what actually [constitutes an incident](/before/what_is_an_incident.md). Incidents can then be classified by critical, high, medium, and low. Operational issues can be classified at one of those levels, and in general you are able to take more risky moves to resolve a higher severity issue. Anything above medium is automatically considered a "major incident" and gets a more intensive response than a normal incident.

!!! note "Always Assume The Worst"
     If you are unsure which level an incident is (e.g. not sure if High or Critical), **treat it as the higher one**. During an incident is not the time to discuss or litigate severities, just assume the highest and review during a post-mortem.

!!! question "Can a Medium be a major incident?"
     All Medium priorities are major incidents, but not all major incidents need to be classified as Medium. If you require co-ordinated response, even for lower severity issues, then trigger our incident response process. The IC can make a determination on whether full incident response is necessary.

<table class="custom-table">
  <thead>
    <tr>
      <th class="priority">Priority</th>
      <th>Description</th>
      <th>Typical Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="critical">Critical</td>
      <td>
        <p class="intent">Critical issue that warrants customer or public notification.</p>
        <ul>
          <li>The system is in a critical state or down.</li>
          <li>Service issue(s) (Ex. Apache/Nginx/MySQL/Disk/etc...) that is affected customer application/website(s)</li>
          <li>Customer-data-exposing security vulnerability has come to our attention.</li>
          <li>MNX.io Hypervisor or Portal Issue.</li>
        </ul>
      </td>
      <td>
        <p class="response">Major incident response.</p>
        <ul>
          <li>See <a href="/during/during_an_incident">During an Incident</a>.</li>
          <li>Open Tickets with Customers.</li>
          <li>Notify team in Slack #general Channel.</li>
          <li>Public notification if this is MNX.io related that involves one or more customers.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td class="high">High</td>
      <td>
        <p class="intent">Critical system issue actively impacting many customers' ability to use the product.</p>
        <ul>
          <li>The system is in a vulnerable state.</li>
          <li>Service not directly impacted but can be soon (Ex. Disk filling up that could cause service outage if not handled).</li>
          <li>Cron jobs not executing that could cause issues later down the road in providing responses.</li>
          <li>Any other event to which a MNX Solutions employee deems necessary of incident response.</li>
        </ul>
      </td>
      <td>
        <p class="response">High-Urgency Page.</p>
        <ul>
          <li>See <a href="/during/during_an_incident">During an Incident</a>.</li>
          <li>Open Tickets with Customers.</li>
          <li>Notify team in Slack #general Channel.</li>
        </ul>
    </tr>
    <tr>
      <td class="warning" colspan="3">Anything above this line is considered a "Major Incident" and will page our on call person. Our incident response process should be triggered for any major incidents.</td>
    </tr>
    <tr>
      <td class="medium">Medium</td>
      <td>
        <p class="intent">Stability or minor customer-impacting issues that require attention from ticket owners.</p>
        <ul>
          <li>Ad-Hoc/Project based work that needs to be handled during a time period to prevent a major issues.</li>
          <li>SSL Certificates that are about to expire in the coming weeks.</li>
          <li>Something that has the likelihood of becoming High Priority if nothing is done (IE, LogRotate not configured properly, etc...).</li>
        </ul>
      </td>
      <td>
        <p class="response">Medium Ticket Creation.</p>
        <ul>
          <li>Work on these after you have completed all tasks with higher priorities.</li>
          <li>Work on tickets/issues as assigned.</li>
          <li>Keep in contact with customer and notify of any impending issues/delays..</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td class="low">Low</td>
      <td>
        <p class="intent">Minor issues requiring action, but not affecting customer ability to use the product.</p>
        <ul>
          <li>Ad-Hoc/Project based work..</li>
          <li>Migration based projects of sites/servers.</li>
          <li>Installing packages/reconfiguring configuration files/services.</li>
        </ul>
      </td>
      <td>
        <p class="response">Low Ticket Creation.</p>
        <ul>
          <li>Work on these after you have completed all tasks with higher priorities.</li>
          <li>Work on tickets/issues as assigned.</li>
          <li>Keep in contact with customer and notify of any impending issues/delays..</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

!!! note "Be Specific"
    These priority descriptions have been changed from the PagerDuty internal definitions to be more generic. For your own documentation, you are encouraged to make your definitions very specific, usually referring to a % of users/accounts affected. You will usually want your severity definitions to be metric driven.
