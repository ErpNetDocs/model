---
uid: Projects.Agile.CaseDevelopments
---
# Projects.Agile.CaseDevelopments Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Case Development. Entity: Apm_Case_Developments (Introduced in version 24.1.3.81)

## Default Visualization
Default Display Text Format:  
_{CreationTimeUtc} {ActionDescription} by {CreationUser}_  
Default Search Members:  
_Case.Title_  
Name Data Member:  
_Case.Title_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Agile.Cases](Projects.Agile.Cases.md)  
Aggregate Root:  
[Projects.Agile.Cases](Projects.Agile.Cases.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActionDescription](Projects.Agile.CaseDevelopments.md#actiondescription) | string | Specifies the latest action, dependent on DevelopmentType. 
| [CreationTimeUtc](Projects.Agile.CaseDevelopments.md#creationtimeutc) | datetime | The exact date and time (in UTC) when the development was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` 
| [Description](Projects.Agile.CaseDevelopments.md#description) | string (max) __nullable__ | Detailed description of the development. `Filter(like)` 
| [DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype) | [DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype) | Type of the development - Edit, Assignment, Resolve, etc. `Required` `Default("EDT")` `Filter(multi eq)` `ReadOnly` 
| [DisplayText](Projects.Agile.CaseDevelopments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.Agile.CaseDevelopments.md#id) | guid |  
| [NewSystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) | [SystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) __nullable__ | When the development incurred changing the state of the case, contains the new state. `Filter(multi eq)` `ReadOnly` 
| [ObjectVersion](Projects.Agile.CaseDevelopments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.Agile.CaseDevelopments.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | When the development incurred re-assignment, specifies the new user, to which the case is assigned. `Filter(multi eq)` `ReadOnly` |
| [Case](Projects.Agile.CaseDevelopments.md#case) | [Cases](Projects.Agile.Cases.md) | The case of the case development. `Required` `Filter(multi eq)` `Owner` |
| [CreationUser](Projects.Agile.CaseDevelopments.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the development. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### ActionDescription

Specifies the latest action, dependent on DevelopmentType.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the development was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Description

Detailed description of the development. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### DevelopmentType

Type of the development - Edit, Assignment, Resolve, etc. `Required` `Default("EDT")` `Filter(multi eq)` `ReadOnly`

_Type_: **[DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype)**  
_Category_: **System**  
Allowed values for the `DevelopmentType`(Projects.Agile.CaseDevelopments.md#developmenttype) data attribute  
_Allowed Values (Projects.Agile.CaseDevelopmentsRepository.DevelopmentType Enum Members)_  

| Value | Description |
| ---- | --- |
| Edit | Edit. Stored as 'EDT'. <br /> _Database Value:_ 'EDT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Edit' |
| Assignment | Assignment . Stored as 'ASN'. <br /> _Database Value:_ 'ASN' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Assignment' |
| ChangeState | Change state. Stored as 'STA'. <br /> _Database Value:_ 'STA' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ChangeState' |
| AssignmentH | Assignment. Stored as 'ASH'. <br /> _Database Value:_ 'ASH' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'AssignmentH' |
| ChangeStateH | Change state. Stored as 'STH'. <br /> _Database Value:_ 'STH' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'ChangeStateH' |
| Create | Create. Stored as 'CRT'. <br /> _Database Value:_ 'CRT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Create' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Edit**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### NewSystemState

When the development incurred changing the state of the case, contains the new state. `Filter(multi eq)` `ReadOnly`

_Type_: **[SystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) __nullable__**  
_Category_: **System**  
Allowed values for the `SystemState`(Projects.Agile.Cases.md#systemstate) data attribute  
_Allowed Values (Projects.Agile.CasesRepository.SystemState Enum Members)_  

| Value | Description |
| ---- | --- |
| BACKLOG | The case is registered but not yet considered for work.. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'BACKLOG' |
| CONSIDER | The case is under evaluation for possible execution.. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CONSIDER' |
| READY | The case is approved and ready to be started.. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'READY' |
| INPROGRESS | Work on the case is currently ongoing.. Stored as '4'. <br /> _Database Value:_ '4' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'INPROGRESS' |
| WAITING | The case is paused, waiting for input or conditions.. Stored as '5'. <br /> _Database Value:_ '5' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'WAITING' |
| RESOLVED | Work is completed; final review or confirmation may be pending.. Stored as '6'. <br /> _Database Value:_ '6' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'RESOLVED' |
| CLOSED | The case is finalized and officially closed.. Stored as '7'. <br /> _Database Value:_ '7' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'CLOSED' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### AssignedToUser

When the development incurred re-assignment, specifies the new user, to which the case is assigned. `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Case

The case of the case development. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Cases](Projects.Agile.Cases.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### CreationUser

The user, who created the development. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Projects.Agile.CaseDevelopments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.CaseDevelopments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_CaseDevelopments

Domain API Entity Type: 
Projects_Agile_CaseDevelopment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_CaseDevelopments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_CaseDevelopments?$top=10>

