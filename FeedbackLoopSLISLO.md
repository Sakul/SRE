# Feedback Loop
The right feedback loops improve reliability in your organization

## Service Level Indicator (SLI)
🤔 How to measure the reliability of our system?  
> Where to measure?

Example
* The ratio of successful to total requests as measured at the load balancer for `Availability`

## Service Level Objective (SLO)
🤔 If we find our web server's availability is indeed 80% available. Is that a good or a bad thing?
> The objective for a SLI for clearly state your goal
### The basic recipe for creating an SLO
* Thing
* Desired proportion - 50%, return < 10ms in 90% of the time
* Time horizon - last 10 minutes? 30 days? rolling window? monthly?

Example
* 90% of HTTP requests as reported by the client returned in <20ms in the last 30-day window

## SLI & SLO on Azure Monitor
```sql
requests
| where timestamp > ago(5h)
| summarize succeed = count (success == true), failed = count (success == false), total = count() by bin(timestamp, 5m)
| extend SLI = succeed * 100.00 / total
| extend SLO = 80.0
| project SLI, timestamp, SLO
| render timechart
```
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/slo-example.png)
> Number of successful / failed requests in the last 30 days (in 5-minute buckets)

## Using SLI & SLO
SLIs and SLOs are work-planning tools (sort of feedback loops, immediate monitoring/response system)
