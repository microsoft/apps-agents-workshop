---
title: "Automate Work in Power Apps with Supervised Agents"
level: 100
persona: "Information Workers"
estimated_duration: "1 hour"
audience_assumptions: "M365 and Power Platform Administrators"
author: "Power CAT"
last_updated: "2026-08-14"
version: "v1.0"
tags: [digitize-internal-operations, modernize-existing-applications]

---

**Power CAT | The Intelligent Enterprise - Power Platform & AI for Frontier Firms**

# Automate Work in Power Apps with Supervised Agents

*Create autonomous agents connected to Power Apps MCP server*  
*Intelligent Apps and Agents*

## Lab overview

This lab shows how to use the Power Apps MCP server and Agent Feed to build autonomous agents that can act on Power Apps and Dataverse data while keeping approval and supervision inside a model-driven app.

## App scenario

Northwind Traders wants to automate product and supplier workflows that currently depend on manual email handling and follow-up actions, while still allowing users to review and complete agent-driven tasks inside the app.

## Learning outcomes

By the end of this lab, you will be able to:

- Configure Copilot Studio agents that use Power Apps MCP server tools.
- Add email and Dataverse triggers that automate agent execution.
- Publish agents into Agent Feed for review inside a model-driven app.
- Validate end-to-end agent behavior across multiple Northwind scenarios.



## Definitions and key capabilities

**Copilot autonomous agents** are AI-powered systems built within Microsoft Copilot Studio that independently reason, plan, and act to complete tasks on behalf of individuals, teams, or entire organizations. These agents go beyond traditional automation by dynamically responding to business signals-such as data changes, system alerts, or scheduled events-without requiring human intervention.

An **MCP (Model Context Protocol) server** is a standardized service that lets AI agents safely discover and use external tools, data, and workflows-making AI systems extensible, composable, and enterprise‑ready without custom integrations.

The **Power Apps MCP server** is a Model Context Protocol service that lets Copilot Studio agents securely read from and act on Power Apps and Dataverse data-automating tasks like data entry and updates with built-in human review and control.

**Agent Feed** is a built-in supervision and task inbox in Power Apps (and model driven apps) that

- shows **what autonomous Copilot Studio agents are doing**,
- surfaces **agent generated tasks for human review or approval**,
- and lets users **monitor, intervene, and complete human-in-the-loop steps without leaving the app**.

## Documentation and learning resources

[Work with Power Apps MCP Server - Power Apps | Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/power-apps-mcp-server)

## Prerequisites

[Workshop prerequisites](/labs/prereqs.md)


## Step 1: Before you begin, review the consolidated [Workshop prerequisites](/labs/prereqs.md) to ensure you have maker access to Power Platform and you have access to **Power Apps**

## Step 2: You can create apps in a **Power Platform environment** (Dev/Sandbox preferred)

## Step 3: Install the Northwind Traders solution - The Northwind Traders solution must be installed in your environment. Follow the shared import and sample-data setup instructions in the [solutions README](../../solutions/README.md) before you start this lab.

## Step 4: You are working in an environment where the **early** release option is checked

## Step 5: Ensure your user is part of the Copilot Studio Authors within the Power Platform Admin portal in the tenant settings. Ask your admin for help

![Copilot Studio Authors in PPAC Tenant Settings.](images/01-copilot-studio-authors-in-ppac-tenant-settings.png)  
Figure: Copilot Studio Authors in PPAC Tenant Settings.

## Step 6: The user executing the lab needs to have an Outlook license as the Outlook connector is used and the executing user needs to send emails as part of the lab

## Lab steps

### Agent 1: Northwind product management Agent

**Business use case**

**Scenario:** The Northwind Traders organization has created a Power Apps solution to manage purchase orders, products, and related business operations. The production team uses email to submit new product requests to the Power Apps solution, which currently requires manual processing and tracking. This creates bottlenecks, delays in response times, and potential errors in new product creation.

**Simple business solution:** Create an autonomous agent that can automatically handle product management without human intervention, including automatically processing new product creation requests from emails.

## Module 1: Create new Copilot Studio agent

## Step 1: Go to <https://make.preview.powerapps.com/> and click on **Solutions** in left Hand Navigation

## Step 2: Select Current Preferred Solution tab and select Manage

![Northwind Traders.](images/02-northwind-traders.png)  
Figure: Northwind Traders.

## Step 3: Select Northwind Traders solution and click on Apply. This will make sure that all new artifacts will automatically, get added to this solution

![The image displays a user interface with options for managing updates and solutions for a software application, specifically focusing on Common Data Services Default Solution (cr85a) for Northwind Traders (nwind).](images/03-the-image-displays-a-user-interface-with-options-for-managing-updates-and-soluti.png)  
Figure: The image displays a user interface with options for managing updates and solutions for a software application, specifically focusing on Common Data Services Default Solution (cr85a) for Northwind Traders (nwind).

## Step 4: Select "Northwind Traders" Solution

![Image 4.](images/04-image-4.png)  
Figure: Image 4.

## Step 5: Select Objects-->Agents

## Step 6: Click on + New dropdown arrow and select Agent--> Agent

![Image 5.](images/05-image-5.png)  
Figure: Image 5.

## Step 7: Verify -user will be redirected to <https://copilotstudio.preview.microsoft.com/>

## Step 8: If requested to get a trial license, follow the steps

