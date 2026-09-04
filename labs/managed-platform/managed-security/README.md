---
title: "Managed Security"
level: 300
persona: "Power Apps makers, admins"
estimated_duration: "120 minutes"
tags: [strengthen-governance-and-security]
author: "Power CAT"
last_updated: "2026-08-10"
version: "1.0"
description: "Secure your Power Platform environment layer by layer."
---

# Managed security

Built by: Power CAT

This workshop series walks you through securing a Power Platform environment layer by layer, following Woodgrove Bank — a retail bank whose sales environment holds customer data — as its security review raises one finding after another: who owns the encryption keys, where the data can be accessed from, and whether a stolen session can be replayed.

The recommended order below follows that storyline, but it is only a narrative thread: the modules have **no technical dependencies** on each other, and each one stands alone. Pick and choose the modules relevant to your organization — or complete all three in order for the full story.

## Modules in this series

| Order | Module | Description |
|-------|--------|-------------|
| 1 | [Customer-managed keys (CMK)](cmk/README.md) | Encrypt the environment with a key you create, rotate, and can revoke in your own Azure Key Vault |
| 2 | [IP firewall in Dataverse](ip-firewall/README.md) | Restrict access to the environment to allow-listed IP ranges, enforced in real time at the network layer |
| 3 | [IP cookie binding in Dataverse](ip-cookie-binding/README.md) | Protect sessions against cookie replay attacks by binding each cookie to the IP address it was issued to |

## What you secure, layer by layer

- **Data at rest.** With CMK, the bank owns the full lifecycle of the encryption key protecting its data — including the ability to revoke it.
- **The network boundary.** With IP firewall, the environment is reachable only from trusted corporate IP ranges.
- **The session.** With IP cookie binding, a stolen cookie replayed from another machine is rejected in real time and the administrator is alerted.

## Configuring at scale

The labs in this series configure each setting on a single environment, which keeps the walkthroughs focused — but all three protections scale beyond one environment:

- **IP firewall and IP cookie binding** can also be configured at the environment group level: in the Power Platform admin center, go to **Manage** > **Environment groups**, open your group, and add the corresponding rule on the **Rules** tab — the same settings then apply to every environment in the group at once.
- **Customer-managed keys** scale through the enterprise policy itself: one policy can be added to multiple environments in the same region.

Both the IP firewall and IP cookie binding can be configured per environment group: you define the settings once, and they're applied automatically to every environment in the group — including environments added to the group later. Only CMK works differently, scaling through its enterprise policy rather than a group-level setting. To create the environment groups themselves and manage rules at scale, work through the [Environment Strategy and Managed Governance module](../managed-governance/environment-strategy-and-governance/README.md).

> 💡 Prerequisites differ per module — check each module's README before starting. All three require administrative access to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and all three features apply to **Managed Environments**: the IP firewall and IP cookie binding settings can only be turned on for a managed environment, and the customer-managed key policy is only enforced on environments activated for Managed Environments.
