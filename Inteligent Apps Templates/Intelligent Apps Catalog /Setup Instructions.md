
**Setup Instructions**
======================

Follow the steps below to install the Intelligent Apps Catalog, configure your Dataverse tables, import the sample data files, and launch the runtime experience.

**1\. Download and Import the Latest Solution**
------------------------------------

Download the most recent version of the solution package:

**➡️ [IntelligentAppsInnovationCompanion\_1\_1\_0\_3](./Intelligent%20Apps%20Catalog/Catalog%20Solution)**

Import this solution into your Power Platform environment (Ensure environment has Dataverse and you have access to Import Solutions)

**2\. Configure Dataverse Tables**
----------------------------------

Once the solution is imported, you will configure the Dataverse tables required by the catalog.

1.  Navigate to **Catalog Management** app. Publish and open the app. 
    <img width="1766" height="410" alt="App Publish" src="https://github.com/user-attachments/assets/ace205b4-daca-44c9-b08b-61a76cde1372" />

2.  This app provides access to all Dataverse tables used by the Prompt Catalog, App Catalog, Use Cases Catalog, and UX Catalog.
    
3.  Each table contains sample schema and views to help you validate the structure before importing data.
    

**3\. Import Sample Data (CSV Files)**
--------------------------------------

Using the Catalog Management app, import the provided CSV files into their corresponding Dataverse tables.

### **Files to Import**

**Import the data in this order only.** Review the details of each of the csv files [here](./Sample%20Data/Sample%20Data%20Files%20Overview.md)

*   sample\_data\_app\_catalog.csv → **App Catalog** table
    
*   sample\_data\_use\_case\_catalog.csv → **Use Case Catalog** table
    
*   sample\_data\_ux\_catalog.csv → **UX Catalog** table (do not map Use Case Lookup column)
    
*   sample\_data\_prompt\_catalog.csv → **Prompt Catalog** table (wait till UX Catalog sample data is availble before importing this)
  > Note: Some prompts may contain actual table names which were used to build the page. As you copy the prompts to clipboard, improve the prompt to use your table names.
    

### **How to Import**

1.  In the Catalog Management app, navigate to the table you want to populate.
    
2.  Use the **Import Data** option (Import from Excel → Import from CSV ).
    <img width="1898" height="423" alt="Import files " src="https://github.com/user-attachments/assets/c0f2013f-e66f-4f99-b17c-bf4c624fa6e2" />

3.  Map the CSV columns to Dataverse fields as shown in the sample structure.
    
4.  Complete the import and verify records appear correctly.
  


Repeat this process for all four CSV files.

**4\. Import and Configure Images**
-----------------------------------

Each part of the catalog uses images differently. Follow the guidelines below to ensure that visuals display correctly within the Catalog Hub.

### **Gen Pages Sample Images (for UX Catalog)**

Use the provided **Gen Pages Sample Images** folder to populate the **UX Catalog**.These images show sample generative UX pages and can be uploaded directly as-is.

**Steps:**

1.  Open the **UX Catalog** table in Catalog Management.
    
2.  Upload the sample Gen Page image for each UX entry.
    
3.  (Optional) Replace these with your own generated UX page screenshots later.
    

### **Use Case Images (Use Your Own)**

The sample images included for Use Cases are placeholders.When configuring your organization’s **Use Case Catalog**, upload **your own solution images**, such as:

*   screenshots
    
*   workflow diagrams
    
*   solution visuals
    
*   product icons
    

This ensures the repository reflects your actual solutions.

**Steps:**

1.  Open the **Use Case Catalog** table.
    
2.  For each use case, upload your custom image in the image column.
    

### **App Catalog Images (Use Your Own)**

The sample app icons are only examples.For your real App Catalog, upload your **actual app icons or logos** so the App Hub reflects the apps your team uses.

**Steps:**

1.  Open the **App Catalog** table.
    
2.  Upload the correct logo or icon for each app entry.

**5\. Open the Runtime Experience**
-----------------------------------

After the tables are configured and data is imported, open the **Catalog Hub** app in the edit mode, publish and play the app to experience the runtime view of your Intelligent Apps Catalog.

>Note: You may experience error when playing the app without editing and publishing the Catalog hub app. 

The Catalog Hub provides:

*   Embedded App Center experience
    
*   UX gallery with generative page previews
    
*   Use Case repository
    
*   Guided prompt workflows
    

**6\. Run as a Webpage (Optional)**
-----------------------------------

If you want to run the Catalog Hub in a clean, embedded webpage view:

Append the following parameter to the app’s web URL:

`   &navbar=off   `

This removes the Power Apps navigation bar and provides a focused, full-screen runtime experience.
