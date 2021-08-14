# 3️⃣ Post-incident
* The `Analysis phase` of the **Incident Response** lifecycle, We'll find `Root causes` of the incident
* 💖 Learning from failure for `Improvement` and `Prevention`

## Complex systems fail
* Complex systems are **NEVER 100% reliable** (especially in a cloud environment)
* System = hardware + software + peopleware (especially people have personalities, training, and knowledge)

---

# 🔥 Post-incident Review
* Make a review meeting after an incident about 24~36 hours (fresh memory, people forget things)
* Blameless 
	* Focus on `fact`
	* `Respect` people
	* Find weak points in our `process`
* Share information about all aspects of the incident so as learn and improve
* The result should be you know more about your systems than before instead of action item or bug report
* Review only significant incident

## Characteristics
Search for knowledge and context, not a hunt for who did what and a reaction to that

`4 Ds` for build more reliable systems
* Discussion
* Discourse
* Dissent
* Discovery

---

# 🔥 Review Process
💖 Goals: construction of a shared, accurate chronology that reflects the non-linear nature of an incident

## Gather the data
Before review we need gather data conversation and context (technical/non-technical) and from your monitoring system
* **Collect the conversation** - ideally people are sharing what worked and what failed, what they’re hesitant to try, what they’ve tried in the past. This conversation between the people as they work through and solve the issue is your best source of learning
* **Determine the context** - ideally we should be able to look at the monitoring system to build a point-in-time snapshot for the time period around or related to the incident
- **Find the changes** - find it from activity and audit logs

### 💡 Azure tools
#### Azure DevOps
* **Boards** suite as one place to collect all of the information about an incident starting from the initial response. It helps us with questions about when an incident was first declared, who was on call, who was assigned to the incident, and so forth.
* **Wiki** suit as gather the pieces of information about both the incident itself and the conversation that happened during the incident
#### Microsoft Graph API
It provides a programmatic way to find, export, and bring in the conversation that was collected inside the team channel devoted to this specific incident (include metadata & timestamps), also Microsoft Teams can query it.
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-failure/media/microsoft-graph-explorer.png)
```sql
AzureActivity
| where CategoryValue == 'Administrative'
| where OperationNameValue endswith "write" or OperationNameValue endswith "delete"
| project TimeGenerated, Level, ResourceGroup, ResourceId, OperationName, OperationNameValue, ActivityStatus, Caller
| order by TimeGenerated nulls first
```

---

# 🔥 Common traps to avoid

## Trap 1: Attribution to “human error”
When human error is deemed to be the reason for a failure, people stop there instead of further analyzing the incident. If we want to learn, we must not stop investigating when we find a human error
> Don't stop when we see/hear "human error", it is a signal that we need to look deeper

## Trap 2: Counterfactual reasoning
Counterfactual reasoning refers to telling a story about events that did not happen, in order to explain the events that did
> When someone talking about things that didn't happen instead of taking the time to understand how what did happen, just stop and look deeper

## Trap 3: Normative language
Normative thinking leads you to judge decisions based on their outcomes. This way of speaking isn’t logical because the outcome is the only piece of information that was not available to those who made the decisions and judgments. if we make judgments after the fact using information that was unavailable to the humans involved during the incident, we will neglect to understand how the actions of the operators made sense to them at the time.
> When you find that happen because of just a normative thing, don't stop and try to find the actual reasons (Why A? Why not B, C, D)

## Trap 4: Mechanistic reasoning
Mechanistic reasoning refers to the concept that a particular outcome can be inferred from intervention
> If your server is down because a kid pulled the plug out. We should find the reason why that kid can enter the server room instead of just blame that kid

---

# 🔥 Helpful practices
## Practice 1: Run a facilitated post-incident review
* **Meetings, not marathons** - the meetings don’t have to be long (60~90 minutes)
* **Pre-meeting prep** - tell an overview of the incident and ideas about which topics to talk about in the meeting
* **Not required for every incident** - start from smaller incidents or only once per month
> The post-incident review meeting is an opportunity to find out what went wrong, what was done right, and how failures can be handled better in the future. The ultimate goal is to improve reliability

## Practice 2: Ask better questions
* It’s better to ask people `How` or `What` instead of **Why** (why tends to push people to the defensive)
* The [Etsy Debriefing Facilitation Guide](https://extfiles.etsy.com/DebriefingFacilitationGuide.pdf)

## Practice 3: Ask how things went right

## Practice 4: Keep review and planning meetings separate
* Discuss `Repair items` and `Planning issues` in a **separate meeting** (do meeting with a smaller group)
* It's easier to avoid jumping to conclusions if you're not focused on how to fix it
* Allowing rest 1~2 days (subconscious can help you)
