---
uid: Systems.Config.Jobs
---
# Systems.Config.Jobs Entity

**Namespace:** [Systems.Config](Systems.Config.md)  

The jobs, which are configured in the system. Entity: Sys_Jobs (Introduced in version 20.1)

## Renames

Old name: **Systems.Core.Jobs**  
New name: **Systems.Config.Jobs**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
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
* [Systems.Config.Jobs](Systems.Config.Jobs.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Config.Jobs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Config.Jobs.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.Jobs.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Config.Jobs.md#id) | guid |  
| [IsActive](Systems.Config.Jobs.md#isactive) | boolean | Specifies whether the job is active and ready for running. `Required` `Default(true)` `Filter(eq)` 
| [JobConfigurations](Systems.Config.Jobs.md#jobconfigurations) | string (max) __nullable__ | The field specifies additional parameters for the execution of the Job in JSON format. null means that there are no specific parameters. `Filter(like)` `Introduced in version 25.1.3.15` 
| [JobType](Systems.Config.Jobs.md#jobtype) | [JobType](Systems.Config.Jobs.md#jobtype) | The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages. `Required` `Filter(multi eq)` 
| [Name](Systems.Config.Jobs.md#name) | string (254) | The name of the job. `Required` `Filter(eq;like)` `ORD` 
| [Notes](Systems.Config.Jobs.md#notes) | string (max) __nullable__ | Notes for this Job. 
| [ObjectVersion](Systems.Config.Jobs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RunOnIdle](Systems.Config.Jobs.md#runonidle) | boolean | Specifies whether to automatically run the job when the server is idle. `Required` `Default(true)` `Filter(eq)` 
| [Schedule](Systems.Config.Jobs.md#schedule) | [Schedule](Systems.Config.Jobs.md#schedule) | Defines the execution schedule of the Job. `Required` `Default("NON")` `Filter(multi eq)` `Introduced in version 26.1.4.62` 


## Attribute Details

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

### IsActive

Specifies whether the job is active and ready for running. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### JobConfigurations

The field specifies additional parameters for the execution of the Job in JSON format. null means that there are no specific parameters. `Filter(like)` `Introduced in version 25.1.3.15`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### JobType

The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages. `Required` `Filter(multi eq)`

_Type_: **[JobType](Systems.Config.Jobs.md#jobtype)**  
_Category_: **System**  
Allowed values for the `JobType`(Systems.Config.Jobs.md#jobtype) data attribute  
_Allowed Values (Systems.Config.JobsRepository.JobType Enum Members)_  

| Value | Description |
| ---- | --- |
| DocumentChangeState | DocumentChangeState value. Stored as 'DOC'. <br /> _Database Value:_ 'DOC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DocumentChangeState' |
| RunPostponedEvents | RunPostponedEvents value. Stored as 'POS'. <br /> _Database Value:_ 'POS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'RunPostponedEvents' |
| DeleteOldNotifications | DeleteOldNotifications value. Stored as 'DNT'. <br /> _Database Value:_ 'DNT' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'DeleteOldNotifications' |
| DeleteOldPrintImages | DeleteOldPrintImages value. Stored as 'DPI'. <br /> _Database Value:_ 'DPI' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'DeleteOldPrintImages' |
| DeleteOldDocumentVersions | Delete old document versions. Stored as 'DDV'. <br /> _Database Value:_ 'DDV' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'DeleteOldDocumentVersions' |
| DeleteOldInformation<br />Messages | Delete old information messages. Stored as 'DIM'. <br /> _Database Value:_ 'DIM' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'DeleteOldInformation<br />Messages' |
| DeleteAttribute<br />ChangesHistory | Delete attribute changes history. Stored as 'DAC'. <br /> _Database Value:_ 'DAC' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'DeleteAttribute<br />ChangesHistory' |
| DeleteOldAuditLogs | Delete Old Audit Logs. Stored as 'DAL'. <br /> _Database Value:_ 'DAL' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'DeleteOldAuditLogs' |
| CompleteUnfinished<br />TimeEntries | Complete Unfinished Time Entries. Stored as 'CTE'. <br /> _Database Value:_ 'CTE' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'CompleteUnfinished<br />TimeEntries' |
| CalculateReporting<br />CurrencyAmounts | Calculate historical Reporting currency amounts. Stored as 'CRC'. <br /> _Database Value:_ 'CRC' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'CalculateReporting<br />CurrencyAmounts' |
| InstanceChangesProcessor | InstanceChangesProcessor value. Stored as 'ICP'. <br /> _Database Value:_ 'ICP' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'InstanceChangesProcessor' |
| DeleteExpiredAccessTokens | DeleteExpiredAccessTokens value. Stored as 'DRT'. <br /> _Database Value:_ 'DRT' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'DeleteExpiredAccessTokens' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The name of the job. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (254)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Job.

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

### RunOnIdle

Specifies whether to automatically run the job when the server is idle. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Schedule

Defines the execution schedule of the Job. `Required` `Default("NON")` `Filter(multi eq)` `Introduced in version 26.1.4.62`

_Type_: **[Schedule](Systems.Config.Jobs.md#schedule)**  
_Category_: **System**  
Allowed values for the `Schedule`(Systems.Config.Jobs.md#schedule) data attribute  
_Allowed Values (Systems.Config.JobsRepository.Schedule Enum Members)_  

| Value | Description |
| ---- | --- |
| None | No schedule - not executed automatically (only manually).. Stored as 'NON'. <br /> _Database Value:_ 'NON' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'None' |
| Night | Executed only during night time.. Stored as 'NGH'. <br /> _Database Value:_ 'NGH' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Night' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **None**  
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

[!list limit=1000 erp.entity=Systems.Config.Jobs erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Config.Jobs erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Config_Jobs

Domain API Entity Type: 
Systems_Config_Job

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Config_Jobs?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Config_Jobs?$top=10>

