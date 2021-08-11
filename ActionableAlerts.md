# Actionable alerts
Alerts are designed to notify you when there is a problem with your systems but we should avoid `Alert Fatigue` such as `Logs`, `Notifications` (not intended to announce non-critical occurrences), `Heartbeats`

Some situations we may need 
* **Human** - to investigate
* **Automated processes**

> It shouldn't page you at 2AM to tell you about unnecessary alerts

## Create actionable alerts
* **Simplicity** - don't make an alert that requires the recipient to have to puzzle over it before they know what to do
* **Scope** - scope of the problem (single server? One service? A whole region?)
* **Context** - needed information to know to get started dealing with it

## Context in the alert
* `Where` is the alert coming from
* `What` expectation was violated
* `Why` is this an issue (customer perspective)
* What are the `next steps` to take
