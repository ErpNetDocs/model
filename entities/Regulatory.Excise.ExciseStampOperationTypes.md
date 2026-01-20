---
uid: Regulatory.Excise.ExciseStampOperationTypes
---
# Regulatory.Excise.ExciseStampOperationTypes Entity

**Namespace:** [Regulatory.Excise](Regulatory.Excise.md)  

Specifies the type of the Excise Stamp operation. Entity: Exc_Excise_Stamp_Operation_Types (Introduced in version 22.1.5.85)

## Default Visualization
Default Display Text Format:  
_{Code}: {Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseStampOperationTypes](Regulatory.Excise.ExciseStampOperationTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseStampOperationTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Box1Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")` 
| [Box2Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")` 
| [Box3Effect](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect) | [ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect) | Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")` 
| [Code](Regulatory.Excise.ExciseStampOperationTypes.md#code) | string (32) | The unique code of the ExciseStampOperationType. `Required` `Filter(multi eq)` `ORD` 
| [DisplayText](Regulatory.Excise.ExciseStampOperationTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Regulatory.Excise.ExciseStampOperationTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseStampOperationTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Regulatory.Excise.ExciseStampOperationTypes.md#id) | guid |  
| [IsWholeLot](Regulatory.Excise.ExciseStampOperationTypes.md#iswholelot) | boolean __nullable__ | Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied. `Filter(eq)` `Introduced in version 24.1.1.80` 
| [Name](Regulatory.Excise.ExciseStampOperationTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of operation (multi-language string). `Required` `Filter(like)` 
| [ObjectVersion](Regulatory.Excise.ExciseStampOperationTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RequireProduct](Regulatory.Excise.ExciseStampOperationTypes.md#requireproduct) | boolean __nullable__ | Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line. `Filter(eq)` `Introduced in version 24.1.1.91` 
| [TrackSequence](Regulatory.Excise.ExciseStampOperationTypes.md#tracksequence) | boolean __nullable__ | Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved. `Filter(eq)` `Introduced in version 24.1.1.82` 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Box1Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")`

_Type_: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box1effect)**  
_Category_: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
_Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)_  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Minus' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **NoChange**  
_Show in UI_: **ShownByDefault**  

### Box2Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")`

_Type_: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box2effect)**  
_Category_: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
_Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)_  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Minus' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **NoChange**  
_Show in UI_: **ShownByDefault**  

### Box3Effect

Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration. `Required` `Default("N")`

_Type_: **[ExciseStampOperation<br />TypeEnum](Regulatory.Excise.ExciseStampOperationTypes.md#box3effect)**  
_Category_: **System**  
Generic enum type for ExciseStampOperationTypeEnum properties  
_Allowed Values (Regulatory.Excise.ExciseStampOperationTypeEnum Enum Members)_  

| Value | Description |
| ---- | --- |
| NoChange | NoChange value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NoChange' |
| Plus | Plus value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Plus' |
| Minus | Minus value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Minus' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **NoChange**  
_Show in UI_: **ShownByDefault**  

### Code

The unique code of the ExciseStampOperationType. `Required` `Filter(multi eq)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsWholeLot

Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied. `Filter(eq)` `Introduced in version 24.1.1.80`

_Type_: **boolean __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

Name of operation (multi-language string). `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RequireProduct

Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line. `Filter(eq)` `Introduced in version 24.1.1.91`

_Type_: **boolean __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TrackSequence

Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved. `Filter(eq)` `Introduced in version 24.1.1.82`

_Type_: **boolean __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