## Step 9: Select the Create an agent section

![The image depicts a user interface for a platform where one can create agents and workflows for automating tasks, emphasizing speed, flexibility, and security.](images/06-the-image-depicts-a-user-interface-for-a-platform-where-one-can-create-agents-an.png)  
Figure: The image depicts a user interface for a platform where one can create agents and workflows for automating tasks, emphasizing speed, flexibility, and security.

## Step 10: Name the agent as - Northwind Product Management Agent. Click on Create

![The image depicts a form with fields for naming an agent, specifically the Northwind Product Management Agent, with options to adjust agent settings and proceed to create or cancel the configuration.](images/07-the-image-depicts-a-form-with-fields-for-naming-an-agent-specifically-the-northw.png)  
Figure: The image depicts a form with fields for naming an agent, specifically the Northwind Product Management Agent, with options to adjust agent settings and proceed to create or cancel the configuration.

## Step 11: This will create a basic - Northwind Product Management Agent. Now, Click on Edit icon in the Agent Details section -

![Agents.](images/08-agents.png)  
Figure: Agents.

## Step 12: Next, Add Description- "Use the Invoke Data Entry tool to create a product record with the extracted information" and then click on Save

![New Agent Details.](images/09-new-agent-details.png)  
Figure: New Agent Details.

## Step 13: Next, Add Power Apps MCP Server to Agent Tools, Under Overview Tab--> Click Add tool

![Adding a tool to agent.](images/10-adding-a-tool-to-agent.png)  
Figure: Adding a tool to agent.

## Step 14: In search bar type- Power Apps MCP Server

![Adding PowerApps MCP Server.](images/11-adding-powerapps-mcp-server.png)  
Figure: Adding PowerApps MCP Server.

## Step 15: Select **Power Apps MCP Server**. If the connection is not present, create a new connection as shown below

![The image shows a Power Apps MCP Server interface with an option to create a new connection.](images/12-the-image-shows-a-power-apps-mcp-server-interface-with-an-option-to-create-a-new.png)  
Figure: The image shows a Power Apps MCP Server interface with an option to create a new connection.

## Step 16: For connection creation, select Connect -> Azure AD and then Create

![The image shows a Microsoft Power Apps interface with options for MCP server interaction and Azure AD, including buttons for connecting and creating a new app.](images/13-the-image-shows-a-microsoft-power-apps-interface-with-options-for-mcp-server-int.png)  
Figure: The image shows a Microsoft Power Apps interface with options for MCP server interaction and Azure AD, including buttons for connecting and creating a new app.

## Step 17: If the connection already existing, Select the Connection and Click on **Add and configure**

![Add and configure PowerApps MCP server.](images/14-add-and-configure-powerapps-mcp-server.png)  
Figure: Add and configure PowerApps MCP server.

## Step 18: Once configured, Power Apps MCP server will be added to Agent --> Tools. Click **Additional Details** and select **Maker-provided credentials** under **Credentials to use**.

![changing Additional details.](images/15-changing-additional-details.png)  
Figure: changing Additional details.

## Step 19: Under tools section, notice all 3 Tools are Enabled by default. Turn off toggle button in header and Enable only **invoke_data_entry ** tool and disable other two tools and Click on ** Save button.**

![Enable only invoke_data_entry tool.](images/16-enable-only-invoke-data-entry-tool.png)  
Figure: Enable only invoke_data_entry tool.

Enable only invoke_data_entry tool

## Step 20: Go to Tools to verify PowerApps MCP Server is added and is **Enabled**

![PowerApps MCP Server is Enabled.](images/17-powerapps-mcp-server-is-enabled.png)  
Figure: PowerApps MCP Server is Enabled.

## Step 21: Next, Create Trigger- Send an email (v3). Go back to Overview Tab--> **Click Add trigger.** This will make our agent and autonomous agent

![Add trigger.](images/18-add-trigger.png)  
Figure: Add trigger.

## Step 22: Select **When a new email arrives (V3)** and click ** Next** and wait for Authentication, it should auto authenticate Copilot Studio and Office 365 Outlook

![Add trigger.](images/19-add-trigger.png)  
Figure: Add trigger.

![Image 20.](images/20-image-20.png)  
Figure: Image 20.

> [!TIP]
> You can rename your trigger to be relevant to the business requirement

## Step 23: Configure Trigger as mentioned below -

## Step 1: **Folder= Inbox**

## Step 2: **Subject=****Northwind Order**

## Step 3: **Additional Instructions to Agent when Invoked by this trigger**= Use Content from @{triggerBody()} - This is by default added to your trigger configuration

> Now, Select **Create trigger** button to create the trigger for autonomous agent.

![configure trigger.](images/21-configure-trigger.png)  
Figure: configure trigger.

## Step 24: Select the agent model

Under **Select your agent's model**, change the model to **GPT-5 Chat**.

![change GPT model.](images/22-change-gpt-model.png)  
Figure: change GPT model.

## Step 25: Add instructions to the agent

Below Select the Agent Model, navigate to **Add instructions**. In the instructions section, click **Edit**, include the instructions below, and click **Save**.

![Add Instructions.](images/23-add-instructions.png)  
Figure: Add Instructions.

Add Instructions

