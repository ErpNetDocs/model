---
uid: Regulatory.Excise.ExciseStampOperationTypes
---
# Regulatory.Excise.ExciseStampOperationTypes


Specifies the type of the Excise Stamp operation.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseStampOperationTypes  
Base Table: Exc_Excise_Stamp_Operation_Types  
Introduced In Version: 22.1.5.85  
API access:  ReadWrite  

## Visualization
Display Format: {Code}: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseStampOperationTypes](Regulatory.Excise.ExciseStampOperationTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Box1Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. 
| [Box2Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. 
| [Box3Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. 
| [Code](Regulatory.Excise.ExciseStampOperationTypes.md#code) | string (32) | The unique code of the ExciseStampOperationType. `Required` `Filter(multi eq)` `ORD` 
| [IsWholeLot](Regulatory.Excise.ExciseStampOperationTypes.md#iswholelot) | boolean __nullable__ | Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied. 
| [Name](Regulatory.Excise.ExciseStampOperationTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of operation (multi-language string). 
| [RequireProduct](Regulatory.Excise.ExciseStampOperationTypes.md#requireproduct) | boolean __nullable__ | Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line. 
| [TrackSequence](Regulatory.Excise.ExciseStampOperationTypes.md#tracksequence) | boolean __nullable__ | Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseStampOperationTypes.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseStampOperationTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.ExciseStampOperationTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseStampOperationTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseStampOperationTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.ExciseStampOperationTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Box1Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

Type: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect)**  
Category: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'Minus' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **NoChange**  
Show in UI: **ShownByDefault**  

### Box2Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

Type: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect)**  
Category: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'Minus' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **NoChange**  
Show in UI: **ShownByDefault**  

### Box3Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

Type: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect)**  
Category: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'Minus' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **NoChange**  
Show in UI: **ShownByDefault**  

### Code

The unique code of the ExciseStampOperationType. `Required` `Filter(multi eq)` `ORD`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### IsWholeLot

Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied.

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

Name of operation (multi-language string).

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RequireProduct

Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line.

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TrackSequence

Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved.

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampOperationTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampOperationTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseStampOperationTypes

Domain API Entity Type: 
Regulatory_Excise_ExciseStampOperationType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseStampOperationTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseStampOperationTypes?$top=10>

