---
uid: Regulatory.Common.CodeEntries
---
# Regulatory.Common.CodeEntries


Represents individual regulatory entries (codes) within a regulatory list, including validity periods and hierarchical relations.

## General
Namespace: [Regulatory.Common](Regulatory.Common.md)  
Repository: Regulatory.Common.CodeEntries  
Base Table: Reg_Code_Entries  
Introduced In Version: 26.2.0.62  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Common.CodeLists](Regulatory.Common.CodeLists.md)  
Aggregate Root:  
[Regulatory.Common.CodeLists](Regulatory.Common.CodeLists.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AdditionalDataJson](Regulatory.Common.CodeEntries.md#additionaldatajson) | string (max) __nullable__ | Flexible JSON field for extended regulatory attributes.`Filter(eq;like)` 
| [AltCode](Regulatory.Common.CodeEntries.md#altcode) | string (64) __nullable__ | Optional alternative/legacy code used for backward compatibility.`Filter(eq;like)` 
| [Code](Regulatory.Common.CodeEntries.md#code) | string (64) | Official statutory code of the entry; may repeat across different validity periods.`Required` `Filter(eq;like)` 
| [Data1](Regulatory.Common.CodeEntries.md#data1) | string (64) __nullable__ | Additional structured attribute for regulatory-specific data.`Filter(eq;like)` 
| [Data2](Regulatory.Common.CodeEntries.md#data2) | string (64) __nullable__ | Additional structured attribute for regulatory-specific data.`Filter(eq;like)` 
| [Data3](Regulatory.Common.CodeEntries.md#data3) | string (64) __nullable__ | Additional structured attribute for regulatory-specific data.`Filter(eq;like)` 
| [IsActive](Regulatory.Common.CodeEntries.md#isactive) | boolean | Specifies whether the code entry is currently active.`Required` `Default(true)` `Filter(eq)` 
| [Name](Regulatory.Common.CodeEntries.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Official regulatory name of the entry (multi-language).`Filter(like)` 
| [Notes](Regulatory.Common.CodeEntries.md#notes) | string (max) __nullable__ | Free text notes or comments`Filter(eq;like)` 
| [ShortName](Regulatory.Common.CodeEntries.md#shortname) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | Abbreviated or short name of the entry, if such exists.`Filter(like)` 
| [ValidFrom](Regulatory.Common.CodeEntries.md#validfrom) | date __nullable__ | Date from which this entry is valid.`Filter(eq;ge;le)` 
| [ValidTo](Regulatory.Common.CodeEntries.md#validto) | date __nullable__ | Date until which this entry is valid.`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CodeList](Regulatory.Common.CodeEntries.md#codelist) | [CodeLists](Regulatory.Common.CodeLists.md) | Reference to the regulatory code list containing this entry. |
| [ParentEntry](Regulatory.Common.CodeEntries.md#parententry) | [CodeEntries](Regulatory.Common.CodeEntries.md) (nullable) | Reference to a parent entry for hierarchical lists (regions / subregions / groups). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Common.CodeEntries.md#id) | guid |  
| [ObjectVersion](Regulatory.Common.CodeEntries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Common.CodeEntries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AdditionalDataJson

Flexible JSON field for extended regulatory attributes.`Filter(eq;like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### AltCode

Optional alternative/legacy code used for backward compatibility.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Code

Official statutory code of the entry; may repeat across different validity periods.`Required` `Filter(eq;like)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Data1

Additional structured attribute for regulatory-specific data.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Data2

Additional structured attribute for regulatory-specific data.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Data3

Additional structured attribute for regulatory-specific data.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the code entry is currently active.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Official regulatory name of the entry (multi-language).`Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Free text notes or comments`Filter(eq;like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ShortName

Abbreviated or short name of the entry, if such exists.`Filter(like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidFrom

Date from which this entry is valid.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidTo

Date until which this entry is valid.`Filter(eq;ge;le)`

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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### CodeList

Reference to the regulatory code list containing this entry.

Type: **[CodeLists](Regulatory.Common.CodeLists.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ParentEntry

Reference to a parent entry for hierarchical lists (regions / subregions / groups).

Type: **[CodeEntries](Regulatory.Common.CodeEntries.md) (nullable)**  
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

[!list limit=1000 erp.entity=Regulatory.Common.CodeEntries erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Common.CodeEntries erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Common_CodeEntries

Domain API Entity Type: 
Regulatory_Common_CodeEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Common_CodeEntries?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Common_CodeEntries?$top=10>