> 1\. When an email arrives: Determine if it contains product-related information (either in the email body or attachments).
>
> 2\. Use the invoke_data_entry tool to create a product (nwind_products) record with the extracted information in the following columns:
>
> nwind_description nwind_discontinued entityimageid importsequencenumber nwind_listprice nwind_minimumreorderquantity entityimage nwind_productsid nwind_productcode nwind_productname nwind_quantityperunit nwind_reorderlevel nwind_sampledataoriginalid nwind_standardcost statuscode statecode nwind_targetlevel timezoneruleversionnumber utcconversiontimezonecode versionnumber owningbusinessunit
>
> 3\. If information is missing, still create the record with available data - leave unknown fields empty

![The image displays a text snippet from a data entry form for an email system, with fields for product information and instructions on how to input data into a product record.](images/24-the-image-displays-a-text-snippet-from-a-data-entry-form-for-an-email-system-wit.png)  
Figure: The image displays a text snippet from a data entry form for an email system, with fields for product information and instructions on how to input data into a product record.

## Step 26: Finally, publish the agent as illustrated below

![Publish Agent.](images/25-publish-agent.png)  
Figure: Publish Agent.

Publish Agent

## Module 2: Set up Agent Feed

## Step 27: Now we will Add our agent created in Step 1 to the Agent Feed. Go to [https://make.preview.powerapps.com/](https://make.preview.powerapps.com/) . Navigate to Northwind Traders solution and then Edit the Admin Management App

![Edit Admin Mgt App.](images/26-edit-admin-mgt-app.png)  
Figure: Edit Admin Mgt App.

## Step 28: After the app opens in the edit mode, Select Agent icon (4th icon) tooltip shows **"Agents"** from Left hand navigation menu

![Select agent.](images/27-select-agent.png)  
Figure: Select agent.

## Step 29: Add the product management agent to Agent Feed

Within the In your Environment section, locate Northwind Product Management Agent. Select **the agent**, click `...`, and select **Add to feed**.

![The image depicts the Contoso Electronics dashboard in Power Apps, showcasing various management features such as agents, orders, inventory, suppliers, and customers.](images/28-the-image-depicts-the-contoso-electronics-dashboard-in-power-apps-showcasing-var.png)  
Figure: The image depicts the Contoso Electronics dashboard in Power Apps, showcasing various management features such as agents, orders, inventory, suppliers, and customers.

>

## Step 30: Verify the agent appears in Agent Feed

Once added to your feed, you will see the agent under **In your feed**.

![The image displays a user interface with a message indicating that an agent has been successfully upgraded to use the Enhanced Agent Feed within the MCP Server.](images/29-the-image-displays-a-user-interface-with-a-message-indicating-that-an-agent-has.png)  
Figure: The image displays a user interface with a message indicating that an agent has been successfully upgraded to use the Enhanced Agent Feed within the MCP Server.

## Step 31: **Publish and Play** Admin Management App

![- Publish App and Play.](images/30-publish-app-and-play.png)  
Figure: - Publish App and Play.

## Step 32: Now, lets Verify Agent Feed Set up. Play the Admin Management App and Click on **Agent Feed**

![Order Detail Status.](images/31-order-detail-status.png)  
Figure: Order Detail Status.

>

![Agent feed option.](images/32-agent-feed-option.png)  
Figure: Agent feed option.

## Module 3: Test the agent

## Step 33: Send New **Email** to the User You Logged in to [Office 365 outlook](https://outlook.office.com) - with the details below and send this email to your logged in demo account

> **Subject : Northwind Order - New Products**
>
Enter the following content:

```text

Please find below the details of our latest new products for Northwind Traders.

Supplier Details

Supplier: Exotic Liquids

Contact: Charlotte Cooper

Address: 49 Gilbert St, London, UK
```

| **Product **|** Category **|** Unit Price** |
|---------------|--------------|----------------|
| Chai | Beverages | \$18.00 |
| Chang | Beverages | \$19.00 |
| Aniseed Syrup | Condiments | \$10.00 |

> Please review the products and confirm you have added them. Let us know if you need any additional information from our side.
>
> Thank you for your continued partnership.

## Step 34: Once the email is sent, lets verify the Agent Activity. Go to **Northwind Product Management Agent ** and click on ** Activity tab** to monitor invoke_data_entry

![Image 33.](images/33-image-33.png)  
Figure: Image 33.

>

## Step 35: Next, Monitor Agent feed in Power App. Play the Admin Management App and **Refresh ** Agent feed to reload Agent feed of **3 Products** submitted in email (Chai, Chang, Aniseed Syrup)

![Refresh agent.](images/34-refresh-agent.png)  
Figure: Refresh agent.

![verify Needs attention feed.](images/35-verify-needs-attention-feed.png)  
Figure: verify Needs attention feed.

## Step 36: Select **" Review new order Product for "** and click on **"Accept and complete".** Repeat the same for all the 3 actions.**\**

![Accept and complete Product data entry.](images/36-accept-and-complete-product-data-entry.png)  
Figure: Accept and complete Product data entry.

## Step 37: Click on **Completed** Tab in Agent Feed to confirm data has been added to Order Products table

![Data added to Order Products table.](images/37-data-added-to-order-products-table.png)  
Figure: Data added to Order Products table.

### Agent 2: Northwind issue management Agent

**Business use case\**

