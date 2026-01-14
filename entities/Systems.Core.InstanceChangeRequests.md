---
uid: Systems.Core.InstanceChangeRequests
---
# Systems.Core.InstanceChangeRequests Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Major changes to enterprise companies (like base or reporting currency change). Entity: Sys_Instance_Change_Requests (Introduced in version 26.1.4.40)

## Default Visualization
Default Display Text Format:  
_{RequestNo}: {ChangeKind}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.InstanceChangeRequests](Systems.Core.InstanceChangeRequests.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Systems.Core.InstanceChangeRequests.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind) | [ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind) | The type of change requested for the enterprise company. `Required` `Filter(multi eq)` 
| [CurrencyRate](Systems.Core.InstanceChangeRequests.md#currencyrate) | decimal (20, 10) __nullable__ | Currency Rate, applied for the change when relevant (e.g. reporting or base currency change). Used to fix the conversion rate at the time of change execution. `Filter(eq)` `Introduced in version 26.1.4.51` 
| [DisplayText](Systems.Core.InstanceChangeRequests.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EffectiveDate](Systems.Core.InstanceChangeRequests.md#effectivedate) | date | The date from which the change is effective. Might differ from execution date. `Required` `Filter(eq;ge;le)` 
| [ExecutionDate](Systems.Core.InstanceChangeRequests.md#executiondate) | date | The date on which the change should be initiated. `Required` `Filter(eq;ge;le)` 
| [ExternalId](Systems.Core.InstanceChangeRequests.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.InstanceChangeRequests.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Core.InstanceChangeRequests.md#id) | guid |  
| [Notes](Systems.Core.InstanceChangeRequests.md#notes) | string (max) __nullable__ | Notes. `Filter(like)` 
| [ObjectVersion](Systems.Core.InstanceChangeRequests.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProgressDate](Systems.Core.InstanceChangeRequests.md#progressdate) | date __nullable__ | The date up to which the data is updated in the database. Updated by the batch job. `Filter(eq;ge;le)` 
| [ProgressPercent](Systems.Core.InstanceChangeRequests.md#progresspercent) | decimal (5, 2) __nullable__ | Progress, updated by the batch job. `Filter(ge;le)` 
| [ReferenceNo](Systems.Core.InstanceChangeRequests.md#referenceno) | string (32) __nullable__ | Text for internal reference of the change request. `Filter(eq)` 
| [RequestNo](Systems.Core.InstanceChangeRequests.md#requestno) | int32 | Global consequtive request number. `Required` `Filter(eq)` `ORD` 
| [SettingsJson](Systems.Core.InstanceChangeRequests.md#settingsjson) | string (max) __nullable__ | Additional settings for the change; expressed in Json. The format depends on the change kind. `Filter(like)` 
| [State](Systems.Core.InstanceChangeRequests.md#state) | [State](Systems.Core.InstanceChangeRequests.md#state) | Current state of the request. `Required` `Default("DRF")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Systems.Core.InstanceChangeRequests.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | The user, to which it is assigned. `Filter(multi eq)` |
| [EnterpriseCompany](Systems.Core.InstanceChangeRequests.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company being changed. Null means that the change is for the whole instance. `Filter(multi eq)` |
| [NewValueCurrency](Systems.Core.InstanceChangeRequests.md#newvaluecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | New value, when the change is for currency. `Filter(multi eq)` |
| [OldValueCurrency](Systems.Core.InstanceChangeRequests.md#oldvaluecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Old value, when the change is for currency. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ChangeKind

The type of change requested for the enterprise company. `Required` `Filter(multi eq)`

_Type_: **[ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind)**  
_Category_: **System**  
Allowed values for the `ChangeKind`(Systems.Core.InstanceChangeRequests.md#changekind) data attribute  
_Allowed Values (Systems.Core.InstanceChangeRequestsRepository.ChangeKind Enum Members)_  

| Value | Description |
| ---- | --- |
| ReportingCurrencyChange | Reporting Currency Change. Stored as 'REP'. <br /> _Database Value:_ 'REP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ReportingCurrencyChange' |
| BaseCurrencyChange | Base Currency Change. Stored as 'BAS'. <br /> _Database Value:_ 'BAS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BaseCurrencyChange' |
| CurrencyOfDefaultsChange | Currency of Defaults Change. Stored as 'DEF'. <br /> _Database Value:_ 'DEF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'CurrencyOfDefaultsChange' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CurrencyRate

Currency Rate, applied for the change when relevant (e.g. reporting or base currency change). Used to fix the conversion rate at the time of change execution. `Filter(eq)` `Introduced in version 26.1.4.51`

_Type_: **decimal (20, 10) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EffectiveDate

The date from which the change is effective. Might differ from execution date. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExecutionDate

The date on which the change should be initiated. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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

### Notes

Notes. `Filter(like)`

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

### ProgressDate

The date up to which the data is updated in the database. Updated by the batch job. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProgressPercent

Progress, updated by the batch job. `Filter(ge;le)`

_Type_: **decimal (5, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ReferenceNo

Text for internal reference of the change request. `Filter(eq)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### RequestNo

Global consequtive request number. `Required` `Filter(eq)` `ORD`

_Type_: **int32**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### SettingsJson

Additional settings for the change; expressed in Json. The format depends on the change kind. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### State

Current state of the request. `Required` `Default("DRF")` `Filter(eq)`

_Type_: **[State](Systems.Core.InstanceChangeRequests.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Systems.Core.InstanceChangeRequests.md#state) data attribute  
_Allowed Values (Systems.Core.InstanceChangeRequestsRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| Draft | Draft. Stored as 'DRF'. <br /> _Database Value:_ 'DRF' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Draft' |
| Submitted | Submitted. Stored as 'SUB'. <br /> _Database Value:_ 'SUB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Submitted' |
| Approved | Approved. Stored as 'APR'. <br /> _Database Value:_ 'APR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Approved' |
| PreparationsNeeded | Preparations Needed. Stored as 'PRN'. <br /> _Database Value:_ 'PRN' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'PreparationsNeeded' |
| PreparationsCompleted | Preparations Completed. Stored as 'PRP'. <br /> _Database Value:_ 'PRP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'PreparationsCompleted' |
| Scheduled | Scheduled. Stored as 'SCH'. <br /> _Database Value:_ 'SCH' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Scheduled' |
| InProgress | In Progress. Stored as 'INP'. <br /> _Database Value:_ 'INP' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'InProgress' |
| Paused | Paused. Stored as 'PAU'. <br /> _Database Value:_ 'PAU' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Paused' |
| CompletedSuccessfully | Completed Successfully. Stored as 'CMP'. <br /> _Database Value:_ 'CMP' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'CompletedSuccessfully' |
| Cancelled | Cancelled. Stored as 'CNC'. <br /> _Database Value:_ 'CNC' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'Cancelled' |
| Failed | Failed. Stored as 'FLD'. <br /> _Database Value:_ 'FLD' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Failed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Draft**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AssignedToUser

The user, to which it is assigned. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company being changed. Null means that the change is for the whole instance. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### NewValueCurrency

New value, when the change is for currency. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OldValueCurrency

Old value, when the change is for currency. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Core.InstanceChangeRequests erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.InstanceChangeRequests erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_InstanceChangeRequests

Domain API Entity Type: 
Systems_Core_InstanceChangeRequest

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_InstanceChangeRequests?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_InstanceChangeRequests?$top=10>

