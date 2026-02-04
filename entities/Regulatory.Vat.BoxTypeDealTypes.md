---
uid: Regulatory.Vat.BoxTypeDealTypes
---
# Regulatory.Vat.BoxTypeDealTypes


Determines the Amount Category which will be accumulated in the Box Type according to the specified the Deal Type.

## General
Namespace: [Regulatory.Vat](Regulatory.Vat.md)  
Repository: Regulatory.Vat.BoxTypeDealTypes  
Base Table: VAT_Box_Type_Deal_Types  
Introduced In Version: 22.1.5.98  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {BoxTypeId}  
Search Members:   
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Vat.BoxTypeDealTypes](Regulatory.Vat.BoxTypeDealTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) | [AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) | Specifies the amount type from the Vat Entry which will be accumulated 
| [Notes](Regulatory.Vat.BoxTypeDealTypes.md#notes) | string (max) __nullable__ | Notes for this BoxTypeDealType. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxType](Regulatory.Vat.BoxTypeDealTypes.md#boxtype) | [BoxTypes](Regulatory.Vat.BoxTypes.md) | The type of box in a VAT declaration. |
| [DealType](Regulatory.Vat.BoxTypeDealTypes.md#dealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) | Deal Type for the box. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Vat.BoxTypeDealTypes.md#id) | guid |  
| [ObjectVersion](Regulatory.Vat.BoxTypeDealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Vat.BoxTypeDealTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Vat.BoxTypeDealTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Vat.BoxTypeDealTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Vat.BoxTypeDealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AmountCategory

Specifies the amount type from the Vat Entry which will be accumulated

Type: **[AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory)**  
Category: **System**  
Allowed values for the `AmountCategory`(Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) data attribute  
Allowed Values (Regulatory.Vat.BoxTypeDealTypesRepository.AmountCategory Enum Members)  

| Value | Description |
| ---- | --- |
| VAT | The amount of the tax for the operation in base currency.. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 0 <br /> Domain API Value: 'VAT' |
| BASE | Amount of the operation without the tax in base currency.. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 1 <br /> Domain API Value: 'BASE' |
| TOTAL | Amount of the operation with the tax in base currency.. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 2 <br /> Domain API Value: 'TOTAL' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this BoxTypeDealType.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### BoxType

The type of box in a VAT declaration.

Type: **[BoxTypes](Regulatory.Vat.BoxTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DealType

Deal Type for the box.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Vat.BoxTypeDealTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Vat.BoxTypeDealTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Vat_BoxTypeDealTypes

Domain API Entity Type: 
Regulatory_Vat_BoxTypeDealType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_BoxTypeDealTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_BoxTypeDealTypes?$top=10>

