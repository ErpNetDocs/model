---
uid: Projects.Procedures.OperationalProcedures
---
# Projects.Procedures.OperationalProcedures Entity

**Namespace:** [Projects.Procedures](Projects.Procedures.md)  

Master record for an operational procedure (“how work is done”). Entity: Op_Operational_Procedures (Introduced in version 26.2.0.99)

## Default Visualization
Default Display Text Format:  
_{Code}_  
Default Search Members:  
_Code_  
Code Data Member:  
_Code_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Procedures.OperationalProcedures](Projects.Procedures.OperationalProcedures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Projects.Procedures.OperationalProcedures.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](Projects.Procedures.OperationalProcedures.md#code) | string (32) | Short unique code for search/reference. `Required` `Filter(eq;like)` `ORD` 
| [ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat) | [ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat) | Storage format of the content. `Required` `Default("MKD")` `Filter(eq)` 
| [CreationTimeUtc](Projects.Procedures.OperationalProcedures.md#creationtimeutc) | datetime | The exact date and time (in UTC) when the procedure was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [DisplayText](Projects.Procedures.OperationalProcedures.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityType](Projects.Procedures.OperationalProcedures.md#entitytype) | string (128) __nullable__ | Name of entity to which the procedure applies. `Filter(eq)` 
| [ExternalId](Projects.Procedures.OperationalProcedures.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Procedures.OperationalProcedures.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Procedures.OperationalProcedures.md#id) | guid |  
| [LastUpdateTimeUtc](Projects.Procedures.OperationalProcedures.md#lastupdatetimeutc) | datetime | The exact date and time (in UTC) when the procedure was last updated. `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Notes](Projects.Procedures.OperationalProcedures.md#notes) | string (max) __nullable__ | Notes for the procedure. `Filter(like)` 
| [ObjectVersion](Projects.Procedures.OperationalProcedures.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProcedureContent](Projects.Procedures.OperationalProcedures.md#procedurecontent) | string (max) __nullable__ | The content of the procedure. `Filter(like)` 
| [Status](Projects.Procedures.OperationalProcedures.md#status) | [Status](Projects.Procedures.OperationalProcedures.md#status) | Lifecycle state (Draft/Active/Obsolete). `Required` `Default("DRF")` `Filter(multi eq)` 
| [Title](Projects.Procedures.OperationalProcedures.md#title) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Procedure name. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Projects.Procedures.OperationalProcedures.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | The access key, containing the user permissions for this Operational Procedure. `Required` `Filter(multi eq)` |
| [OwnerRole](Projects.Procedures.OperationalProcedures.md#ownerrole) | [Roles](Systems.Security.Roles.md) (nullable) | Responsible role (content owner). `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Code

Short unique code for search/reference. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### ContentFormat

Storage format of the content. `Required` `Default("MKD")` `Filter(eq)`

_Type_: **[ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat)**  
_Category_: **System**  
Allowed values for the `ContentFormat`(Projects.Procedures.OperationalProcedures.md#contentformat) data attribute  
_Allowed Values (Projects.Procedures.OperationalProceduresRepository.ContentFormat Enum Members)_  

| Value | Description |
| ---- | --- |
| MarkDown | MarkDown. Stored as 'MKD'. <br /> _Database Value:_ 'MKD' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'MarkDown' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **MarkDown**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the procedure was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityType

Name of entity to which the procedure applies. `Filter(eq)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
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

### LastUpdateTimeUtc

The exact date and time (in UTC) when the procedure was last updated. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the procedure. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### ProcedureContent

The content of the procedure. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Status

Lifecycle state (Draft/Active/Obsolete). `Required` `Default("DRF")` `Filter(multi eq)`

_Type_: **[Status](Projects.Procedures.OperationalProcedures.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Projects.Procedures.OperationalProcedures.md#status) data attribute  
_Allowed Values (Projects.Procedures.OperationalProceduresRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| DRAFT | Draft. Stored as 'DRF'. <br /> _Database Value:_ 'DRF' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DRAFT' |
| ACTIVE | Active. Stored as 'ACT'. <br /> _Database Value:_ 'ACT' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ACTIVE' |
| OBSOLETE | Obsolete. Stored as 'OBS'. <br /> _Database Value:_ 'OBS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'OBSOLETE' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **DRAFT**  
_Show in UI_: **ShownByDefault**  

### Title

Procedure name. `Required` `Filter(like)`

_Type_: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

The access key, containing the user permissions for this Operational Procedure. `Required` `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### OwnerRole

Responsible role (content owner). `Filter(multi eq)`

_Type_: **[Roles](Systems.Security.Roles.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedures erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedures erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Procedures_OperationalProcedures

Domain API Entity Type: 
Projects_Procedures_OperationalProcedure

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Procedures_OperationalProcedures?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Procedures_OperationalProcedures?$top=10>

