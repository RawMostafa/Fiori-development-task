Northwind Fiori Application on SAP BTP
# Project Description
This project demonstrates the development of a SAP Fiori List Report application using the SAP Business Technology Platform (BTP).
The application consumes the Northwind OData service to display product data in a structured and user-friendly interface.

# Architecture Overview
The application is built using SAP Business Application Studio (BAS). A destination is configured to connect the application to the external Northwind OData service.

BAS: Used as the development environment to generate and run the Fiori application.

Cloud Foundry: Manages the runtime and application hosting.

# Setup Instructions
- Register for a SAP BTP Trial account.

- Create and access your Sub-account in the BTP Cockpit.

- Enable Cloud Foundry and create a space (e.g., dev).

- Subscribe to:
     .SAP Business Application Studio

     .Destination Service

- Assign the required role collections to your user.

- Create a Destination with the Northwind OData service configuration.

- Launch SAP Business Application Studio.

- Create a new Dev Space (SAP Fiori type).

- Generate a Fiori Application using the List Report template.

- Connect to the OData service: https://services.odata.org/V2/Northwind/Northwind.svc/

- Modify the annotation.xml file to add the data fields for the main columns:

{ProductID-ProductName-UnitPrice} by using 
<!-- <Annotations Target="NorthwindModel.Product"> 
            <Annotation Term="UI.LineItem">
                <Collection>
                    <Record Type="UI.DataField">
                        <PropertyValue Property="Value" Path="ProductID" />
                    </Record>
                    <Record Type="UI.DataField">
                        <PropertyValue Property="Value" Path="ProductName" />
                    </Record>
                    <Record Type="UI.DataField">
                        <PropertyValue Property="Value" Path="UnitPrice" />
                    </Record>
                </Collection>
            </Annotation>
        </Annotations> -->

-  Run the application preview and click on the GO button to verify the data is displayed.

# OData Entity Used
The Products entity set was selected because it provides meaningful and structured business data such as product names, prices, and stock levels. This makes it ideal for demonstrating a List Report application with multiple useful columns.

# Challenges Faced
During the configuration of the data source, the following warning appeared:

"No backend annotations associated with this service were retrieved"

The Solution:
Through research, I discovered that the Northwind OData service is a simple public demo service and does not provide annotations (metadata) that instruct SAP Fiori/BAS on how to automatically render the data in the UI. To resolve this, I manually defined the columns in the local annotations file.

# Screenshots
You can view the project assets and screenshots here:
<!--https://github.com/RawMostafa/Fiori-development-task/tree/main/docs-->