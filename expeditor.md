# Expeditor

Congratulations! You've been trusted with a noble and powerful honor: the role of Expeditor. Do not fear. While it carries with it a great responsibility, you shall prevail. Follow these steps, and you shall go down in Expeditor history. (History that's only a few months old is still history.) And besides, you only have to survive the rest of the week. (We must all share the ~~burden~~ responsibility.)

## Manage Daily Deploys

We'd like to have a scheduled deploy every day at/around 11am ET. Here are some guidelines to help the process along:

### Monday-Friday

* Every day's deploy will (mostly) consist of bug PRs that were managed by the White Team.
* Check with the White Team leader (Scott) to see if/that all the PRs to go out today are ready.
* If there are migrations to run, be sure to get them taken care of.

### Thursday

* Thursday's deploy will also include customer-facing UI tickets.
* At end-of-day Wednesday, take a look at the [upcoming UI PRs][GH UI PRs] to see what's coming up.
* If there are migrations that require low-traffic, check with Scott to plan their execution.
* You will be responsible for merging the UI PRs waiting for you on Thursday morning.
  * If there are conflicts, check with the team leads to see about resolving them.

## Check NewRelic for Errors

You're going to want to keep an eye on any errors popping up in the app, especially if they're recent.

* Check NewRelic for errors.
  * On Monday, set "Time Picker" to 3 days. For the rest of the week, set it to "24 hours".
  * Apps:
    * [Production][]
    * [PipelineGoogle][]
    * [William][]
    * [PipelineEmail][]
* ~~If you find a ticketable error, click "File a ticket in JIRA 5" link on the error page.~~
* If you find a ticketable error, create an issue in Jira.
  * Feel free to add to the description or comment with some context that will help the product and customer care teams prioritize the work.
* Try to focus on errors that occur often or could be related to recent deploys.

## FAQs

### I'd like to cleanup post-deploy. How do I check the status of the old queues?

Run `hubot queue stats` in the Operations Room.

### The build check failed, but I'm suspicious. How can I run it manually?

1. Download/install/configure [`pd-cli`][pd-cli].
2. Run `pd aws -a deployer` to get the IP address of the current deployer box.
3. SSH to said box.
4. Open a Rails console.
5. Run `PldBuildCheckWorker.perform_async`. The results will display in the Operations Room.

[GH UI PRs]: https://github.com/pulls?utf8=%E2%9C%93&q=is%3Aopen+is%3Apr+user%3APipelineDeals+label%3A%22Hold+for+UI+deploy%22++-label%3AWIP

[Production]: https://rpm.newrelic.com/accounts/7082/applications/1944961/traced_errors
[PipelineGoogle]: https://rpm.newrelic.com/accounts/7082/applications/3658335/traced_errors
[William]: https://rpm.newrelic.com/accounts/7082/applications/4073616/traced_errors
[PipelineEmail]: https://rpm.newrelic.com/accounts/7082/applications/2102351/traced_errors

[pd-cli]: https://github.com/PipelineDeals/pd_cli
