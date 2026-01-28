---
uid: Regulatory.Excise.ExciseStampLots
---
# Regulatory.Excise.ExciseStampLots


Sequence of excise stamps with same production batch and type, received with one delivery.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseStampLots  
Base Table: Exc_Excise_Stamp_Lots  
Introduced In Version: 22.1.6.13  
API access:  ReadWrite  

## Visualization
Display Format: {BatchNumber} {StartNumber}  
Search Members: BatchNumber  
Code Member: BatchNumber  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseStampLots](Regulatory.Excise.ExciseStampLots.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BatchNumber](Regulatory.Excise.ExciseStampLots.md#batchnumber) | string (30) | Production batch of the Excise Stamps. `Required` `Filter(multi eq;like)` `ORD` 
| [EndNumber](Regulatory.Excise.ExciseStampLots.md#endnumber) | string (30) | End number of the lot. `Required` 
| [IsActive](Regulatory.Excise.ExciseStampLots.md#isactive) | boolean | Is Active. `Required` `Default(true)` `Filter(eq)` 
| [Prefix](Regulatory.Excise.ExciseStampLots.md#prefix) | string (30) __nullable__ | Specifies the prefix that is used in forming the value of the "BatchNumber" field. `Filter(eq;like)` `Introduced in version 24.1.2.1` 
| [PurchaseLotNumber](Regulatory.Excise.ExciseStampLots.md#purchaselotnumber) | string (30) | Type and number of the document with which the excise stamps were received from the customs administration. `Required` `Filter(eq;like)` 
| [Quantity](Regulatory.Excise.ExciseStampLots.md#quantity) | int32 | Number of excise stamps in the lot. `Required` `Default(0)` 
| [StartNumber](Regulatory.Excise.ExciseStampLots.md#startnumber) | string (30) | Start number of the lot. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ExciseProductType](Regulatory.Excise.ExciseStampLots.md#exciseproducttype) | [ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable) | Specifies the Excise Product Type of the Excise Stamps in the lot. `Filter(multi eq)` `Introduced in version 22.1.6.53` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseStampLots.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseStampLots.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.ExciseStampLots.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseStampLots.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseStampLots.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.ExciseStampLots.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BatchNumber

Production batch of the Excise Stamps. `Required` `Filter(multi eq;like)` `ORD`

Type: **string (30)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( IsNullOrEmpty( obj.Prefix), Concat( obj.StartNumber, "-", obj.Quantity.ToString( )), Concat( new [] {obj.Prefix, "-", obj.StartNumber, "-", obj.Quantity.ToString( )}))`
### EndNumber

End number of the lot. `Required`

Type: **string (30)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Quantity > 0), obj.StartNumber, null).AddToNumberInString( Convert( ( obj.Quantity - 1), BigInteger), null)`
### IsActive

Is Active. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Prefix

Specifies the prefix that is used in forming the value of the "BatchNumber" field. `Filter(eq;like)` `Introduced in version 24.1.2.1`

Type: **string (30) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

### PurchaseLotNumber

Type and number of the document with which the excise stamps were received from the customs administration. `Required` `Filter(eq;like)`

Type: **string (30)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

### Quantity

Number of excise stamps in the lot. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### StartNumber

Start number of the lot. `Required`

Type: **string (30)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **30**  
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

### ExciseProductType

Specifies the Excise Product Type of the Excise Stamps in the lot. `Filter(multi eq)` `Introduced in version 22.1.6.53`

Type: **[ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampLots erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampLots erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseStampLots

Domain API Entity Type: 
Regulatory_Excise_ExciseStampLot

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseStampLots?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseStampLots?$top=10>

