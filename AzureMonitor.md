# Azure Monitor for Actionable Alerts

![img](https://docs.microsoft.com/en-us/learn/modules/incident-response-with-alerting-on-azure/media/2-azure-resource-signal-types.svg)

## Composition of an alert rule
* **RESOURCE** - single/multiple *target resources* to be used for the alert rule
* **CONDITION** 
	* *Signal type* to be used to assess the rule
	* *Alert logic* applied to the data that's supplied via the signal type
* **ACTIONS** - *action/action group* of things you want it to do
* **ALERT DETAILS**
	* *alert name* & *alert description* are specify the alert's purpose
	* *severity* of the alert 0:Critical, 1:Error, 2:Warning, 3:Informational, 4:Verbose

## Scope of alert rules
* Metric values
* Log search queries
* Activity log events
* Health of the underlying Azure platform
* Tests for website availability
> Not available yet
> * Service health alerts based on activity logs
> * Web availability tests through Application Insights

## Manage alert rules
* Run forever
* Enable / Disable

## Alert summary view
* **Subscription** - maximum 5 subscriptions
* **Resource groups** - only one resource group
* **Time ranges** - hourly, daily, weekly, monthly

## Alert state
* `New` - the issue has been detected, but not yet * reviewed
* `Acknowledged` - after an admin has reviewed the alert
* `Closed` - the issue is resolved

## Filter alerts
To filter the **Alert summary**
* Smart groups - You can select this filter if it's enabled
* Resource type - Applies only when it's used with a resource group
* Resource - Applies only when a resource type has been specified
* Severity - Identifies the severity assigned by the alert rule
* Monitor condition - Set by the system and indicates if the alert is fired or resolved
* Alert state - Typically, finds the New and Acknowledged alerts

---

## Metric alert
* Monitor `Performance`
* Use thresholds to monitor specific resources (ex. Free disk space on a server is less than 5%)

### Composition
* **Static** - simple static conditions and thresholds that you define such as "threshold of 85 percent CPU utilization checks the rule every 2 minutes"
* **Dynamic** - improve the accuracy of the thresholds defined by the initial rule

### Dimensions
You can monitoring data from multiple target instances such as monitor CPU utilization across all the servers running your app (supported `*` as `wildcard`)

---

## Log alerts
* Monitor `Events`
* You can capture from log files by defines the `Log search rule`

### Composition of log search rules
* **Log query** - Query that runs every time the alert rule fires
* **Time period** - Time range for the query
* **Frequency** - How often the query should run
* **Threshold** - Trigger point for an alert to be created

Log search results are one of two types
* **Number of records**
	* Use this when you're working with an event or event-driven data (ex. Web app responses)
	* It returns a **Single alert** when the number of records in a search result reaches or exceeds the value for the number of records (threshold)
* **Metric measurement** - like metric alert logs but it require additional criteria to be set
	* **Aggregate function** - the calculation that will be made against the result data (count, average)
	* **Group field** - a field by which the result will be grouped. it used in conjunction with the aggregated value
	* **Interval** - the time interval by which data is aggregated
	* **Threshold** - a point defined by an aggregated value and the total number of breaches
> One use for this type of alert is to respond if a particular trend or pattern is found (metric measurements greatly reduce the volume of alerts that are produced)

## Stateless nature
They are stateless (It will generate new alerts every time the rule criteria are triggered, regardless of whether the alert was previously recorded)

---

## Activity log
It enable you to be notified when a specific event happens on some Azure resource such as someone creates a new VM in a subscription

### When to use it?
It designed to work with `Azure resources` (ex. Changes occur on a resource within your Azure subscription)

### Types
* **Specific operations** - scope with specific resources or a resource group
* **Service health events** - include notice of incidents and maintenance of target resources

### Composition
* Category - administrative, service health, autoscale, policy, or recommendation
* Scope - resource level, resource group level, or subscription level
* Resource group - where the alert rule is saved
* Resource type - namespace for the target of the alert
* Operation name - operation name
* Level - verbose, informational, warning, error, or critical
* Status - started, failed, or succeeded
* Event initiated by- email address or Azure Active Directory identifier (known as the "caller") for the user

### Perform actions when an alert happens
When any event is triggered, you can create an associated action in an `Action group`. Also you can reuse action groups on multiple alerts. The available actions are:
* Send an email
* Send an SMS message
* Create an Azure app push notification
* Make a voice call to a number
* Call an Azure function
* Trigger a logic app
* Send a notification to a webhook
* Create an ITSM ticket
* Use a runbook (to restart a VM, or scale a VM up or down)

---

## Smart groups
* Smart groups are an automatic feature of Azure Monitor
* They using ML for reduce the alert noise and make the task of managing alerts easier
* Name of the smart group can't be changed or amended
* they have their own state, like regular alerts

![img](https://docs.microsoft.com/en-us/learn/modules/incident-response-with-alerting-on-azure/media/8-smart-group-all-alerts.jpg)
