# Expeditor

Congratulations! You've been trusted with a noble and powerful honor: the role of Expeditor. Do not fear. While it carries with it a great responsibility, you shall prevail. Follow these steps, and you shall go down in Expeditor history. (History that's only a few months old is still history.) And besides, you only have to survive the rest of the week. (We must all share the ~~burden~~ responsibility.)

The expeditor's duties are thus:

* You will be on pagerduty rotation.
* Daily check of newrelic from the past 24 hours, for PipelineDeals and all major service apps (william, etc).

## PagerDuty rotation

If pagerduty blows up, you are front and center.  See the [site emergency checklist](https://github.com/PipelineDeals/pipeline_deals/wiki/Site-emergency-checklist-and-contact-info) if you get paged.


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

Run `hubot deploy pld:check` in the Operations Room.

[k&g]: mailto:kevin@pipelinedealsco.com,grant@pipelinedealsco.com?subject=Tomorrow's%20UI%20Deploy:%20Red%20Team%20stuff

[GH UI PRs]: https://github.com/pulls?utf8=%E2%9C%93&q=is%3Aopen+is%3Apr+user%3APipelineDeals+label%3A%22Hold+for+UI+deploy%22+-label%3AWIP

[Production]: https://rpm.newrelic.com/accounts/7082/applications/1944961/traced_errors
[PipelineGoogle]: https://rpm.newrelic.com/accounts/7082/applications/3658335/traced_errors
[William]: https://rpm.newrelic.com/accounts/7082/applications/4073616/traced_errors
[PipelineEmail]: https://rpm.newrelic.com/accounts/7082/applications/2102351/traced_errors

