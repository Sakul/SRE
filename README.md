# Site Reliability Engineering (SRE)

## 🤔 What's SRE?
```csharp
public class SRE : DevOps
// DevOps -> Delivery
// SRE -> Reliability
```
> `Site Reliability Engineering` is an engineering discipline devoted to helping an organization sustainably achieve the appropriate level of reliability in their systems, services, and products.

# 💖 Reliability
Reliability has to be measured from the customer’s perspective, not the component perspective

## Aspects of Reliability
* **Availability** - is the system "up" or is it "down?"
* **Latency** - amount of delay between a request and a response
* **Throughput** - measure of the rate at which something is processed
* **Coverage** - how much of the data that you expected to process was actually processed
* **Correctness** - does result correctly as expected?
* **Fidelity** - `degraded experience` instead of not being able to work
* **Freshness** - how up to date the information is in situations where timeliness matters to the customer
* **Durability** - expected of your user to your service's durability

---

## 🔥 Changing the frame
### 🤯 Reframing #1: Reliability from the customer’s perspective
**🤔 Question**  
You have a web farm with 100 server instances. Suddenly, 14 of these 100 instances stop working due to an operating system failure. Which of the following is true in this situation?
* A: It’s no big deal.
* B: It’s a serious matter. You should stop whatever you’re doing and get those 14 server instances back into service as soon as possible.
* C: It’s an existential crisis for the business. You should notify C-level executives and call everyone in to work to take care of the situation as fast as possible  

**🤠 Answer**  
It depends on how your customers are experiencing this outage  
* If no customers even noticed the back ends going down and the other 86 server instances are shouldering the load with no problems, then there’s no crisis here
* If the outage cause losing serious amounts of money for every minute those servers are down, then there’s a crisis

### 🤯 Reframing #2: Appropriate levels of reliability
100% reliable is almost never the right goal, we don't really need things to be 100% reliable. And in fact, 100% reliable isn't often possible.

---

# 💖 The Dickerson hierarchy
> ## TLDR
> * **Monitoring** - source of information that allows you to have concrete conversations
> * **Incident response** - triaging & mitigating the problem
> * **Post-Incident Review** - learning from failure
> (investigating, reviewing, discussing of each significant incident)
> * **Testing/Release** - deployment (catch problems before they cause incidents?)
> * **Capacity/Scaling** - attention to capacity planning and scaling as ways of addressing that threat
> * **Dev & UX** - out of scope of this repo 😥

![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-introduction/media/dickerson-hierarchy.png)

## 1️⃣ Monitoring
🤔 What exactly is running in production? ... to answer the question we need to collect information about
* **Normal & Past performance** - it may give us at least some sense of potential failure modes
* **Context** - clear idea of who the stakeholders are

### Learning paths for monitoring
* [Azure Tools for operational awareness](/AzureMonitoringTools.md)
* [Feedback Loop by SLI & SLO](/FeedbackLoopSLISLO.md)
* [Actionable Alerts](/ActionableAlerts.md)
* [Azure Monitor for Actionable Alerts](/AzureMonitor.md)

## Inprogress
* Incident response
* Post-Incident Review
* Testing/Release
* Capacity/Scaling
* TBD

## References
* [Google SRE books](https://sre.google/books)
* [Improve your reliability with modern operations practices](https://docs.microsoft.com/en-us/learn/paths/improve-reliability-modern-operations)
* [Incident response with alerting on Azure](https://docs.microsoft.com/en-us/learn/modules/incident-response-with-alerting-on-azure)