**Scenario:** The Northwind Traders organization has created a Power Apps solution to manage purchase orders, products, and related business operations. Suppliers are created in the system frequently. When an international supplier gets created, the Northwind Traders team needs to perform additional action outside the system. This has been a manual process to date. It has happened multiple times that the manual process was not completed, and Northwind Traders were out of compliance risking disciplinary actions.

**Simple business solution:** Create an autonomous agent that can automatically intercept the creation of international suppliers in the system and ensure the manual process gets executed.

**Copilot autonomous agents** are AI-powered systems built within Microsoft Copilot Studio that independently reason, plan, and act to complete tasks on behalf of individuals, teams, or entire organizations. These agents go beyond traditional automation by dynamically responding to business signals, such as data changes, system alerts, or scheduled events, without requiring human intervention. Combining autonomous agents with the **Power Apps MCP server** provides a Power Apps-optimized capability to intercept and supervise work from within **Agent Feed**.

## Step 1: Modify Northwind traders - supplier table

**Add Country_Region to Supplier Form and View**

## Step 38: In the maker portal (<https://make.preview.powerapps.com/>), change the environment and open the Northwind Traders solution

In the maker portal, change the environment to your early release developer environment. In our example, the environment is called **Intelligent Apps 2**. Your environment will have a different name.

![Environment picker in the maker portal](images/105-environment-picker.png)  
Figure: Environment picker (your environment name will be different).

Go to the Northwind Traders solution.

![Click on Northwind Traders to open the solution.](images/38-click-on-northwind-traders-to-open-the-solution.png)  
Figure: Click on Northwind Traders to open the solution.

## Step 39: Edit the **Supplier** table and add the **Country_Region** field to the main form and Active Suppliers view

Expand Tables and select **Supplier table**. Click **Forms** and then click **Information** on the *Main* form type.

![Form under Data experiences.](images/39-form-under-data-experiences.png)  
Figure: Form under Data experiences.

![The image displays a section of a software interface, specifically a Northwind Traders database, showcasing an unmanaged form with no active status, and a card without any information.](images/40-the-image-displays-a-section-of-a-software-interface-specifically-a-northwind-tr.png)  
Figure: The image displays a section of a software interface, specifically a Northwind Traders database, showcasing an unmanaged form with no active status, and a card without any information.

>

## Step 40: Edit the Main form in a new tab

![Edit.](images/41-edit.png)  
Figure: Edit.

## Step 41: Drag **Country_Region** onto the form

![Country_Region in Table Columns.](images/42-country-region-in-table-columns.png)  
Figure: Country_Region in Table Columns.

![After dragging Country_Region onto form.](images/43-after-dragging-country-region-onto-form.png)  
Figure: After dragging Country_Region onto form.

## Step 42: Click **Save and publish** the Main Information form

![Save and publish in top right.](images/44-save-and-publish-in-top-right.png)  
Figure: Save and publish in top right.

## Step 43: Go back to the **Supplier ** table, and click ** Views ** and edit the ** Active Suppliers**:

![Views under Data Experiences.](images/45-views-under-data-experiences.png)  
Figure: Views under Data Experiences.

![The image displays a Microsoft Power BI dashboard with a navigable view of suppliers, featuring options to activate or deactivate various supplier views, such as active, inactive, advanced, and associated supplier views.](images/46-the-image-displays-a-microsoft-power-bi-dashboard-with-a-navigable-view-of-suppl.png)  
Figure: The image displays a Microsoft Power BI dashboard with a navigable view of suppliers, featuring options to activate or deactivate various supplier views, such as active, inactive, advanced, and associated supplier views.

>

## Step 44: **Click View column ** and select ** Country_Region**:

![Add Country_Region to view.](images/47-add-country-region-to-view.png)  
Figure: Add Country_Region to view.

## Step 45: Click **Save and publish the view**

![Save and publish.](images/48-save-and-publish.png)  
Figure: Save and publish.

## Module 2: Create new Copilot Studio agent

## Step 46: Inside the Northwind Traders solution expand **Agents **. Select **+ New **->** Agent **->** Agent**:

![Create new agent.](images/49-create-new-agent.png)  
Figure: Create new agent.

## Step 47: Ensure the environment selected is the one initially selected. This will open a new window within Copilot Studio. Click on **Create an agent**:

![Create Agent.](images/50-create-agent.png)  
Figure: Create Agent.

## Step 48: Name the agent as Northwind Issue Management Agent and click on Create

![The image shows a user interface with a form to name a Northwind Issue Management Agent, with options to create or cancel.](images/51-the-image-shows-a-user-interface-with-a-form-to-name-a-northwind-issue-managemen.png)  
Figure: The image shows a user interface with a form to name a Northwind Issue Management Agent, with options to create or cancel.

> [!NOTE]
> Once the agent is created, it will get added in the preferred default solution. Go back to Northwind Trader solution, add existing agent and select Northwind Issue Management Agent.

![The image displays a Power Apps interface for adding a new agent to the Northwind Issue Management Agent, with options to select from existing solutions or unlisted agents.](images/52-the-image-displays-a-power-apps-interface-for-adding-a-new-agent-to-the-northwin.png)  
Figure: The image displays a Power Apps interface for adding a new agent to the Northwind Issue Management Agent, with options to select from existing solutions or unlisted agents.

## Step 49: Once the agent is ready, enter the below Description and then click **Save**

