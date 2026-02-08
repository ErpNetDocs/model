---
uid: Regulatory.Excise.TaxWarehouses
---
# Regulatory.Excise.TaxWarehouses


Contains excise-related data for warehouses (stores), which are defined as tax warehouses. Products subject to excise duties must be produced in tax warehouses. They can also be stored, under duty suspension, in these tax warehouses.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.TaxWarehouses  
Base Table: Exc_Tax_Warehouses  
Introduced In Version: 21.1.1.1  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.TaxWarehouses  
New name: Regulatory.Excise.TaxWarehouses  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {Name:T}  
Search Members: TaxWarehouseExciseNumber; Name  
Code Member: TaxWarehouseExciseNumber  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.TaxWarehouses](Regulatory.Excise.TaxWarehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CustomsOffice](Regulatory.Excise.TaxWarehouses.md#customsoffice) | string (32) __nullable__ | The customs office to which the warehouse is headed.`Filter(like)` `Introduced in version 22.1.4.93` 
| [Name](Regulatory.Excise.TaxWarehouses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Tax Warehouse Name (Multilanguage)`Required` `Filter(like)` `Introduced in version 21.1.3.93` 
| [TaxWarehouseExciseNumber](Regulatory.Excise.TaxWarehouses.md#taxwarehouseexcisenumber) | string (32) | The excise identification number of the tax warehouse, issued by the competent authorities.`Required` `Default(&quot;-&quot;)` `Introduced in version 21.1.3.87` 
| [TraderExciseNumber](Regulatory.Excise.TaxWarehouses.md#traderexcisenumber) | string (32) | The excise identification number of the owner of the Tax Warehouse.`Required` `Default(&quot;-&quot;)` `Introduced in version 21.1.3.87` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Regulatory.Excise.TaxWarehouses.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise company to which the tax warehouse belongs. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.TaxWarehouses.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.TaxWarehouses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.TaxWarehouses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.TaxWarehouses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.TaxWarehouses.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.TaxWarehouses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CustomsOffice

The customs office to which the warehouse is headed.`Filter(like)` `Introduced in version 22.1.4.93`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Name

Tax Warehouse Name (Multilanguage)`Required` `Filter(like)` `Introduced in version 21.1.3.93`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxWarehouseExciseNumber

The excise identification number of the tax warehouse, issued by the competent authorities.`Required` `Default(&quot;-&quot;)` `Introduced in version 21.1.3.87`

Type: **string (32)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Default Value: **-**  
Show in UI: **ShownByDefault**  

### TraderExciseNumber

The excise identification number of the owner of the Tax Warehouse.`Required` `Default(&quot;-&quot;)` `Introduced in version 21.1.3.87`

Type: **string (32)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Default Value: **-**  
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

The Enterprise company to which the tax warehouse belongs.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.TaxWarehouses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.TaxWarehouses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_TaxWarehouses

Domain API Entity Type: 
Regulatory_Excise_TaxWarehouse

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_TaxWarehouses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_TaxWarehouses?$top=10>

