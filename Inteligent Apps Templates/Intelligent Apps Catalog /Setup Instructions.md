
**Setup Instructions**
======================

Follow the steps below to install the Intelligent Apps Catalog, configure your Dataverse tables, import the sample data files, and launch the runtime experience.

**1\. Download and Import the Latest Solution**
------------------------------------

Download the most recent version of the solution package:

**➡️ [IntelligentAppsInnovationCompanion](./Catalog%20Solution)**

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

Click [here](./Sample%20Data) to download the files

**Import the data in this order only.** Review the details of each of the csv files [here](./Sample%20Data/Sample%20Data%20Files%20Overview.md)

*   sample\_data\_app\_catalog.csv → **App Catalog** table
    
*   sample\_data\_use\_case\_catalog.csv → **Use Case Catalog** table
    
*   sample\_data\_ux\_catalog.csv → **UX Catalog** table (do not map Use Case Lookup column)
    
*   sample\_data\_prompt\_catalog.csv → **Prompt Catalog** table (wait till UX Catalog sample data is available before importing this)
  > Note: Some prompts may contain actual table names which were used to build the page. As you copy the prompts to clipboard, improve the prompt to use your table names.
    

### **How to Import**

1.  In the Catalog Management app, navigate to the App Catalog page.
    
2.  Use the **Import Data** option (Import from Excel → Import from CSV ).
    <img width="1890" height="287" alt="image" src="https://github.com/user-attachments/assets/41f7b654-87b1-47f9-8169-7b0246e7a0ca" />
    

    Click on … on the right corner of the page as highlighted below and select the icon next to Import from Excel. Then select Import from CSV
    <img width="370" height="143" alt="image" src="https://github.com/user-attachments/assets/47957c41-6b65-45cf-a02b-dac8df08308b" />



3.  Map the CSV columns to Dataverse fields as shown in the image below.
   
    <img width="350" style="border: 1px solid #ccc; border-radius: 6px;" alt="image" src="https://github.com/user-attachments/assets/226fc6c9-3065-4479-b0f8-55e83202eb7b" />

4.  Complete the import and wait for the records to import successfully.
  
Repeat this process for all four CSV files.

* Use Case Catalog Mappings - 

<img width="350" alt="image" src="https://github.com/user-attachments/assets/f946a4c2-d2c7-420d-bf0e-75d568804cac" />


* UX Catalog Mappings - **(do not map Use Case Lookup column)** 

<img width="350" alt="image" src="https://github.com/user-attachments/assets/360eff87-57ba-4591-9061-8e8ed367ffa1" />


* Prompt Catalog Mappings- **(wait till UX Catalog sample data is available before importing this)**

<img width="350" alt="image" src="https://github.com/user-attachments/assets/9ef35055-02b1-455d-95ce-f7d3c3419e67" />



**4\. Add Images**
-----------------------------------

Each part of the catalog uses images differently. Follow the guidelines below to ensure that visuals display correctly within the Catalog Hub.

### **Gen Pages Sample Images (for UX Catalog)**

Use the provided [**Gen Pages Sample Images**](./Sample%20Images/Gen%20Pages%20Images) folder to populate the **UX Catalog**.These images show sample generative UX pages and can be uploaded directly as-is.

**Steps:**

1.  Open the **UX Catalog** table in Catalog Management App.
    
2.  Open each record and upload the corresponding image. 
    
    

### **Use Case Images (Use Your Own)**

The [**sample images**](./Sample%20Images/Use%20Cases%20Images) included for Use Cases are placeholders. When configuring your organization’s **Use Case Catalog**, upload **your own solution images**, such as:

*   screenshots
    
*   workflow diagrams
    
*   solution visuals
    
*   product icons
    

This ensures the repository reflects your actual solutions.

**Steps:**

1.  Open the **Use Case Catalog** table in Catalog Management App.
    
2.  Open each record and upload the corresponding image. 
    

### **App Catalog Images (Use Your Own)**

The [**sample images **](./Sample%20Images/App%20Catalog%20Images) icons are only examples. For your real App Catalog, upload your **actual app icons or logos** so the App Hub reflects the apps your team uses.

**Steps:**

1.  Open the **App Catalog** table in Catalog Management App.
    
2.  Open each record and upload the corresponding image.
   

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