This agent helps Northwind Traders to request for human assistance if a qualified Issue occurred which the agent cannot resolve itself. One use case includes an international supplier is created. For international suppliers, actions outside of the system need to be completed first before the supplier can be created in the system.

![Northwind Issue Management Agent.](images/53-northwind-issue-management-agent.png)  
Figure: Northwind Issue Management Agent.

![Image 54.](images/54-image-54.png)  
Figure: Image 54.

>

## Step 50: Add the issue-management instructions

Scroll down and click **Instructions**, click **Edit**, copy and paste the text mentioned below, and click **Save**.

When this agent is triggered by the creation of a supplier with a country other than USA, it should request human assistance. For the request assistance, set the title by prefixing the value of supplier1, space and supplier2 with "Assistance needed: ". In the task description, include the first name, last name, company and job title, and the Country value as steps. Also include a navigation link to the Dataverse supplier record.

![Instructions.](images/55-instructions.png)  
Figure: Instructions.

## Step 51: Scroll down to **Tools** and click **+ Add Tool**

## Step 52: Type **Power Apps MCP** into the **Search** bar, click **Enter**, and select **Power Apps MCP Server**

![Adding Power Apps MCP Server.](images/56-adding-power-apps-mcp-server.png)  
Figure: Adding Power Apps MCP Server.

## Step 53: Select your existing connection or create a new connection. If you are creating a new connection, select Azure AD and then Click **Add and configure**

![Connection dialog.](images/57-connection-dialog.png)  
Figure: Connection dialog.

## Step 54: Expand **Additional Details** and change **Credentials to use** to **Maker-provided credentials**

![Configure Power Apps MCP server.](images/58-configure-power-apps-mcp-server.png)  
Figure: Configure Power Apps MCP server.

## Step 55: Scroll down to Tools and observe that all Power Apps MCP tools are enabled. Here we can turn off tools not to be used if desired

![Power Apps MCP Tools.](images/59-power-apps-mcp-tools.png)  
Figure: Power Apps MCP Tools.

## Step 56: Go to **Overview**, scroll to **Triggers**, and click **+ Add Trigger**

![Set up your agent.](images/60-set-up-your-agent.png)  
Figure: Set up your agent.

## Step 57: Select **When a row is added, modified or deleted**, and click **Next**

![Select Dataverse trigger.](images/61-select-dataverse-trigger.png)  
Figure: Select Dataverse trigger.

## Step 58: In the trigger configuration page, update any connections if required and click on Next

![The image depicts a user interface for adding a trigger in Microsoft Copilot Studio, which activates an agent when a row is added, modified, or deleted in Microsoft Dataverse.](images/62-the-image-depicts-a-user-interface-for-adding-a-trigger-in-microsoft-copilot-stu.png)  
Figure: The image depicts a user interface for adding a trigger in Microsoft Copilot Studio, which activates an agent when a row is added, modified, or deleted in Microsoft Dataverse.

## Step 59: Fill in **Change type**, **Table name**, and **Scope**

- Change type: **Add or Modified**
- Table name: **Suppliers**
- Scope: **Organization**
- Keep the default values for all other fields.

> Click **Create trigger**.

![Configure trigger.](images/63-configure-trigger.png)  
Figure: Configure trigger.

## Step 60: Now you are ready to **Publish ** your agent. Click ** Publish**

## Step 61: Select **Force newest version ** and click ** Publish **. You can** Close** the pop-up message

![Agent publishing.](images/64-agent-publishing.png)  
Figure: Agent publishing.

## Module 3: Add agent to Agent Feed

Now, you are ready to add your new **Northwind Issue Management Agent** to the Northwind Admin App.

## Step 62: Return to <https://make.preview.powerapps.com/> with the correct environment, select and go to **Solutions **>** Northwind Traders**

## Step 63: Expand **Apps ** and ** Edit ** the ** Amin Management App**:

![Edit the Admin Management App.](images/65-edit-the-admin-management-app.png)  
Figure: Edit the Admin Management App.

## Step 64: On the left-hand navigation, click **Agents**

![Agents menu.](images/66-agents-menu.png)  
Figure: Agents menu.

## Step 65: Add the **Northwind Issue Management Agent** to feed:

![Add agent to agent feed.](images/67-add-agent-to-agent-feed.png)  
Figure: Add agent to agent feed.

## Step 66: You should see **both agents ** added to your ** agent feed**:

![2 agents in agent feed.](images/68-2-agents-in-agent-feed.png)  
Figure: 2 agents in agent feed.

## Step 67: In the top right header, click **Save and Publish**:

![Save and Publish.](images/69-save-and-publish.png)  
Figure: Save and Publish.

## Module 4: Test the agent

Now, let's test the Northwind Issue Management Agent. We will create a new supplier record with country = Canada which will trigger the agent and create a task in the Agent Feed for the user to review and complete before the new supplier record will be created.

## Step 68: Click the **Ellipsis ** next to the Admin Management App and click ** Play**:

![Play Admin Management App.](images/70-play-admin-management-app.png)  
Figure: Play Admin Management App.

## Step 69: Once the **Admin Management App ** has opened, click ** Suppliers ** and **+ New**:

![+ New Button.](images/71-new-button.png)  
Figure: + New Button.

## Step 70: Enter the following values:

- First Name: **Joanne**
- Last Name: **Doe**
- Company: **Oltiva**
- Job Title: **Microchip Manufacturer**
- Country_Region: **Canada\**

