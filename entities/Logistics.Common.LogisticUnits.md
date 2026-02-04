---
uid: Logistics.Common.LogisticUnits
---
# Logistics.Common.LogisticUnits


Composition of products established for transport and/or storage which needs to be managed through the supply chain.

## General
Namespace: [Logistics.Common](Logistics.Common.md)  
Repository: Logistics.Common.LogisticUnits  
Base Table: Log_Logistic_Units  
Introduced In Version: 21.1.0.77  
API access:  ReadWrite  

## Renames

Old name: Logistics.LogisticUnits  
New name: Logistics.Common.LogisticUnits  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {SerialCode}  
Search Members: SerialCode  
Code Member: SerialCode  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  LogisticUnitTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  
  * [Logistics.Common.LogisticUnitContents](Logistics.Common.LogisticUnitContents.md)  
  * [Logistics.Common.LogisticUnitSpecifications](Logistics.Common.LogisticUnitSpecifications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExpectedWeight](Logistics.Common.LogisticUnits.md#expectedweight) | decimal (12, 3) __nullable__ | Expected weight of the unit, in the measurement unit, specified in the Logistic Unit Type. Used for planning purposes. NULL means unknown.  
| [IsActive](Logistics.Common.LogisticUnits.md#isactive) | boolean | Indicates whether the logistic unit is currently active. 
| [MeasuredWeight](Logistics.Common.LogisticUnits.md#measuredweight) | decimal (12, 3) __nullable__ | Actual measured weight of the unit, in the measurement unit, specified in the Logistic Unit Type. NULL means unknown.  
| [Notes](Logistics.Common.LogisticUnits.md#notes) | string (max) __nullable__ | Notes for this LogisticUnit. `Filter(like)` 
| [SerialCode](Logistics.Common.LogisticUnits.md#serialcode) | string (32) | Unique serial code of the logistic unit. If GS1 coding is used, this is the SSCC. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Common.LogisticUnits.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable) | General type of the cargo of the logistic unit. NULL means unknown or N/A. |
| [LogisticUnitType](Logistics.Common.LogisticUnits.md#logisticunittype) | [LogisticUnitTypes](Logistics.Common.LogisticUnitTypes.md) (nullable) | The type of the logistic unit. NULL means the type is currently unknown. |
| [RepresentedAsProduct](Logistics.Common.LogisticUnits.md#representedasproduct) | [Products](General.Products.Products.md) (nullable) | When the logistic unit is also a tradeable item, specifies the product used to trade the unit. The product should uniquely identify only one logistic unit. Note that this is different from a logistic unit containing a single item. NULL means that the unit is not a tradeable item. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Common.LogisticUnits.md#id) | guid |  
| [ObjectVersion](Logistics.Common.LogisticUnits.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Common.LogisticUnits.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Common.LogisticUnits.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Common.LogisticUnits.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Common.LogisticUnits.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Contents | [LogisticUnitContents](Logistics.Common.LogisticUnitContents.md) | List of `LogisticUnitContent`(Logistics.Common.LogisticUnitContents.md) child objects, based on the `Logistics.Common.LogisticUnitContent.LogisticUnit`(Logistics.Common.LogisticUnitContents.md#logisticunit) back reference 
| Specifications | [LogisticUnitSpecifications](Logistics.Common.LogisticUnitSpecifications.md) | List of `LogisticUnitSpecification<br />`(Logistics.Common.LogisticUnitSpecifications.md) child objects, based on the `Logistics.Common.LogisticUnitSpecification.LogisticUnit`(Logistics.Common.LogisticUnitSpecifications.md#logisticunit) back reference 


## Attribute Details

### ExpectedWeight

Expected weight of the unit, in the measurement unit, specified in the Logistic Unit Type. Used for planning purposes. NULL means unknown.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the logistic unit is currently active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### MeasuredWeight

Actual measured weight of the unit, in the measurement unit, specified in the Logistic Unit Type. NULL means unknown.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this LogisticUnit. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SerialCode

Unique serial code of the logistic unit. If GS1 coding is used, this is the SSCC.

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
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

### CargoType

General type of the cargo of the logistic unit. NULL means unknown or N/A.

Type: **[CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LogisticUnitType

The type of the logistic unit. NULL means the type is currently unknown.

Type: **[LogisticUnitTypes](Logistics.Common.LogisticUnitTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RepresentedAsProduct

When the logistic unit is also a tradeable item, specifies the product used to trade the unit. The product should uniquely identify only one logistic unit. Note that this is different from a logistic unit containing a single item. NULL means that the unit is not a tradeable item.

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### UpdateGS1ApplicationCodes

Based on the internal data in the logistic unit and its contents, creates or updates the GS1 application codes.              The data is than stored in the logistic unit specifications.              The method does not commit the object transaction.  
Return Type: **void**  
Declaring Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md)**  
Domain API Request: **POST**  

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

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnits erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnits erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Common_LogisticUnits

Domain API Entity Type: 
Logistics_Common_LogisticUnit

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Common_LogisticUnits?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Common_LogisticUnits?$top=10>

