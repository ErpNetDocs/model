---
uid: Finance.Accounting.AccountGroups
---
# Finance.Accounting.AccountGroups


Hierarchical structure that organizes financial accounts into categories and subcategories. Account groups help define the overall layout and logic of the chart of accounts.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.AccountGroups  
Base Table: Acc_Account_Groups  
API access:  ReadWrite  

## Visualization
Display Format: {Number}: {Name:T}  
Search Members: Number; Name  
Code Member: Number  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.AccountGroups](Finance.Accounting.AccountGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Finance.Accounting.AccountGroups.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The description of this AccountGroup. 
| [Discontinued](Finance.Accounting.AccountGroups.md#discontinued) | boolean | 1 means that the account group won't be used any more and should not appear in combo boxes[Required] [Default(false)] [Filter(eq)] 
| [FullPath](Finance.Accounting.AccountGroups.md#fullpath) | string (256) __nullable__ | Full path to the group. Contains delimited list of group numbers of parent groups[Filter(like)] 
| [Name](Finance.Accounting.AccountGroups.md#name) | [MultilanguageString (160)](../data-types.md#multilanguagestring) | Account group name, required. Must be unique within the parent group[Required] [Filter(like)] 
| [Number](Finance.Accounting.AccountGroups.md#number) | string (30) | Unique account group number. May contain characters, if required[Required] [Filter(like)] [ORD] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Parent](Finance.Accounting.AccountGroups.md#parent) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Parent account group. null if this is root group. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.AccountGroups.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.AccountGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Accounting.AccountGroups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Accounting.AccountGroups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Accounting.AccountGroups.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Accounting.AccountGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Description

The description of this AccountGroup.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Discontinued

1 means that the account group won't be used any more and should not appear in combo boxes[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### FullPath

Full path to the group. Contains delimited list of group numbers of parent groups[Filter(like)]

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **CannotBeShown**  

### Name

Account group name, required. Must be unique within the parent group[Required] [Filter(like)]

Type: **[MultilanguageString (160)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Number

Unique account group number. May contain characters, if required[Required] [Filter(like)] [ORD]

Type: **string (30)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **True**  
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

### Parent

Parent account group. null if this is root group. `Filter(multi eq)`

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Accounting.AccountGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.AccountGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_AccountGroups

Domain API Entity Type: 
Finance_Accounting_AccountGroup

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_AccountGroups?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountGroups?$top=10>

