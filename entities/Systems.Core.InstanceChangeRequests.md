---
uid: Systems.Core.InstanceChangeRequests
---
# Systems.Core.InstanceChangeRequests


Major changes to enterprise companies (like base or reporting currency change).

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.InstanceChangeRequests  
Base Table: Sys_Instance_Change_Requests  
Introduced In Version: 26.1.4.40  
API access:  ReadWrite  

## Visualization
Display Format: {RequestNo}: {ChangeKind}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.InstanceChangeRequests](Systems.Core.InstanceChangeRequests.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind) | [ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind) | The type of change requested for the enterprise company.`Required` `Filter(multi eq)` 
| [CurrencyRate](Systems.Core.InstanceChangeRequests.md#currencyrate) | decimal (20, 10) __nullable__ | Currency Rate, applied for the change when relevant (e.g. reporting or base currency change). Used to fix the conversion rate at the time of change execution.`Filter(eq)` `Introduced in version 26.1.4.51` 
| [EffectiveDate](Systems.Core.InstanceChangeRequests.md#effectivedate) | date | The date from which the change is effective. Might differ from execution date.`Required` `Filter(eq;ge;le)` 
| [ExecutionDate](Systems.Core.InstanceChangeRequests.md#executiondate) | date | The date on which the change should be initiated.`Required` `Filter(eq;ge;le)` 
| [Notes](Systems.Core.InstanceChangeRequests.md#notes) | string (max) __nullable__ | Notes`Filter(like)` 
| [ProgressDate](Systems.Core.InstanceChangeRequests.md#progressdate) | date __nullable__ | The date up to which the data is updated in the database. Updated by the batch job.`Filter(eq;ge;le)` 
| [ProgressPercent](Systems.Core.InstanceChangeRequests.md#progresspercent) | decimal (5, 2) __nullable__ | Progress, updated by the batch job.`Filter(ge;le)` 
| [ReferenceNo](Systems.Core.InstanceChangeRequests.md#referenceno) | string (32) __nullable__ | Text for internal reference of the change request.`Filter(eq)` 
| [RequestNo](Systems.Core.InstanceChangeRequests.md#requestno) | int32 | Global consequtive request number.`Required` `Filter(eq)` `ORD` 
| [SettingsJson](Systems.Core.InstanceChangeRequests.md#settingsjson) | string (max) __nullable__ | Additional settings for the change; expressed in Json. The format depends on the change kind`Filter(like)` 
| [State](Systems.Core.InstanceChangeRequests.md#state) | [State](Systems.Core.InstanceChangeRequests.md#state) | Current state of the request.`Required` `Default(&quot;DRF&quot;)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Systems.Core.InstanceChangeRequests.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | The user, to which it is assigned. |
| [EnterpriseCompany](Systems.Core.InstanceChangeRequests.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company being changed. Null means that the change is for the whole instance. |
| [NewValueCurrency](Systems.Core.InstanceChangeRequests.md#newvaluecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | New value, when the change is for currency. |
| [OldValueCurrency](Systems.Core.InstanceChangeRequests.md#oldvaluecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Old value, when the change is for currency. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.InstanceChangeRequests.md#id) | guid |  
| [ObjectVersion](Systems.Core.InstanceChangeRequests.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.InstanceChangeRequests.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.InstanceChangeRequests.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.InstanceChangeRequests.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.InstanceChangeRequests.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ChangeKind

The type of change requested for the enterprise company.`Required` `Filter(multi eq)`

Type: **[ChangeKind](Systems.Core.InstanceChangeRequests.md#changekind)**  
Category: **System**  
Allowed values for the `ChangeKind`(Systems.Core.InstanceChangeRequests.md#changekind) data attribute  
Allowed Values (Systems.Core.InstanceChangeRequestsRepository.ChangeKind Enum Members)  

| Value | Description |
| ---- | --- |
| ReportingCurrencyChange | Reporting Currency Change. Stored as 'REP'. <br /> Database Value: 'REP' <br /> Model Value: 0 <br /> Domain API Value: 'ReportingCurrencyChange' |
| BaseCurrencyChange | Base Currency Change. Stored as 'BAS'. <br /> Database Value: 'BAS' <br /> Model Value: 1 <br /> Domain API Value: 'BaseCurrencyChange' |
| CurrencyOfDefaultsChange | Currency of Defaults Change. Stored as 'DEF'. <br /> Database Value: 'DEF' <br /> Model Value: 2 <br /> Domain API Value: 'CurrencyOfDefaultsChange' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CurrencyRate

Currency Rate, applied for the change when relevant (e.g. reporting or base currency change). Used to fix the conversion rate at the time of change execution.`Filter(eq)` `Introduced in version 26.1.4.51`

Type: **decimal (20, 10) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EffectiveDate

The date from which the change is effective. Might differ from execution date.`Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionDate

The date on which the change should be initiated.`Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProgressDate

The date up to which the data is updated in the database. Updated by the batch job.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProgressPercent

Progress, updated by the batch job.`Filter(ge;le)`

Type: **decimal (5, 2) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReferenceNo

Text for internal reference of the change request.`Filter(eq)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### RequestNo

Global consequtive request number.`Required` `Filter(eq)` `ORD`

Type: **int32**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### SettingsJson

Additional settings for the change; expressed in Json. The format depends on the change kind`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### State

Current state of the request.`Required` `Default(&quot;DRF&quot;)` `Filter(eq)`

Type: **[State](Systems.Core.InstanceChangeRequests.md#state)**  
Category: **System**  
Allowed values for the `State`(Systems.Core.InstanceChangeRequests.md#state) data attribute  
Allowed Values (Systems.Core.InstanceChangeRequestsRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| Draft | Draft. Stored as 'DRF'. <br /> Database Value: 'DRF' <br /> Model Value: 0 <br /> Domain API Value: 'Draft' |
| Submitted | Submitted. Stored as 'SUB'. <br /> Database Value: 'SUB' <br /> Model Value: 1 <br /> Domain API Value: 'Submitted' |
| Approved | Approved. Stored as 'APR'. <br /> Database Value: 'APR' <br /> Model Value: 2 <br /> Domain API Value: 'Approved' |
| PreparationsNeeded | Preparations Needed. Stored as 'PRN'. <br /> Database Value: 'PRN' <br /> Model Value: 3 <br /> Domain API Value: 'PreparationsNeeded' |
| PreparationsCompleted | Preparations Completed. Stored as 'PRP'. <br /> Database Value: 'PRP' <br /> Model Value: 4 <br /> Domain API Value: 'PreparationsCompleted' |
| Scheduled | Scheduled. Stored as 'SCH'. <br /> Database Value: 'SCH' <br /> Model Value: 5 <br /> Domain API Value: 'Scheduled' |
| InProgress | In Progress. Stored as 'INP'. <br /> Database Value: 'INP' <br /> Model Value: 6 <br /> Domain API Value: 'InProgress' |
| Paused | Paused. Stored as 'PAU'. <br /> Database Value: 'PAU' <br /> Model Value: 7 <br /> Domain API Value: 'Paused' |
| CompletedSuccessfully | Completed Successfully. Stored as 'CMP'. <br /> Database Value: 'CMP' <br /> Model Value: 8 <br /> Domain API Value: 'CompletedSuccessfully' |
| Cancelled | Cancelled. Stored as 'CNC'. <br /> Database Value: 'CNC' <br /> Model Value: 9 <br /> Domain API Value: 'Cancelled' |
| Failed | Failed. Stored as 'FLD'. <br /> Database Value: 'FLD' <br /> Model Value: 10 <br /> Domain API Value: 'Failed' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Draft**  
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

### AssignedToUser

The user, to which it is assigned.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company being changed. Null means that the change is for the whole instance.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### NewValueCurrency

New value, when the change is for currency.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OldValueCurrency

Old value, when the change is for currency.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
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

