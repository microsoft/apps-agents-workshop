# Solutions

This folder contains the managed and unmanaged solutions used in the workshop labs.

| Solution | Version | Description |
| --- | --- | --- |
| NorthwindTraders | 1.0.0.11 | Sample data solution including the Northwind Sample Data App for seeding supplier and product records |

## Installing sample data

Follow these steps to import the Northwind Traders solution into your Power Platform environment and seed it with sample data.

### Step 1: Import the solution

1. Go to <https://make.powerapps.com> and select the environment you want to use.
2. In the left navigation, select **Solutions**.
3. Select **Import solution**.
4. Select **Browse** and choose `NorthwindTraders_1_0_0_11.zip` from the `solutions` folder of this repository.
5. Select **Next**, review the details, and select **Import**.
6. Wait for the import to complete. A confirmation message appears when the solution is successfully installed.

![Select Import solution on the Solutions page](images/Import-Solution.png)
Figure: Importing the Northwind Traders solution from the Solutions page.

### Step 2: Run the Northwind Sample Data app

Once the solution is imported, use the included **Northwind Sample Data** canvas app to populate the Dataverse tables with sample records.

1. In **Solutions**, open the **Northwind Traders** solution.
2. Locate the **Northwind Sample Data** app and select **Play** to launch it.
3. In the app, select **Load Data**.
4. Wait for the seeding process to complete. A success message confirms the data has been loaded.

![Sample Data Manager no data](images/Sample-Data-Manager-0.png)
Figure: Sample Data Manager with no data loaded.

![Sample Data Manager loading data](images/Sample-Data-Manager-1.png)
Figure: Loading data for each table.

![Sample Data Manager completed data load](images/Sample-Data-Manager-2.png)
Figure: Data finished loading.

> 💡 If the **Load Data** button is disabled or grayed out, sample data may already be present. Select **Remove Data** first, then re-run the installation.

### Step 3: Verify the data

After seeding, confirm the sample records are available in Dataverse.

1. Return to <https://make.powerapps.com> and select your environment.
2. In the left navigation, select **Tables**.
3. Search for the **Suppliers** table and confirm it contains records.

✅ The environment is now ready for use with the workshop labs.
