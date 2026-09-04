---
title: "Bring AI Inside Your App: Natural Language Queries, Auto Charts & Smart Form Fill"
level: 100
persona: "information workers, Power Apps makers"
estimated_duration: "30 mins"
author: "Power CAT"
last_updated: "2026-03-04"
version: "v5"
tags: [modernize-existing-applications]
description: "Add focused agents inside Power Apps to support users with contextual data, guidance, and task completion."
---

**Power CAT | The Intelligent Enterprise - Power Platform & AI for Frontier Firms**


# In-app agents


## Lab overview

This lab shows how to use in-app agents in a model-driven app to explore data, generate visuals, assist with form completion, and surface record summaries directly in the user workflow.

## App scenario

Northwind Traders wants end users to work faster inside the Admin Management model-driven app without relying on separate analytics or manual data-entry workflows. In-app agents help users query orders, visualize trends, complete forms from unstructured content, and review AI-generated summaries directly in the app experience.

## Prerequisites

Review the consolidated workshop prerequisites before you begin:

- [Workshop prerequisites](/labs/prereqs.md)

For this hands-on lab, use a dedicated Power Apps developer environment. Import the **Northwind Traders** unmanaged solution from the `solutions` folder and seed the sample data by following the instructions in the [solutions README](../../solutions/README.md).

> [!NOTE]
> Use the shared solution setup guidance in the [solutions README](../../solutions/README.md) rather than duplicating import instructions in each lab.

Use a modern browser such as **Microsoft Edge** or **Google Chrome** for best compatibility.

1. Launch your browser.
2. Open a new window in **InPrivate** or **Incognito** mode.
3. Go to <https://make.powerapps.com> and select your developer environment.

> [!NOTE]
> This lab uses generative AI features. Generated content may differ between users and between the documentation and the live experience. If results vary, use your judgment to complete the task based on the intent and UI you see.

## Learning outcomes

By the end of this lab, you will be able to:

- Run natural language queries with the data exploration agent.
- Generate charts with the data visualization agent.
- Use form fill assistance to map unstructured input into record fields.
- Configure row summaries so users can review record context more quickly.

## Documentation & learning resources

