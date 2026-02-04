---
uid: Applications.Service.ServiceObjects
---
# Applications.Service.ServiceObjects


Contains the serviceable objects. The service objects can be covered by service agreements, serviced in service activities, etc.

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceObjects  
Base Table: Srv_Service_Objects  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: SerialNumber; Name  
Code Member: SerialNumber  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  ServiceObjectTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Service.ServiceObjects](Applications.Service.ServiceObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Applications.Service.ServiceObjects.md#isactive) | boolean | Indicates whether the current service object is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.53` 
| [Name](Applications.Service.ServiceObjects.md#name) | string (254) | The name of this ServiceObject. `Required` `Filter(eq;like)` 
| [Notes](Applications.Service.ServiceObjects.md#notes) | string (254) __nullable__ | Notes for this ServiceObject. 
| [SerialNumber](Applications.Service.ServiceObjects.md#serialnumber) | string (32) __nullable__ | The serial number of the item, that is being serviced. `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.Service.ServiceObjects.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this ServiceObject applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [ManagedAsset](Applications.Service.ServiceObjects.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable) | Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74` |
| [Product](Applications.Service.ServiceObjects.md#product) | [Products](General.Products.Products.md) (nullable) | When not-null identifies the product, from which the service object was created. `Filter(multi eq)` |
| [SerialNumberObj](Applications.Service.ServiceObjects.md#serialnumberobj) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number for the product, that corresponds to this service object. If there is no product, then the other field for 'Serial number' is used to specify this data. `Filter(multi eq)` |
| [ServicedProduct](Applications.Service.ServiceObjects.md#servicedproduct) | [Products](General.Products.Products.md) (nullable) | The product, which is used to physically store the service object, when it is serviced. Need to be specified, only when it is different from Product; otherwise, it is null. `Filter(multi eq)` |
| [ServiceObjectType](Applications.Service.ServiceObjects.md#serviceobjecttype) | [ServiceObjectTypes](Applications.Service.ServiceObjectTypes.md) (nullable) | When not null specifies the type of the service object. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceObjects.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceObjects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Service.ServiceObjects.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Service.ServiceObjects.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Service.ServiceObjects.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Service.ServiceObjects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

Indicates whether the current service object is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.53`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this ServiceObject. `Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.Name`
### Notes

Notes for this ServiceObject.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SerialNumber

The serial number of the item, that is being serviced. `Filter(like)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.SerialNumberObj != null), null, obj.SerialNumber)`
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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### EnterpriseCompany

The Enterprise Company to which this ServiceObject applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74`

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

When not-null identifies the product, from which the service object was created. `Filter(multi eq)`

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumberObj

Serial number for the product, that corresponds to this service object. If there is no product, then the other field for 'Serial number' is used to specify this data. `Filter(multi eq)`

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.SerialNumber != null), null, obj.SerialNumberObj)`
### ServicedProduct

The product, which is used to physically store the service object, when it is serviced. Need to be specified, only when it is different from Product; otherwise, it is null. `Filter(multi eq)`

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceObjectType

When not null specifies the type of the service object. `Filter(multi eq)`

Type: **[ServiceObjectTypes](Applications.Service.ServiceObjectTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.Service.ServiceObjects erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceObjects erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceObjects

Domain API Entity Type: 
Applications_Service_ServiceObject

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceObjects?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceObjects?$top=10>

