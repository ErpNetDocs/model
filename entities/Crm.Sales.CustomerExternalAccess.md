---
uid: Crm.Sales.CustomerExternalAccess
---
# Crm.Sales.CustomerExternalAccess


Customer External Access defines which external users are allowed to access data related to a specific customer.

This data type specifies external users and their access rights to customer-related information such as sales orders, invoices, payments, and other sales documents, intended for controlled access outside the internal user environment.

It is used to securely expose customer data to external parties, ensuring appropriate visibility and separation from internal operational access.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.CustomerExternalAccess  
Base Table: Crm_Customer_External_Access  
Introduced In Version: 25.1.2.51  
API access:  ReadWrite  

## Visualization
Display Format: {Customer} - {ShipToCustomer} - {User}  
Search Members: Customer.Party.PartyName  
Name Member: Customer.Party.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  
Aggregate Root:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DaysBackAccess](Crm.Sales.CustomerExternalAccess.md#daysbackaccess) | int32 __nullable__ | The maximum number of past days the user is allowed to view. If NULL, the access is unlimited. 
| [Notes](Crm.Sales.CustomerExternalAccess.md#notes) | string (max) __nullable__ | Notes for this External Access. 
| [Role](Crm.Sales.CustomerExternalAccess.md#role) | [Role](Crm.Sales.CustomerExternalAccess.md#role) | The role of the user, defines the granted access. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Customer](Crm.Sales.CustomerExternalAccess.md#customer) | [Customers](Crm.Sales.Customers.md) | The customer whose data is being accessed. |
| [User](Crm.Sales.CustomerExternalAccess.md#user) | [Users](Systems.Security.Users.md) | The user to whom the access is granted. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.CustomerExternalAccess.md#id) | guid |  
| [ObjectVersion](Crm.Sales.CustomerExternalAccess.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.CustomerExternalAccess.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DaysBackAccess

The maximum number of past days the user is allowed to view. If NULL, the access is unlimited.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **30**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this External Access.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Role

The role of the user, defines the granted access.

Type: **[Role](Crm.Sales.CustomerExternalAccess.md#role)**  
Category: **System**  
Allowed values for the `Role`(Crm.Sales.CustomerExternalAccess.md#role) data attribute  
Allowed Values (Crm.Sales.CustomerExternalAccessRepository.Role Enum Members)  

| Value | Description |
| ---- | --- |
| Basic | Basic. Stored as 'L10'. <br /> Database Value: 'L10' <br /> Model Value: 0 <br /> Domain API Value: 'Basic' |
| Orders | Orders. Stored as 'L20'. <br /> Database Value: 'L20' <br /> Model Value: 1 <br /> Domain API Value: 'Orders' |
| OrdersWithPrices | Orders with Prices. Stored as 'L30'. <br /> Database Value: 'L30' <br /> Model Value: 2 <br /> Domain API Value: 'OrdersWithPrices' |
| Billing | Billing. Stored as 'L40'. <br /> Database Value: 'L40' <br /> Model Value: 3 <br /> Domain API Value: 'Billing' |
| Admin | Admin. Stored as 'L80'. <br /> Database Value: 'L80' <br /> Model Value: 4 <br /> Domain API Value: 'Admin' |
| Owner | Owner. Stored as 'L90'. <br /> Database Value: 'L90' <br /> Model Value: 5 <br /> Domain API Value: 'Owner' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **OrdersWithPrices**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Customer

The customer whose data is being accessed.

Type: **[Customers](Crm.Sales.Customers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### User

The user to whom the access is granted.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Crm.Sales.CustomerExternalAccess erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.CustomerExternalAccess erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_CustomerExternalAccess

Domain API Entity Type: 
Crm_Sales_CustomerExternalAcces

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_CustomerExternalAccess?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_CustomerExternalAccess?$top=10>