- [Add agents to your model-driven app](https://learn.microsoft.com/power-apps/maker/model-driven-apps/add-agents-to-app)
- [Configure a row summary for a model-driven app](https://learn.microsoft.com/power-apps/maker/data-platform/configure-form-row-summary)
- [Use AI form fill assistance feature in model-driven apps](https://learn.microsoft.com/power-apps/user/form-filling-assistance)
- [Import, update, and export solutions](https://learn.microsoft.com/power-apps/maker/data-platform/import-update-export-solutions)

## Core concepts

The in-app agent experiences in this lab include:

| Concept | Why it matters |
| --- | --- |
| Data exploration agent | Lets users query records with natural language and apply filters without building custom views. |
| Data visualization agent | Creates charts from the current data context so users can inspect trends quickly. |
| Data entry agent | Suggests field values from pasted or uploaded content to reduce manual entry. |
| Row summary agent | Generates concise record summaries that surface key context directly in the app. |

## Lab steps

## Step 1: Use the data exploration agent

Use the data exploration agent to interact with order data using natural language queries that convert to filters.

1. Open the **Northwind Traders** solution, go to **Objects** > **Apps**, open **Admin Management App**, and click **Play**.

![Open the Admin Management app from the Northwind Traders solution](images/01-image-1.png)  
Figure: Open the Admin Management app from the solution.

2. Go to **Orders** and enter the following prompt:

```text
List orders where payment was made via credit card in Chicago
```

![Enter a natural language filter prompt in Orders](images/02-image-2.png)  
Figure: Enter a natural language query in the Orders view.

3. Review the filtered results returned by the agent.

![Review filtered order results after the agent applies the query](images/03-image-3.png)  
Figure: Filtered order results returned by the data exploration agent.

4. Try the following prompt:

```text
Orders paid by check in last 10 months
```

![View filtered results for orders paid by check in the last 10 months](images/04-image-4.png)  
Figure: Filtered results for orders paid by check in the last 10 months.

5. Try one more prompt:

```text
Orders paid by credit card - Sort them by payment date, latest on top
```

![Sort credit card orders by payment date using a natural language prompt](images/05-image-5.png)  
Figure: Credit card orders sorted by payment date.

## Step 2: Use the data visualization agent

Use the data visualization agent to automatically generate charts based on the current data context.

1. Go back to **Orders** and click **Visualize**.

![Open the visualize action from the Orders view](images/06-image-6.png)  
Figure: Open the visualization experience from Orders.

2. Review the generated visual. In this example, a column chart shows order counts by city.

![Review the generated orders by city chart](images/07-image-7.png)  
Figure: Example visualization generated from the current Orders context.

3. Click chart options to change the chart type, aggregation, axes, and other properties.

![Open chart options for the generated visual](images/08-image-8.png)  
Figure: Chart options for the generated visual.

4. Inspect available properties such as aggregation, X and Y axes, and formatting.

![Inspect the generated chart properties panel](images/09-image-9.png)  
Figure: Properties available for the generated chart.

5. Enter the following prompt to create a visualization:

```text
visualize number of orders and payment type as a pie chart
```

![Generate a pie chart for orders by payment type](images/10-image-10.png)  
Figure: Pie chart visualization created from a prompt.

## Step 3: Use the data entry agent

Use the data entry agent to assist with form completion by suggesting values and mapping unstructured input.

1. In **Orders**, click **New** to create a new order record.

![Open a new order form in the Admin Management app](images/11-image-11.png)  
Figure: New order form.

2. Click **Form assist** if the form fill pane is hidden.

![Show the form assist pane on the new order form](images/12-image-12.png)  
Figure: Form assist pane on the order form.

3. Upload a file or paste clipboard data. The agent detects and maps information to form fields.

![Open Smart Paste or upload options for form fill assistance](images/13-image-13.png)  
Figure: Smart Paste and upload options for form fill assistance.

4. Copy and paste the following sample order text into Smart Paste:

```text
I want to place a new order for customer AA. The order needs to be placed today and the paid date to 2 weeks from now. This order is taxable. Please ship this order to 1 Microsoft Way, Redmond, WA, 98052. The order will be paid via check. Also add a note that this order is for a big private company.
```

You can also upload the image below to test mapping.

![Reference image that can be uploaded for form fill testing](images/14-image-14.png)  
Figure: Reference image for testing form fill mapping.

5. Review the suggestions and accept the values you want to apply.

![Review suggested field values returned by the data entry agent](images/15-image-15.png)  
Figure: Suggested field values returned by form fill assistance.

> [!NOTE]
> Limitations:
> - Suggestions appear only for fields on main and quick-create forms.
> - Supported types: text, numeric, choice, date.
> - Fields with column security are not supported.

6. Accept or cancel suggestions individually, or use the bulk accept experience.

![Accept or reject suggested values one at a time](images/16-image-16.png)  
Figure: Accept or reject suggestions individually.

![Accept multiple suggested values for the new order](images/17-image-17.png)  
Figure: Accept multiple suggested values on the form.

7. Review the populated form, update any remaining values, and click **Save and close**.

![Save the populated order record after applying suggestions](images/18-image-18.png)  
Figure: Save the populated order record.

8. Confirm the order appears in the view.

![Confirm the saved order appears in the Orders view](images/19-image-19.png)  
Figure: Saved order displayed in the Orders view.

## Step 4: Configure the row summary agent

Use the row summary agent to generate concise record summaries for quick insight.

1. In the **Northwind Traders** solution, select **Objects** > **Tables** > **Order** > **Row summary**.

![Open row summary settings for the Order table](images/20-image-20.png)  
Figure: Row summary configuration for the Order table.

2. Add prompt instructions for the summary. To include dynamic data, select **Add data**, choose the **Order** table, and add the columns you want included.

![Add table data references to the row summary prompt](images/21-image-21.png)  
Figure: Add data references to the row summary prompt.

![Select columns to include in the row summary prompt](images/22-image-22.png)  
Figure: Select columns to include in the prompt.

![Review prompt data selections for the summary](images/23-image-23.png)  
Figure: Review the selected data references for the prompt.

3. Frame the prompt instructions for the summary.

![Write row summary instructions in the prompt editor](images/24-image-24.png)  
Figure: Prompt instructions for the row summary agent.

4. Click **Test** to preview the generated response.

![Test the row summary prompt against a sample record](images/25-image-25.png)  
Figure: Test the row summary prompt.

5. Add a related column to the instructions. Enter `/` or use **Add data**, then select **Orders** > **Customer (Customer)** > **First name**.

![Add a related customer field to the summary prompt](images/26-image-26.png)  
Figure: Add a related customer field to the prompt.

6. Test the model response again.

![Review the updated row summary test response](images/27-image-27.png)  
Figure: Updated row summary response after adding related data.

7. Click **Apply to main forms** and **Close**.

![Apply the configured row summary to main forms](images/28-image-28.png)  
Figure: Apply the row summary to main forms.

8. Play the **Admin Management** model-driven app.

![Launch the Admin Management app to verify row summaries](images/29-image-29.png)  
Figure: Launch the Admin Management app.

9. In **Orders**, hover over the primary column and click the summary indicator.

![Open the summary indicator from an order record in the grid](images/30-image-30.png)  
Figure: Summary indicator in the Orders view.

10. Review the summary card for the selected record.

![Review the generated summary card for the selected record](images/31-image-31.png)  
Figure: Generated row summary card.

11. Open an order record and review the summary at the top of the form.

![Open an order form to review the row summary on the form](images/32-image-32.png)  
Figure: Open an order form to review the summary.

![Review the generated row summary at the top of the form](images/33-image-33.png)  
Figure: Row summary displayed on the order form.

## Summary & best practices

- Use natural language queries and generated visuals to help users explore data without leaving the model-driven app.
- Review AI-generated suggestions and summaries before saving changes to production data.
- Keep shared environment and solution setup instructions in the central workshop prerequisite and solutions documentation.

## Lab completion

> [!TIP]
> You completed the in-app agents lab.
