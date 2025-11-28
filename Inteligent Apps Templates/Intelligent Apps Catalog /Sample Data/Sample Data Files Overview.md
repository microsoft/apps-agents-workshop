**Sample Data Files Overview**
==============================

The Intelligent Apps Catalog includes several sample data files that you can use to quickly configure the App Hub, Use Case Catalog, UX Catalog, and Prompt Catalog. Each file provides a structured template that helps you understand the expected data format and how the catalog components work together.

**1\. App Catalog Sample Data — Sample Data App Catalogs.csv**
----------------------------------------------------------------

This file contains the foundational information needed to configure your **App Hub**. Each row represents an app that you want to showcase inside the hub.

**Key fields included:**

*   **App Name** – The display name of the application.
    
*   **App Logo** – A link or reference to the image representing the app.
    
*   **App Link** – The URL or deep link that launches the app.
    

**How it's used:**Import or map this file into your App Catalog table to create an embedded App Hub experience. Each entry determines which applications appear in the catalog and where users are redirected when launching the app.

**2\. Use Case Catalog Sample Data — Sample Data Use Case Catalogs.csv**
---------------------------------------------------------------------------

This file provides a template for setting up your **Use Cases Catalog**, which serves as your central repository of reusable organizational solutions.

**Key fields included:**

*   **Use Case Name** – The title of the use case or solution.
    
*   **Description** – A summary explaining what the use case does and why it’s useful.
    
*   **Repository Link** – A URL pointing to the solution package, documentation, or source code.
    

**How it's used:**Load this data into your Use Case Catalog to showcase published solutions, templates, components, connectors, or any reusable assets your teams can benefit from. This catalog helps teams quickly discover and reuse best-practice solutions.

**3\. UX Catalog Sample Data — Sample Data UX Catalogs.csv**
--------------------------------------------------------------

This file contains information used to populate the **UX Catalog**, which is responsible for showcasing generated UX experiences and linking them to relevant use cases.

**Key fields included:**

*   **UX Experience Name** – The name of the UX pattern or page layout.
    
*   **Description** – A short explanation of what the UX page represents.
    
*   **Sample Image** – A reference to the visual sample used when generating the UI.
    
*   **Use Case Reference** – A link or key that connects this UX entry to a specific item in the Use Case Catalog.
    
*   **UX Page Link** – A URL or app link that opens the generated UX page at runtime.
    

**How it's used:**This data powers the visual UX Gallery, allowing users to preview sample screens, understand how they map to real use cases, and navigate to live generated pages to learn how they function.

**4\. Prompt Catalog Sample Data — Sample Data Prompt Catalogs.csv**
----------------------------------------------------------------------

This file defines the content of the **Prompt Catalog**, which provides structured prompts for generating UX pages and intelligent application flows.

**Key fields included:**

*   **Prompt Details** – The actual generative prompt text used to create a page or component.
    
*   **Description** – A summary of what the prompt does or when it should be used.
    
*   **Associated Gen UX Page** – A reference linking the prompt to the corresponding UX page.
    
*   **Starter Prompt** – A flag indicating whether the prompt should appear as an initial, entry-level prompt.
    
*   **Prompt Order** – A numeric value determining the sequence in which prompts are shown.
    

**How it's used:**Import this file to define how prompts appear to the user, the order they follow, and how they connect to the UX pages. This provides a consistent, guided prompt-driven experience for generating intelligent application pages.
