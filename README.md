- 👋 Hi, I’m @ococolos
- 👀 I’m interested primarily in back-end programming, with emphasis on Django.
- 🌱 I’m currently learning Javascript and Angular
- 📫 You can reach me on my email ioanovidiu.cocolos@gmail.com

<!---
ococolos/ococolos is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Details on the private repositories:

## **PCL_APPS**
  Central hub for all applications designed for the Production Control and Logistics department; each requested application by the department is designed as a separate Django app.
  
 ### Sub-applications
 #### Shipping requests
 ##### General info
  This application is created for the Planning department and replaces classical emails to the Shipping department regarding any out-bound shipment. Roles assigned to the Demand Planners to create a ShippingRequest and to the Shipping Clerks to update a ShippingRequest's status. Authentication is done with company Windows credentials, through the Active Directory. All asctions performed on a ShippingRequest are logged via django-simple-history. 
 ##### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-simple-history 3.0.0
 * htmx 1.4.1
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1
 
 #### Receiving
 ##### General info
  This application is a work in progress intended to visually represent in real-time the status of in-bound shipments of parts. It is a work in it's early stages - updates to come
 ##### Technologies used
  To be assessed
  
## **PURCHASING_APPS**
 Central hub for all applications designed for the Purchasing department; each requested application by the department is designed as a separate Django app.
 
 ### Sub-applications
 #### Contracts
 ##### General info
  Created for a better monitoring of the exsting contracts between Eberspaecher and suppliers of indirect materials (materials not for production) and existing NDAs with those suppliers. Read/write access restricted to Purchasing department. Authentication is done with company Windows credentials, through the Active Directory. For contracts who's renewal/expiration date is less than 30 days, an alert is sent to a particular subgroup of the Purchasing department, nominated by the department manager. The notification is sent daily via django.core.email until the contract is extended or canceled. To achieve this, Django-Q performs a scheduled task daily at 08:00AM.
  
 ##### Technologies used
 * django 3.0.10
 * django-auth-ldap 2.3.0
 * python-ldap 3.3.1
 * django-q 1.3.5
 * django-crispy-forms 1.10.0
 * django-environ 0.4.5
 * django-mssql-backend 2.8.1
