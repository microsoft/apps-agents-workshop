# Automation foundations
<!-- PDF refresh trigger: 2026-07-24 -->

Built by: Power CAT

This module walks you through automating one business process — the Northwind Traders order lifecycle — end to end, using four different Power Platform automation tools and learning when each one is the right choice.

## Labs in this module

| Lab | Description |
|-----|-------------|
| [Module 1: Cloud Flow](01-cloud-flow.md) | Build a cloud flow that routes new orders through a two-tier approval and creates the invoice in Dataverse |
| [Module 2: RPA](02-rpa.md) | Import legacy order files into Dataverse with Power Automate for desktop, feeding the same approval process |
| [Module 3: Workflows](03-workflow.md) | Build a workflow that an agent calls mid-conversation to validate returns — combining data, AI, and human approval |
| [Module 4: CUA](04-cua.md) | Build an agent with a computer use tool that operates a carrier portal no connector or API can reach |

## Prerequisites

Each lab lists its own self-contained prerequisites, so you can cherry-pick a single lab and find everything it needs there. Across the series, you need:

1. A **Power Platform developer environment** where you have maker permissions. See [Create a developer environment](https://learn.microsoft.com/power-platform/developer/create-developer-environment). For what the capabilities in these labs require, refer to the [Power Platform licensing documentation](https://learn.microsoft.com/power-platform/admin/pricing-billing-skus).
2. The **Northwind Traders** solution imported into that environment **and seeded with sample data** — the shared backbone of every lab. Follow the import and **Northwind Sample Data** steps in [solutions/README.md](../../solutions/README.md).
3. An **email-capable account** to receive approval requests (Modules 1–3).
4. For Module 2, a **Windows machine** with **Power Automate for desktop** installed. Confirm the desktop-flow and Dataverse capabilities you need are available for your account — see the [Power Automate licensing documentation](https://learn.microsoft.com/power-platform/admin/pricing-billing-skus).
5. For Modules 3 and 4, a **Microsoft Copilot Studio** environment with the capabilities these labs use, and for Module 4, **computer use** enabled in your environment. Refer to the [Microsoft Copilot Studio licensing documentation](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions) for what's required.
6. A modern browser such as **Microsoft Edge** or **Google Chrome**.

🔧 **Setup check:** Use the same lab account throughout the series, and confirm the environment picker every time you open a maker portal — a wrong environment is the most common reason something "doesn't work." The labs repeat this check at every portal entry.

## Business use case

Northwind Traders sells food products, and its order process is stitched together by hand. Approvals travel as manual emails and orders fall through the cracks while waiting. A regional partner still sends orders as files that someone retypes. Customers asking "can I return this?" wait while an agent checks statuses and chases sign-offs. And every shipment ends at a carrier portal Northwind doesn't control — no API, no connector, and a form that rearranges its fields on every visit.

The labs in this module automate that process end to end, and in doing so introduce the Power Platform automation toolbox one tool at a time:

- **Approving** every order consistently with a cloud flow — two tiers of approval, clean rejection handling, and an invoice created automatically in Dataverse.
- **Importing** orders from legacy files with robotic process automation (RPA), so they enter the same governed approval process as orders typed into the app.
- **Grounding** an agent's answers with a workflow it calls as a tool — deterministic branches deciding, generative AI phrasing, and a human signing off where the value is high.
- **Reaching** the one system nothing else can touch with computer use — an agent that operates a website through its screen, the way a person would.

### Choosing the right tool

The series teaches a decision rule you'll reuse long after the labs: if a connector or API exists, use it (Module 1). If the UI is predictable enough to script step by step, use RPA (Module 2). When logic must stay deterministic and reviewable but an agent needs to call it, use a workflow (Module 3). And when all you can do is *describe* a task on a screen you don't control, that's computer use (Module 4) — the last resort.

### What you learn

By the end of this module, you can:

- Build automated cloud flows triggered by Dataverse events, with variables, expressions, multi-tier approvals, and solutions.
- Build desktop flows that bridge local files into Dataverse with Power Automate for desktop.
- Build workflows in Copilot Studio that agents call as tools, combining Dataverse data, deterministic branches, AI classification, generated messages, and human review.
- Build computer-using agents that operate websites by reading the screen — with restricted access, run-time inputs, and replayable session logs.
- Choose between connectors, RPA, workflows, and computer use for any automation problem.

> 🥳 Ready to get started? Begin with [Module 1: Cloud Flow](01-cloud-flow.md) and go through the labs table above in order — the modules tell one story, though each also stands alone if you want to cherry-pick.
