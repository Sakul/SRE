# 2️⃣ Incident response
* 100% reliable is not the goal
* Things will go wrong, so we need a `plan to limit the impact` on our end users and return operations to normal as quickly as possible `💖 Respond with urgency`
* Incident is a service disruption that `impacts your customers`

Effective incident response approach
* Understanding what’s going on (`diagnosing` the problem)
* Triaging (determining the urgency) and `prioritizing` the problem
* Engaging the right resources to `mitigate` the issue(s)
* `Communicating` with stakeholders about the problem

## Measuring incident response performance
* `TTR` - Time To Recover/Remediate/Restore (they are all the same) it is the total amount of time it takes for you to bring services back
* Using TTR for measuring how well teams are performing when responding to incidents

> **NOTE**  
> * High performing teams recover from incidents 2,604 times more quickly than their “low performing” peers  
> * High performers also are deploying to production 208 times more often  
> They understand the importance of having a good foundational response plan already in place when things inevitably go wrong

## Phases of an incident
* **Detection** - monitor the customer-centric objectives, send actionable alerts
* **Response** - mitigating the impact and/or restoring the service including communication flows both between the responders and to those interested in the incident’s progress
* **Remediation** - restore the systems to normal functionality (your job doesn’t stop once that’s done)
* **Analysis** - gathering the information on just what happened and when during the incident and seeing what can be learned from it by asking the right questions (`Finding root cause`)
* **Readiness** - prevent a similar outage in the future

![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-incidents/media/lifecycle.png)

> **NOTE**  
> Before you create an incident response plan, you need to understand the characteristics and value of incidents

---

# 🔥 Foundations
* 💖 Reliability  is built on the foundational level of `Monitoring` and `Incident response`
* Good incident response plan is supported by three pillars **Rosters**, **Roles**, **Rotations**

## Rosters
* It's a list of people who are assigned to the **on-call team** (made up of multiple engineers)
* These team members should have the knowledge & skills

## Roles
* **Primary responder** - first on-call engineer
* **Secondary responder** - who is a backup incase the primary responder isn’t available
* **Subject matter experts** - people who have in-depth knowledge for assistance (they are not on call all the time)
* **Incident commander** - who coordinates a lot of the conversation and the effort regarding the response and remediation activities. They keep an eye on the `big picture` and let engineers stay focuse on their works
* **Scribe** - document the conversation around the incident
* **Communication coordinator** - conjunction with the incident commander to share information about the incident

## Rotations
Schedule assigns the shifts for which each person is on call (shouldn't be assigned randomly)
* **24 x 7** -  **CAUTION**: shift rotations longer than three to four days can be detrimental to the overall health of the engineering staff
* **Follow the sun shifts** - normal working hours and at the end of their workday shift to another colleague located in a different time zone

---

# 🔥 Incident tracking
To respond most effectively, you need to be able to track the evolution of the incident lifecycle and respond from the very beginning of that cycle

## Assess what you know
* `When` did you first know about the problem?
* `How` did you find out about the problem?
* `Who` should be aware of the issue?
* How bad is it? Who is affected?
* What (if anything) is being done about it? Has someone started taking action to address it?

## Standardize where incident information will be tracked
Keep and share your list of incidents (active or otherwise)

## Create space for conversation
`Unique channel` for the people working on that incident to communicate about it

## Automation
* When an urgent problem arises, all you really want to do is to be able to push the "go" button so work can immediately start to deal with the problem
* How we can automate the setup of the mechanisms for incident tracking and communication?

> **Sample - Use Logic Apps for codeless automation**  
> ![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-incidents/media/logic-app-overview.png)

---

# 🔥 Communication & collaboration
* **Timely** and **Clear sharing information** is an essential element of effectively responding to incident
* High performing organizations take a `proactive`, rather than reactive approach

## Prioritize for clear communications
Keys to prioritizing for clear communication
* Make sure you are `sharing information` about what is going on at each step of the way
* `Document the information` – put it in writing so that it’s less likely to be misunderstood or forgotten
* Place the information in a centralized location where it will be accessible to everyone who needs it
* Use `efficiency tools` for communications

## Communication tools: ChatOps
* A conversation-driven collaboration model
* Bots and AI to automate work
* Bring group chat tools into the conversation

> **Sample**: Use Microsoft Teams in your ChatOps solution

---

# 🔥 Remediation
* It should be all team members responsibility to have the system running to meet your reliability objectives
* Metrics, Logs, Queries are a good place to getting started
* Update stakeholders (prevent interruption)
	* What we know
	* What we’re doing
	* Amount of time to get it back

## Azure tools
* Azure Monitor Workbooks & Application Insights Troubleshooting Guides
	* Bulleted list of items to do or other helpful information
	* Links to other systems (dashboards, documentation, etc)
	* Kusto Query Language (KQL) queries
	* Customizable
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-incidents/media/troubleshooting-guide-samples.png)
