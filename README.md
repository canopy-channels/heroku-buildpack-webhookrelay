# heroku-buildpack-stripecli
Heroku buildpack that installs Webhook Relay.

## Why is this useful?
Webhooks are an increasingly common way for third-party services to inform backends about new events that happen. For example, Stripe might reach out to a Ruby on Rails backend to inform the backend about a new subscriber to a service.

Often these webhook endpoints have limitations that make them difficult to set up in dynamically spun-up environments. For example, there might be a low cap on the number of webhook endpoints (e.g. 16 for Stripe test mode) or they might need to be added and removed via a dashboard.

Heroku Review Apps are a prime example of this: a new review app is created for each pull request, but how do you ensure that review app sets up and tears down any necessary webhooks?

Webhook Relay helps solve this problem by providing a static endpoint to send these webhooks to and allowing subscribers to dynamically subscribe and unsubscribe as the application is set up and torn down.

This buildpack makes the Webhook Relay CLI available for Heroku applications.

## Thanks
Thank you to [heroku/heroku-buildpack-awscli](https://github.com/heroku/heroku-buildpack-awscli), which served as a great reference while writing this.
