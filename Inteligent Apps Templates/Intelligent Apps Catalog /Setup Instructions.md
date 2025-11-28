
**Setup Instructions**
======================

Follow the steps below to install the Intelligent Apps Catalog, configure your Dataverse tables, import the sample data files, and launch the runtime experience.

**1\. Download the Latest Solution**
------------------------------------

Download the most recent version of the solution package:

**➡️ IntelligentAppsInnovationCompanion\_1\_0\_0\_1 (V2)**

Import this solution into your environment using the standard Power Platform solution import process.

**2\. Configure Dataverse Tables**
----------------------------------

Once the solution is imported, you will configure the Dataverse tables required by the catalog.

1.  Open the **Catalog Management** app included in the solution.
    
2.  This app provides access to all Dataverse tables used by the Prompt Catalog, App Catalog, Use Cases Catalog, and UX Catalog.
    
3.  Each table contains sample schema and views to help you validate the structure before importing data.
    

**3\. Import Sample Data (CSV Files)**
--------------------------------------

Using the Catalog Management app, import the provided CSV files into their corresponding Dataverse tables.

### **Files to Import**

Import the data in this order only.

*   sample\_data\_app\_catalog.csv → **App Catalog** table
    
*   sample\_data\_use\_case\_catalog.csv → **Use Case Catalog** table
    
*   sample\_data\_ux\_catalog.csv → **UX Catalog** table
    
*   sample\_data\_prompt\_catalog.csv → **Prompt Catalog** table
    

### **How to Import**

1.  In the Catalog Management app, navigate to the table you want to populate.
    
2.  Use the **Import Data** option (Import from Excel → Import from CSV ).
    
3.  Map the CSV columns to Dataverse fields as shown in the sample structure.
    
4.  Complete the import and verify records appear correctly.
    <img width="1909" height="438" alt="Import files " src="https://github.com/user-attachments/assets/cbd15d92-4957-4208-83e1-51798545dfcb" />


Repeat this process for all four CSV files.

**4\. Open the Runtime Experience**
-----------------------------------

After the tables are configured and data is imported, open the **Catalog Hub** app to experience the runtime view of your Intelligent Apps Catalog.

The Catalog Hub provides:

*   Embedded App Center experience
    
*   UX gallery with generative page previews
    
*   Use Case repository
    
*   Guided prompt workflows
    

**5\. Run as a Webpage (Optional)**
-----------------------------------

If you want to run the Catalog Hub in a clean, embedded webpage view:

Append the following parameter to the app’s web URL:

`   &navbar=off   `

This removes the Power Apps navigation bar and provides a focused, full-screen runtime experience.
