---
uid: Regulatory.Common.CodeLists
---
# Regulatory.Common.CodeLists Entity

**Namespace:** [Regulatory.Common](Regulatory.Common.md)  

Code Lists. Entity: Reg_Code_Lists (Introduced in version 26.2.0.62)

## Default Visualization
Default Display Text Format:  
_{ListCode}: {ListName}_  
Default Search Members:  
_ListCode; EntityTypeName_  
Code Data Member:  
_ListCode_  
Name Data Member:  
_EntityTypeName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Common.CodeLists](Regulatory.Common.CodeLists.md)  
  * [Regulatory.Common.CodeEntries](Regulatory.Common.CodeEntries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Authority](Regulatory.Common.CodeLists.md#authority) | string (128) __nullable__ | The source authority (agency), which controls the list. `Filter(eq;like)` 
| [Description](Regulatory.Common.CodeLists.md#description) | string (254) __nullable__ | Description of the list. `Filter(eq;like)` 
| [DisplayText](Regulatory.Common.CodeLists.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityTypeName](Regulatory.Common.CodeLists.md#entitytypename) | string (128) __nullable__ | Internal entity type, whose entities map to entries in the list. `Filter(eq;like)` 
| [ExternalId](Regulatory.Common.CodeLists.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Common.CodeLists.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Regulatory.Common.CodeLists.md#id) | guid |  
| [IsActive](Regulatory.Common.CodeLists.md#isactive) | boolean | Specifies whether the list is active. `Required` `Default(true)` `Filter(eq)` 
| [LegalReference](Regulatory.Common.CodeLists.md#legalreference) | string (254) __nullable__ | Reference to law/article/ordinance number, URL, file name, etc. `Filter(eq;like)` 
| [ListCode](Regulatory.Common.CodeLists.md#listcode) | string (16) | Regulatory code of the list, unique within the jurisdiction. `Required` `Filter(eq;like)` 
| [ListName](Regulatory.Common.CodeLists.md#listname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Regulatory name of the list. `Required` `Filter(like)` 
| [Notes](Regulatory.Common.CodeLists.md#notes) | string (max) __nullable__ | Notes for the list. 
| [ObjectVersion](Regulatory.Common.CodeLists.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ValidFrom](Regulatory.Common.CodeLists.md#validfrom) | date __nullable__ | When not null specifies the first date when the list is valid. `Filter(eq;ge;le)` 
| [ValidTo](Regulatory.Common.CodeLists.md#validto) | date __nullable__ | When not null specifies the last date (inclusive) when the list is valid. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Jurisdiction](Regulatory.Common.CodeLists.md#jurisdiction) | [Jurisdictions](Regulatory.Common.Jurisdictions.md) | The jurisdiction to which the list belongs. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| CodeEntries | [CodeEntries](Regulatory.Common.CodeEntries.md) | List of `CodeEntry`(Regulatory.Common.CodeEntries.md) child objects, based on the `Regulatory.Common.CodeEntry.CodeList`(Regulatory.Common.CodeEntries.md#codelist) back reference 


## Attribute Details

### Authority

The source authority (agency), which controls the list. `Filter(eq;like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Description

Description of the list. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityTypeName

Internal entity type, whose entities map to entries in the list. `Filter(eq;like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

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

### IsActive

Specifies whether the list is active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### LegalReference

Reference to law/article/ordinance number, URL, file name, etc. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListCode

Regulatory code of the list, unique within the jurisdiction. `Required` `Filter(eq;like)`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### ListName

Regulatory name of the list. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the list.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ValidFrom

When not null specifies the first date when the list is valid. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidTo

When not null specifies the last date (inclusive) when the list is valid. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Jurisdiction

The jurisdiction to which the list belongs. `Required` `Filter(multi eq)`

_Type_: **[Jurisdictions](Regulatory.Common.Jurisdictions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Regulatory.Common.CodeLists erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Common.CodeLists erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Common_CodeLists

Domain API Entity Type: 
Regulatory_Common_CodeList

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Common_CodeLists?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Common_CodeLists?$top=10>