![Create a new supplier.](images/72-create-a-new-supplier.png)  
Figure: Create a new supplier.

> [!TIP]
> You can use Form Fill assist agent to fill the form.

## Step 71: Click the **Ellipsis ** and click ** Save & Close**

![The image shows a user interface screen with fields for entering new supplier information, including first and last name, company name, job title, and country region.](images/73-the-image-shows-a-user-interface-screen-with-fields-for-entering-new-supplier-in.png)  
Figure: The image shows a user interface screen with fields for entering new supplier information, including first and last name, company name, job title, and country region.

## Step 72: Go back to <https://copilotstudio.preview.microsoft.com/> to open your Northwind Issue Management Agent

## Step 73: Scroll down to **Triggers ** and select the When a row is added, modified or deleted trigger. This will open the Power Automate flow which triggers the agent. On the ** Overview ** screen, check the ** Run History ** for a ** Succeeded** run:

> [!NOTE]
> the flow may get opened in edit mode. Click on the back button to show the flow run details.

![Code view.](images/74-code-view.png)  
Figure: Code view.

![Power Automate Flow Run History.](images/75-power-automate-flow-run-history.png)  
Figure: Power Automate Flow Run History.

## Step 74: Review the agent activity

Go back to the agent and navigate to **Activity**. Once refreshed, you will see a new activity where one step named **request_assitance** was executed with **In progress** status.

![Image 76.](images/76-image-76.png)  
Figure: Image 76.

> [!NOTE]
> *:* In case the request_assistance step does not trigger the first time, create another new **Supplier** record.

## Step 75: The activity remains **In Progress** until the related task in **Agent Feed** is completed

## Step 76: Refresh the app and review the assistance task

Go back to the **Admin Management App** and refresh the app. A new task will appear under Agent Feed with the title **Assistance needed: Joanne Doe**.

![Agent feed with required assistance task.](images/77-agent-feed-with-required-assistance-task.png)  
Figure: Agent feed with required assistance task.

## Step 77: Hover of the task to make the Complete icon visible:

![Complete icon on Agent feed task.](images/78-complete-icon-on-agent-feed-task.png)  
Figure: Complete icon on Agent feed task.

## Step 78: Click **Complete**

This moves the task to the **Completed** section under Agent Feed.

![Completed Agent feed task.](images/79-completed-agent-feed-task.png)  
Figure: Completed Agent feed task.

## Step 79: Navigate back to the Activity view under the Northwind Issues Agent. You will notice after refreshing the view the status will change to Completed

![Completed request_assitance agent activity.](images/80-completed-request-assitance-agent-activity.png)  
Figure: Completed request_assitance agent activity.

**\**
**Agent 3: Northwind Supplier Management Agent**
-------------------------------------------------

**Business use case\**

**Scenario:** The Northwind Traders organization has created a Power Apps solution to manage purchase orders, products, and related business operations. Supplier contacts are created manually today when a supplier contact sends an email which is leading to inefficiencies and inconsistencies frequently.

**Simple business solution:** Create an autonomous agent that can automatically create the supplier contact from an email. The autonomous agent will also create a log entry in the Agent feed to make it fast and easy for a human to review the automatically created suppliers' contacts.

**Copilot autonomous agents ** are AI-powered systems built within Microsoft Copilot Studio that independently reason, plan, and act to complete tasks on behalf of individuals, teams, or entire organizations. These agents go beyond traditional automation by dynamically responding to business signals-such as data changes, system alerts, or scheduled events-without requiring human intervention. Combining autonomous agents with the ** Power Apps MCP server ** provides the Power Apps optimized capability to intercept from within ** Agent Feed**.

## Module 1: Create new Copilot Studio agent

## Step 80: In the maker portal (<https://make.preview.powerapps.com/>), change the environment and open the Northwind Traders solution

In the maker portal, change the environment to your early release developer environment. In our example, the environment is called **Intelligent Apps 2**. Your environment will have a different name.

![Environment picker in the maker portal](images/105-environment-picker.png)  
Figure: Environment picker (your environment name will be different).

Go to the Northwind Traders solution.

![Click on Northwind Traders to open the solution.](images/38-click-on-northwind-traders-to-open-the-solution.png)  
Figure: Click on Northwind Traders to open the solution.

## Step 81: Expand **Agents **. Select **+ New **>** Agent **>** Agent**:

![Create new agent.](images/49-create-new-agent.png)  
Figure: Create new agent.

> [!TIP]
> Ensure the environment selected is the one initially selected. This will open a new window within Copilot Studio:

![Environment Selector.](images/81-environment-selector.png)  
Figure: Environment Selector.

## Step 82: Scroll down to **Create an agent**:

![Create Agent.](images/82-create-agent.png)  
Figure: Create Agent.

## Step 83: Name the agent **Northwind Supplier Management Agent** and click **Create**

![Image 83.](images/83-image-83.png)  
Figure: Image 83.

## Step 84: Once the agent is ready, In the Agent Details section, click on Edit and enter the below Description and Click **Save**

