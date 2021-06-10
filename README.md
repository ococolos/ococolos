- 👋 Hi, I’m @ococolos
- 👀 I’m interested primarily in back-end programming, with emphasis on Django.
- 🌱 I’m currently learning Javascript and Angular
- 📫 You can reach me on my email ioanovidiu.cocolos@gmail.com

<!---
ococolos/ococolos is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Details on the private repositories:
All applications made for internal purposes are deployed on Windows IIS. 

# DJANGO APPS
## **PCL_APPS**
  Central hub for all applications designed for the Production Control and Logistics department; each requested application by the department is designed as a separate Django app.
  
 ### Sub-applications
 ### Shipping requests
 #### General info
  This application is created for the Planning department and replaces classical emails to the Shipping department regarding any out-bound shipment. Roles assigned to the Demand Planners to create a ShippingRequest and to the Shipping Clerks to update a ShippingRequest's status. Authentication is done with company Windows credentials, through the Active Directory. All asctions performed on a ShippingRequest are logged via django-simple-history. Local refresh performed every 30seconds with HTMX-GET (Ajax) to show any new requests created.
 #### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-simple-history 3.0.0
 * htmx 1.4.1
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1
 
 ### Receiving
 #### General info
  This application is a work in progress intended to visually represent in real-time the status of in-bound shipments of parts. It is a work in it's early stages - updates to come
 #### Technologies used
  To be assessed
  
## **PURCHASING_APPS**
 Central hub for all applications designed for the Purchasing department; each requested application by the department is designed as a separate Django app.
 
 ### Sub-applications
 ### Contracts
 #### General info
  Created for a better monitoring of the exsting contracts between Eberspaecher and suppliers of indirect materials (materials not for production) and existing NDAs with those suppliers. Read/write access restricted to Purchasing department. Authentication is done with company Windows credentials, through the Active Directory. For contracts who's renewal/expiration date is less than 30 days, an alert is sent to a particular subgroup of the Purchasing department, nominated by the department manager. The notification is sent daily via django.core.email until the contract is extended or canceled. To achieve this, Django-Q performs a scheduled task daily at 08:00AM.
  
 #### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-q 1.3.5
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1


## **STOCK_APPS**
 Central hub for all applications designed for the managing stocks in the production line, intended to replace paper hardcopy; each requested application is designed as a separate Django app. 
 
 ### Sub-applications
 ### Canning Kanban
 #### General info
 A kanban system for managing stocks of Cannings (subassemblies). Roles assigned to the Productio Team Leaders to create a CanningRequest and to the Canning Team Leaders to approve or reject a CanningRequest's. Authentication is done with company Windows credentials, through the Active Directory. Local refresh performed every 30seconds with HTMX-GET (Ajax) to show any new requests created.
 Application is not meant to replace SAP, but to be complementary to it - it allows for a more in-detail view of the finished goods or subassemblies stocks. For example, in SAP you see the stock for a subassembly in its entirety; with the applications, you are able to see the input of production Team Leaders and have a separation between subassemblies being produced and the same parts already built and sent for further assembly in a finished good.
 
 #### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * htmx 1.4.1
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1

### Internal Pipes
 #### General info
 A system for monitoring the stocks of Internal Pipes - exhaust pipes subassemblies produced for internal consumption on various finished goots. Virtual rack created on 5 levels, each level with 20 locations available. The Team Leaders responsible with the management of the stock have been granted read/write access. Authentication is done with company Windows credentials, through the Active Directory. 
 
 #### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1

## **PRODUCTION_APPS**
 Central hub for all applications designed for the production and quality department; each requested application is designed as a separate Django app. 
 
 ### Sub-applications
 ### Reject Sheet
 #### General info
 An application intended to replace paper-written monitoring of rejects - finished goods or subassemblies which contain a defect and need have not reached the end of the process. As all of the production lines have a different number of stations, each with an individual names, a dynamic form is generated for each Line via Django's form __init__.
 
  #### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1
 
 
 # FLASK APPS
 
 ## Quality wall
  First application built for Eberspaecher. It allows for the quality department to monitor finished goods inspected at the Quality Wall - an inspection point separated from the production line, intended as a last line of defence for potential defects escaping to the customer. Application has its own user database with User and Admin roles. Good and Defective parts are scanned, with data logged for each particular user, making traceability possible in case of 
