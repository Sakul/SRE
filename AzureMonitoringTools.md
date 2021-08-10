# Azure Tools

## Azure Tools for operational awareness
* **Application Insights** - virtualize communication, connections, number of calls made, average latency for those components
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/application-map.png)
* **Azure Resource Graph** - lets you run arbitrary queries that return real-time answers via `Kusto Query Language (KQL)`
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/resource-graph-explorer-results.png)
* **Dashboards** - summarize the system at anything you want like graphs, charts, counters, enabled to share pre-setup exactly as we need via `JSON` file
![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/azure-inventory-dashboard.png)

## Azure Monitor
It's a comprehensive platform for monitoring Azure resources

### Data sources
It's data that comes into the system such as Applications, Operating Systems, Azure Resources, Azure Subscriptions, Azure Tenants, Custom Sources

### Data types
* **Metrics** - `numerical` pieces of information from counters
* **Log data** - `logs` such as Windows event, Linux syslog, VM's agents, custom, telemetry, etc

![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/azure-monitor-overview-full.png)

> Azure have a lot of tools that will let us analyze, visualize, respond to specific contents, and integrate that data with other tools.

## Log analytics
It allow us to query logs' data and display it via `Kusto Query Language (KQL)`

![img](https://docs.microsoft.com/en-us/learn/advocates/improve-reliability-monitoring/media/log-analytics-requests-table.png)

```sql
requests
|where timestamp > ago(30m)
|summarize count() by name, URL
```

> [Log Analytics Tutorial](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-tutorial)