> This agent can automatically create a supplier contact from an email. The autonomous agent will also create a log entry in the Agent feed to make it fast and easy for a human to review the automatically created supplier contacts.
>
![The image shows a user interface detailing a Northwind Supplier Management Agent's functionality for automated creation and logging of supplier contacts.](images/84-the-image-shows-a-user-interface-detailing-a-northwind-supplier-management-agent.png)  
Figure: The image shows a user interface detailing a Northwind Supplier Management Agent's functionality for automated creation and logging of supplier contacts.

>

## Step 85: Add the supplier-management instructions

Scroll down and click **Instructions**, click **Edit**, copy and paste the following, and click **Save**.

When an email is received concerned with a supplier this agent must check if the supplier already exists based on the first and last name of the supplier (mwind_suppliers). If the supplier does not yet exist, the agent must create the supplier in the system. When a new supplier is added in the system, this agent must log the details for human review. The review item title should be based on the last name and first name of the supplier and must use the exact prefix "Review new Supplier Contact: ". In the review description, write a concise, natural language summary of the booking that includes main fields like First Name, Last Name, Company, and Country_Region, so a reviewer can quickly understand what was processed without opening the record. Ensure the description reads as a short paragraph and accurately reflects the current values from the booking record.

![Instructions.](images/85-instructions.png)  
Figure: Instructions.

## Step 86: Scroll down to **Tools** and click **+ Add Tool**

## Step 87: Type **Power Apps MCP** into the **Search** bar, click **Enter**, and select **Power Apps MCP Server**

![Adding Power Apps MCP Server.](images/56-adding-power-apps-mcp-server.png)  
Figure: Adding Power Apps MCP Server.

## Step 88: Select your existing connection or create a new connection. If you are creating a new connection, select Azure AD. Click **Add and Configure** button

![Connection dialog.](images/57-connection-dialog.png)  
Figure: Connection dialog.

## Step 89: Expand **Additional Details** and change **Credentials to use** to **Maker-provided credentials**

![Configure Power Apps MCP server.](images/58-configure-power-apps-mcp-server.png)  
Figure: Configure Power Apps MCP server.

## Step 90: In **Tools**, click **+ Add Tool** to add a second MCP server

## Step 91: Type **Dataverse MCP** into the **Search** bar, click **Enter**, and select **Dataverse MCP Server**

> [!NOTE]
> A deprecated version of the Dataverse MCP Server is also available. Be sure to select the current version, which typically appears as the first result in the search list.

![Adding Dataverse MCP Server.](images/86-adding-dataverse-mcp-server.png)  
Figure: Adding Dataverse MCP Server.

## Step 92: Select your existing connection or create a new connection

If you are creating a new connection, select **OAuth** and then click **Add and Configure**.

![Connection dialog.](images/87-connection-dialog.png)  
Figure: Connection dialog.

## Step 93: Expand **Additional Details** and change **Credentials to use** to **Maker-provided credentials**

Once done, click **Save**.

![Configure Dataverse MCP server.](images/88-configure-dataverse-mcp-server.png)  
Figure: Configure Dataverse MCP server.

![The image depicts the Microsoft Dataverse MCP Server configuration page in the Northwind Supplier Management Agent, where a user is presented with an option to input credentials.](images/89-the-image-depicts-the-microsoft-dataverse-mcp-server-configuration-page-in-the-n.png)  
Figure: The image depicts the Microsoft Dataverse MCP Server configuration page in the Northwind Supplier Management Agent, where a user is presented with an option to input credentials.

## Step 94: Go to **Overview**, scroll to **Triggers**, and click **+ Add Trigger**

![Add trigger.](images/90-add-trigger.png)  
Figure: Add trigger.

## Step 95: Select **When a new email arrives (V3)** and click **Next**

![Add Email trigger.](images/91-add-email-trigger.png)  
Figure: Add Email trigger.

## Step 96: Configure the trigger name

Click **Next** again on the **Add trigger** screen. Set the Trigger Name to **When an email is received from a supplier** and then click **Next**.

![The image shows an interface in Microsoft Copilot Studio with a trigger set up to respond to new emails from a supplier.](images/92-the-image-shows-an-interface-in-microsoft-copilot-studio-with-a-trigger-set-up-t.png)  
Figure: The image shows an interface in Microsoft Copilot Studio with a trigger set up to respond to new emails from a supplier.

## Step 97: Configure the trigger by selecting Folder = Inbox and click **Create trigger**

![The image illustrates an Office 365 Outlook interface with a section dedicated to setting up an email trigger, allowing users to specify conditions like new emails, attachments, and subject filters to automate responses.](images/93-the-image-illustrates-an-office-365-outlook-interface-with-a-section-dedicated-t.png)  
Figure: The image illustrates an Office 365 Outlook interface with a section dedicated to setting up an email trigger, allowing users to specify conditions like new emails, attachments, and subject filters to automate responses.

![Configure trigger with Inbox.](images/94-configure-trigger-with-inbox.png)  
Figure: Configure trigger with Inbox.

## Step 98: Publish the agent

You are now ready to **Publish** your agent. Click **Publish**.

## Step 99: Select **Force newest version** and click **Publish**

You can **Close** the pop-up message afterward.

![Agent publishing.](images/64-agent-publishing.png)  
Figure: Agent publishing.

## Module 2: Add agent to Agent Feed

Now, you are ready to add your new **Northwind Supplier Management Agent** to the Northwind Admin App.

## Step 100: Return to <https://make.preview.powerapps.com/> with the correct environment and go to **Solutions** > **Northwind Traders**

## Step 101: Expand **Apps** and **Edit** the **Admin Management App**

![Edit the Admin Management App.](images/65-edit-the-admin-management-app.png)  
Figure: Edit the Admin Management App.

## Step 102: On the left-hand navigation, click **Agents**

![Agents menu.](images/95-agents-menu.png)  
Figure: Agents menu.

## Step 103: Add the **Northwind Supplier Management Agent** to feed:

![Image 96.](images/96-image-96.png)  
Figure: Image 96.

>

## Step 104: Verify that **3 agents** are added to your **agent feed**

![2 agents in agent feed.](images/97-2-agents-in-agent-feed.png)  
Figure: 2 agents in agent feed.

## Step 105: In the top right header, click **Save and Publish**:

![Save and Publish.](images/69-save-and-publish.png)  
Figure: Save and Publish.

## Step 106: Once publishing is completed, click **Back**

## Module 3: Test the agent

Now, let's test the Northwind Supplier Management Agent. We will have a supplier email and the email will trigger to check if the supplier contact already exists. If not, the agent will create the supplier contact in Dataverse. Once created, the agent will log an activity for review by a human in the agent feed.

## Step 107: Click the **Ellipsis** next to the Admin Management App and click **Play the app**

![Play Admin Management App.](images/70-play-admin-management-app.png)  
Figure: Play Admin Management App.

## Step 108: Send an email to your users Inbox:

> **Subject:** Supplier Communication
>
> **Body:** Hello Contoso,
>
> I am your supplier. This is a reminder to pay your invoice.
>
> Best regards,
>
> Anna Doe

## Step 109: Go back to <https://copilotstudio.preview.microsoft.com/> to open your Northwind Supplier Management Agent

## Step 110: Scroll down to **Triggers** and click on the existing triggers. This will open the Power Automate flows which trigger the agent

> [!NOTE]
> The Power Automate flow may open in the edit mode. Click on the Back button to see the flow details.

![Add trigger.](images/98-add-trigger.png)  
Figure: Add trigger.

On the **Overview** screen for each flow, check the **Run History** for a **Succeeded** run:

![Power Automate Flow Run History.](images/99-power-automate-flow-run-history.png)  
Figure: Power Automate Flow Run History.

## Step 111: Review the supplier-management agent activity

Go back to the agent and navigate to **Activity**. Once refreshed, you will see a new activity where 6-7 steps were executed and the last step, **Power Apps MCP Server**, is in **Completed** status.

![Image 100.](images/100-image-100.png)  
Figure: Image 100.

> [!NOTE]
> *:* In case the agent does not trigger correctly the first time, send another email.

You can also click on the activity to see the entire workflow.

![The image displays a user interface of the Northwind Supplier Management Agent, showcasing various tools and functionalities for managing supplier information, including email notifications, data entry, and human assistance.](images/101-the-image-displays-a-user-interface-of-the-northwind-supplier-management-agent-s.png)  
Figure: The image displays a user interface of the Northwind Supplier Management Agent, showcasing various tools and functionalities for managing supplier information, including email notifications, data entry, and human assistance.

## Step 112: Refresh the app and review the logged supplier task

Go back to the **Admin Management App** and refresh the app. A new task will appear in Agent Feed with the title **Review new Supplier: Doe Anna**.

![Image 102.](images/102-image-102.png)  
Figure: Image 102.

> [!NOTE]
> *:* In case the task does not show in the Agent feed, clear your browser cache and refresh the application (Ctrl & F5).

## Step 113: If the activity in the agent feed is not already completed, mark the activity as Completed as highlighted in the below image

![The image shows an interface with a user interface for managing suppliers, including a section for an employee named Anna Doe, indicating an issue with a new supplier's country being non-USA and requiring review.](images/103-the-image-shows-an-interface-with-a-user-interface-for-managing-suppliers-includ.png)  
Figure: The image shows an interface with a user interface for managing suppliers, including a section for an employee named Anna Doe, indicating an issue with a new supplier's country being non-USA and requiring review.

## Step 114: Click on Suppliers in the sitemap. This will open the Active Suppliers view. You can see that a new supplier contact has been created:

![New supplier contact from email.](images/104-new-supplier-contact-from-email.png)  
Figure: New supplier contact from email.

## Summary & best practices

- Use maker-provided credentials and the minimum required MCP tools for each agent scenario.
- Keep agent instructions explicit so actions and review items remain deterministic.
- Validate the end-to-end flow in Agent Feed after every trigger or tool change before moving on.

## Lab completion

Congratulations! You have completed the Power Apps MCP server agents and Agent Feed lab.

## Additional resources

- [Design autonomous agent capabilities - Microsoft Learn](https://learn.microsoft.com/microsoft-copilot-studio/guidance/autonomous-agents)
- [Microsoft Copilot Studio - Microsoft Learn](https://learn.microsoft.com/microsoft-copilot-studio/)
- [Work with Power Apps MCP Server - Power Apps | Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/power-apps-mcp-server)
- [Agent Feed configuration steps - Maker](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/add-agents-to-app)
- [Enhanced Agent feed - End user](https://learn.microsoft.com/en-us/power-apps/user/supervise-agents-with-agent-feed)
- [Power Platform Integration - Microsoft Learn](https://learn.microsoft.com/power-platform/)
- [Dataverse Integration - Microsoft Learn](https://learn.microsoft.com/power-apps/maker/data-platform/)
