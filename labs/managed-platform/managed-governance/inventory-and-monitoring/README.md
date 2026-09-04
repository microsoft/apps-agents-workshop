---
title: "Managed Operations: Inventory & Monitoring"
level: 200
persona: "Power Apps makers, admins"
estimated_duration: "120 minutes"
tags: [strengthen-governance-and-security]
author: "Power CAT"
last_updated: "2026-08-10"
version: "1.0"
---


# Inventory and Monitoring workshop — Module 2

Built by: Power CAT

In this module you continue in the role of your organization's **Power Platform Lead**. Governance gave makers a safe place to build — but it also gave you a new obligation: leadership now expects you to know what exists across the tenant, what actually matters, and whether it's healthy. Across eleven labs you build that visibility in two arcs: first an **inventory** you can search, query, and report on; then a **monitoring and alerting system** that watches your resources and tells you when something needs attention.

## Labs in this module

| Lab | Description |
|-----|-------------|
| [Open inventory](01-open-inventory.md) | Open Power Platform inventory, search it, and drill from a row into resource details and connectors |
| [Add columns](02-add-columns.md) | Add the **Last modified by** column and sort by newest changes to track what's moving |
| [Filter inventory](03-filter-inventory.md) | Combine environment, owner, and date filters to narrow inventory to a precise list |
| [Export inventory to CSV](04-export-inventory-csv.md) | Download a filtered inventory export for offline analysis and sharing |
| [Query with Azure Resource Graph](05-query-resource-graph.md) | Run KQL against the `PowerPlatformResources` table to rank environments and analyze connector impact |
| [Explore the Usage tab](06-explore-usage-tab.md) | Review adoption trends and the most used apps, flows, and agents — tenant-wide and per environment |
| [Export inventory with a cloud flow](07-export-inventory-flow.md) | Build a Power Automate flow that pages through the inventory API and writes to Excel |
| [Monitor overview](08-monitor-overview.md) | Inspect health charts and recommendations for apps and flows |
| [View and export logs](09-view-logs.md) | Drill from a metric into the runtime events behind it and export them |
| [Create a custom alert rule](10-create-alert-rule.md) | Set up a threshold-based alert on a Managed Environment with email notifications |
| [Review triggered and predefined alerts](11-review-alerts.md) | See where triggered alerts land and meet the predefined alerts Microsoft runs for you |

## Prerequisites

1. You have a supported admin role in Microsoft Entra ID — **Power Platform administrator** or **Dynamics 365 administrator** covers all labs in this module.
2. You have at least one environment that contains apps, flows, or agents with recent activity.
3. For the Azure Resource Graph lab, your admin account can sign in to the [Azure portal](https://portal.azure.com). No Azure subscription is required — inventory is queried at the Directory (tenant) scope.
4. For the alert labs, at least one of your environments must be a **Managed Environment** — alerts can only be placed on Managed Environments.
5. Tenant-level analytics must be turned on in the Power Platform admin center for the monitoring labs.

> 💡 If the inventory page fails to load, this may be caused by conditional access policies for Azure Resource Manager. See [Power Platform inventory — Known limitations](https://learn.microsoft.com/power-platform/admin/power-platform-inventory#known-limitations) for resolution steps.

## Business use case

**Scenario:** Adoption is healthy and growing — makers are shipping apps, flows, and agents across dozens of environments. What's missing is your side of the picture. When a connector deprecation notice arrives, nobody can quickly say which resources are affected. When a maker resigns, nobody has a list of what they own. And when the most-used app in the tenant starts failing on a Monday morning, you find out from user complaints — hours after the platform itself knew. None of these are made-up problems; they're the routine events that separate organizations with visibility from organizations with a mess.

This module builds the answer in two halves:

- **Inventorying** every app, flow, and agent across the tenant — searchable in the admin center, queryable with KQL through Azure Resource Graph, and exportable on a schedule through the inventory API, with connector usage included.
- **Understanding impact** through the Usage page: which resources people actually use, tenant-wide and per environment, so governance effort follows the usage rather than the count.
- **Monitoring** performance and reliability in the Monitor area: health metrics, recommendations, and the runtime event logs behind them.
- **Alerting** on what matters: custom threshold rules that email you when a metric crosses the line, backed by Microsoft's predefined alerts for high-use resources.

### The importance of inventory and monitoring

- **Compliance and risk management:** Know which apps access which connectors and data, and answer impact questions in minutes instead of meetings.
- **Operational health:** Find failing flows and underperforming apps before they disrupt business processes — and be notified instead of having to look.
- **Cost optimization:** See where usage concentrates to guide licensing and capacity decisions.
- **Maker enablement:** Reach the right owner with the right evidence — usage data, health metrics, and logs — instead of vague reports.

### What you learn

By the end of this module, you can:

- View, search, filter, and export inventory in the Power Platform admin center.
- Query Power Platform inventory with KQL in Azure Resource Graph, including environment rankings and connector impact analysis.
- Review tenant-wide and per-environment usage to identify the resources that matter most.
- Build a cloud flow that uses the inventory API to generate a structured export in Excel.
- Read health metrics and recommendations in Monitor, and drill into the event logs behind them.
- Create custom alert rules with email notifications, and work with the predefined alerts Microsoft provides.

> 🥳 Ready to get started? Go through the labs table above in order because the labs partially build on each other.
