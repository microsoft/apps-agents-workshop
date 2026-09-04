---
title: "Managed Governance: Environment Strategy & Governance"
level: 200
persona: "Power Apps makers, admins"
estimated_duration: "120 minutes"
tags: [strengthen-governance-and-security]
author: "Power CAT"
last_updated: "2026-08-10"
version: "1.0"
---


# Environment Strategy and Managed Governance workshop — Module 1

Built by: Power CAT

In this module you take on the role of your organization's **Power Platform Lead**. Your job is to build a Safe Innovation Zone — a governed environment group where every maker gets a personal developer environment with consistent rules applied automatically. Across nine labs you stand it up one guardrail at a time, turning ungoverned sprawl into a place where makers can move fast while risk stays contained.

## Labs in this module

| Lab | Description |
|-----|-------------|
| [Create an environment group](01-create-environment-group.md) | Create the Safe Innovation Zone and understand environment groups |
| [Configure connector policy](02-configure-connector-policy.md) | Set up advanced connector policies to control which connectors makers can use |
| [Configure sharing limits](03-configure-sharing-limits.md) | Restrict how broadly canvas apps can be shared |
| [Configure additional rules](04-configure-additional-rules.md) | Set up solution checker, usage insights, backup retention, and apply all rules |
| [Configure maker welcome](05-configure-maker-welcome.md) | Embed onboarding guidance directly in Power Apps |
| [Configure environment routing](06-configure-environment-routing.md) | Route new makers to the Safe Innovation Zone |
| [Test sharing limits](07-test-sharing-limits.md) | Verify that sharing limits and routing work as expected |
| [Configure default pipeline](08-configure-default-pipeline.md) | Set up a deployment pipeline for the Safe Innovation Zone |
| [Clean up default environment](09-clean-up-default-environment.md) | Migrate apps out of the default environment |

## Prerequisites

1. You have the **Power Platform administrator** role assigned in Microsoft Entra ID (tenant administrator).
2. You have access to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/).
3. For the pipeline lab, you create a pipelines host and install the **Power Platform Pipelines** package as part of the lab. All target environments used in pipelines must be **Managed Environments**.
4. For the cleanup lab, at least one app must exist in your default environment for the advisor recommendation to appear.

> 💡 If you don't have a tenant yet, either use the [Customer Digital Experiences (CDX) Portal](https://cdx.transform.microsoft.com/), or use the [Microsoft 365 Developer Program](https://developer.microsoft.com/en-us/microsoft-365/dev-program) to request a new one. This [YouTube video](https://www.youtube.com/watch?v=Wzwb5HFTqzk) provides guidance on how to get a tenant for free or at a minimal cost. Keep in mind that frontier and preview features become available in the US region first. It is also recommended for demo tenants to set the Release preferences in the M365 admin center to **Targeted release for everyone**. Navigate to the M365 admin center, select **Show all** to expand the left navigation pane, expand **Settings**, select **Org settings**, select the **Organization profile** tab, and then select **Release preferences**.

## Business use case

**Scenario:** You are the Power Platform Lead for your organization, and you have inherited a problem. Adoption took off faster than anyone planned, and almost all of it landed in one shared default environment — tens of thousands of apps, flows, and agents with no owner, no guardrails, and no visibility into what is running or why. Recently, a maker shared an app full of sensitive data with far more people than intended, and no one caught it until afterward. Leadership's mandate is clear: bring it under control, but don't slow the makers down.

To put the scale in perspective, Microsoft's own default environment has over 100,000 users, 65,000 canvas apps, 12,000 cloud flows, and 5,000 agents — and that number keeps climbing. Managing risk and compliance at that scale becomes nearly impossible without a structured approach.

Over the next nine labs, you build the answer: an environment strategy that shifts your organization from "everyone builds everywhere" to "everyone builds safely" — empowering innovation while keeping risk under control:

- **Organizing** environments into governed groups with consistent rules applied at scale.
- **Controlling** what can be built, how broadly it can be shared, and which connectors are available.
- **Routing** makers away from the default environment and into secure, personal developer environments.
- **Standardizing** deployment practices with default pipelines across environment groups.
- **Cleaning up** the default environment by migrating apps to designated managed environments.

### The importance of environment strategy

- **Compliance and risk management:** Apply connector policies and sharing limits consistently, eliminating ungoverned development.
- **Operational efficiency:** Route makers automatically — no manual intervention from IT required.
- **Cost control:** Restrict sharing to prevent broad, accidental exposure that drives unnecessary licensing costs.
- **Maker enablement:** Provide embedded onboarding guidance so every maker starts in a secure, well-governed workspace from day one.

### What you learn

By the end of this module, you can:

- Create and configure environment groups with governance rules.
- Set up advanced connector policies, sharing limits, and additional rules.
- Embed maker welcome content directly in Power Apps.
- Route makers to governed developer environments instead of the default environment.
- Configure a default deployment pipeline for an environment group.
- Migrate apps out of the default environment using manual and automated approaches.

> 🥳 Ready to get started? Go through the labs table above in order because the labs partially build on each other.
