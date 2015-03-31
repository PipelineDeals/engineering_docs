# Expeditor

Congratulations! You've been trusted with a noble and powerful honor: the role of Expeditor. Do not fear. While it carries with it a great responsibility, you shall prevail. Follow these steps, and you shall go down in Expeditor history. (History that's only a few months old is still history.) And besides, you only have to survive the rest of the week. (We must all share the ~~burden~~ responsibility.)

## Manage Daily Deploy

There's a deploy happening at 11am. Is master prepared? Are you prepared? Here are some guidelines to get set up:

* Check [GitHub][GH bug PRs] for open bug PRs.
  * Perform code review. When approved, mark as such via Hubot. (hubot room: `hubot pr qa accept PRNUMGOESHERE`)
  * When the PR has been approved by both QA and BO, merge it to master. (hubot room: `hubot pr merge PRNUMGOESHERE`)
* Martin/Scott will manage the deploy at 11am.
  * You can see what has been merged by checking out the [latest release][] and clicking the "## commits to master" link.
  * If there are migrations to run, please coordinate with the deployer to make sure they're run properly.

## Check NewRelic for Errors

You're going to want to keep an eye on any errors popping up in the app, especially if they're recent.

* Check NewRelic for errors.
  * On Monday, set "Time Picker" to 3 days. For the rest of the week, set it to "24 hours".
  * Apps:
    * [Production][]
    * [PipelineGoogle][]
    * [William][]
    * [PipelineEmail][]
* If you find a ticketable error, click "File a ticket in JIRA 5" link on the error page.
  * This will create an MBL ticket with a link to the error in NewRelic.
  * Feel free to add to the description or comment with some context that will help the product and customer care teams prioritize the work.
* Try to focus on errors that occur often or could be related to recent deploys.

[GH bug PRs]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3APipelineDeals+label%3Abug
[latest release]: https://github.com/PipelineDeals/pipeline_deals/releases/latest

[Production]: https://rpm.newrelic.com/accounts/7082/applications/1944961/traced_errors
[PipelineGoogle]: https://rpm.newrelic.com/accounts/7082/applications/3658335/traced_errors
[William]: https://rpm.newrelic.com/accounts/7082/applications/4073616/traced_errors
[PipelineEmail]: https://rpm.newrelic.com/accounts/7082/applications/2102351/traced_errors
