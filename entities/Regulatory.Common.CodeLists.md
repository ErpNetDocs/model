---
uid: Regulatory.Common.CodeLists
---
# Regulatory.Common.CodeLists


Represents a regulatory list of codes issued by an authority within a jurisdiction.

## General
Namespace: [Regulatory.Common](Regulatory.Common.md)  
Repository: Regulatory.Common.CodeLists  
Base Table: Reg_Code_Lists  
Introduced In Version: 26.2.0.62  
API access:  ReadWrite  

## Visualization
Display Format: {ListCode}: {ListName}  
Search Members: ListCode; EntityTypeName  
Code Member: ListCode  
Name Member: EntityTypeName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Common.CodeLists](Regulatory.Common.CodeLists.md)  
  * [Regulatory.Common.CodeEntries](Regulatory.Common.CodeEntries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Authority](Regulatory.Common.CodeLists.md#authority) | string (128) __nullable__ | Issuing or controlling authority (agency, institution).[Filter(eq;like)] 
| [Description](Regulatory.Common.CodeLists.md#description) | string (254) __nullable__ | Short description of the list’s purpose or scope.[Filter(eq;like)] 
| [EntityTypeName](Regulatory.Common.CodeLists.md#entitytypename) | string (128) __nullable__ | Internal system entity type mapped to entries in this list.[Filter(eq;like)] 
| [IsActive](Regulatory.Common.CodeLists.md#isactive) | boolean | Specifies whether the list version is currently active.[Required] [Default(true)] [Filter(eq)] 
| [LegalReference](Regulatory.Common.CodeLists.md#legalreference) | string (254) __nullable__ | Reference to the legal basis (law, article, ordinance, URL, file).[Filter(eq;like)] 
| [ListCode](Regulatory.Common.CodeLists.md#listcode) | string (16) | Regulatory code of the list, unique within the jurisdiction[Required] [Filter(eq;like)] 
| [ListName](Regulatory.Common.CodeLists.md#listname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Official regulatory name of the list (multi-language).[Required] [Filter(like)] 
| [Notes](Regulatory.Common.CodeLists.md#notes) | string (max) __nullable__ | Additional notes or comments 
| [ValidFrom](Regulatory.Common.CodeLists.md#validfrom) | date __nullable__ | When not null specifies the first date when the list is valid.[Filter(eq;ge;le)] 
| [ValidTo](Regulatory.Common.CodeLists.md#validto) | date __nullable__ | When not null specifies the last date (inclusive) when the list is valid.[Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Jurisdiction](Regulatory.Common.CodeLists.md#jurisdiction) | [Jurisdictions](Regulatory.Common.Jurisdictions.md) | The jurisdiction to which the list belongs. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Common.CodeLists.md#id) | guid |  
| [ObjectVersion](Regulatory.Common.CodeLists.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Common.CodeLists.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Common.CodeLists.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Common.CodeLists.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Common.CodeLists.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| CodeEntries | [CodeEntries](Regulatory.Common.CodeEntries.md) | List of `CodeEntry`(Regulatory.Common.CodeEntries.md) child objects, based on the `Regulatory.Common.CodeEntry.CodeList`(Regulatory.Common.CodeEntries.md#codelist) back reference 


## Attribute Details

### Authority

Issuing or controlling authority (agency, institution).[Filter(eq;like)]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Description

Short description of the list’s purpose or scope.[Filter(eq;like)]

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### EntityTypeName

Internal system entity type mapped to entries in this list.[Filter(eq;like)]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the list version is currently active.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### LegalReference

Reference to the legal basis (law, article, ordinance, URL, file).[Filter(eq;like)]

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListCode

Regulatory code of the list, unique within the jurisdiction[Required] [Filter(eq;like)]

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### ListName

Official regulatory name of the list (multi-language).[Required] [Filter(like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Additional notes or comments

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ValidFrom

When not null specifies the first date when the list is valid.[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidTo

When not null specifies the last date (inclusive) when the list is valid.[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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


## Reference Details

### Jurisdiction

The jurisdiction to which the list belongs.

Type: **[Jurisdictions](Regulatory.Common.Jurisdictions.md)**  
Indexed: **True**  
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

