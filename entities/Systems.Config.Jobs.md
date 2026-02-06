---
uid: Systems.Config.Jobs
---
# Systems.Config.Jobs


The jobs, which are configured in the system.

## General
Namespace: [Systems.Config](Systems.Config.md)  
Repository: Systems.Config.Jobs  
Base Table: Sys_Jobs  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.Jobs  
New name: Systems.Config.Jobs  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.Jobs](Systems.Config.Jobs.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Systems.Config.Jobs.md#isactive) | boolean | Specifies whether the job is active and ready for running.[Required] [Default(true)] [Filter(eq)] 
| [JobConfigurations](Systems.Config.Jobs.md#jobconfigurations) | string (max) __nullable__ | The field specifies additional parameters for the execution of the Job in JSON format. NULL means that there are no specific parameters.[Filter(like)] [Introduced in version 25.1.3.15] 
| [JobType](Systems.Config.Jobs.md#jobtype) | [JobType](Systems.Config.Jobs.md#jobtype) | The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages.[Required] [Filter(multi eq)] 
| [Name](Systems.Config.Jobs.md#name) | string (254) | The name of the job.[Required] [Filter(eq;like)] [ORD] 
| [Notes](Systems.Config.Jobs.md#notes) | string (max) __nullable__ | Notes for this Job. 
| [RunOnIdle](Systems.Config.Jobs.md#runonidle) | boolean | Specifies whether to automatically run the job when the server is idle.[Required] [Default(true)] [Filter(eq)] 
| [Schedule](Systems.Config.Jobs.md#schedule) | [Schedule](Systems.Config.Jobs.md#schedule) | Defines the execution schedule of the Job.[Required] [Default(&quot;NON&quot;)] [Filter(multi eq)] [Introduced in version 26.1.4.62] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Config.Jobs.md#id) | guid |  
| [ObjectVersion](Systems.Config.Jobs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Config.Jobs.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.Jobs.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Config.Jobs.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.Jobs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

Specifies whether the job is active and ready for running.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### JobConfigurations

The field specifies additional parameters for the execution of the Job in JSON format. NULL means that there are no specific parameters.[Filter(like)] [Introduced in version 25.1.3.15]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### JobType

The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages.[Required] [Filter(multi eq)]

Type: **[JobType](Systems.Config.Jobs.md#jobtype)**  
Category: **System**  
Allowed values for the `JobType`(Systems.Config.Jobs.md#jobtype) data attribute  
Allowed Values (Systems.Config.JobsRepository.JobType Enum Members)  

| Value | Description |
| ---- | --- |
| DocumentChangeState | DocumentChangeState value. Stored as 'DOC'. <br /> Database Value: 'DOC' <br /> Model Value: 0 <br /> Domain API Value: 'DocumentChangeState' |
| RunPostponedEvents | RunPostponedEvents value. Stored as 'POS'. <br /> Database Value: 'POS' <br /> Model Value: 1 <br /> Domain API Value: 'RunPostponedEvents' |
| DeleteOldNotifications | DeleteOldNotifications value. Stored as 'DNT'. <br /> Database Value: 'DNT' <br /> Model Value: 2 <br /> Domain API Value: 'DeleteOldNotifications' |
| DeleteOldPrintImages | DeleteOldPrintImages value. Stored as 'DPI'. <br /> Database Value: 'DPI' <br /> Model Value: 3 <br /> Domain API Value: 'DeleteOldPrintImages' |
| DeleteOldDocumentVersions | Delete old document versions. Stored as 'DDV'. <br /> Database Value: 'DDV' <br /> Model Value: 4 <br /> Domain API Value: 'DeleteOldDocumentVersions' |
| DeleteOldInformation<br />Messages | Delete old information messages. Stored as 'DIM'. <br /> Database Value: 'DIM' <br /> Model Value: 5 <br /> Domain API Value: 'DeleteOldInformation<br />Messages' |
| DeleteAttribute<br />ChangesHistory | Delete attribute changes history. Stored as 'DAC'. <br /> Database Value: 'DAC' <br /> Model Value: 6 <br /> Domain API Value: 'DeleteAttribute<br />ChangesHistory' |
| DeleteOldAuditLogs | Delete Old Audit Logs. Stored as 'DAL'. <br /> Database Value: 'DAL' <br /> Model Value: 7 <br /> Domain API Value: 'DeleteOldAuditLogs' |
| CompleteUnfinished<br />TimeEntries | Complete Unfinished Time Entries. Stored as 'CTE'. <br /> Database Value: 'CTE' <br /> Model Value: 8 <br /> Domain API Value: 'CompleteUnfinished<br />TimeEntries' |
| CalculateReporting<br />CurrencyAmounts | Calculate historical Reporting currency amounts. Stored as 'CRC'. <br /> Database Value: 'CRC' <br /> Model Value: 9 <br /> Domain API Value: 'CalculateReporting<br />CurrencyAmounts' |
| InstanceChangesProcessor | InstanceChangesProcessor value. Stored as 'ICP'. <br /> Database Value: 'ICP' <br /> Model Value: 10 <br /> Domain API Value: 'InstanceChangesProcessor' |
| DeleteExpiredAccessTokens | DeleteExpiredAccessTokens value. Stored as 'DRT'. <br /> Database Value: 'DRT' <br /> Model Value: 11 <br /> Domain API Value: 'DeleteExpiredAccessTokens' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of the job.[Required] [Filter(eq;like)] [ORD]

Type: **string (254)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Job.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RunOnIdle

Specifies whether to automatically run the job when the server is idle.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Schedule

Defines the execution schedule of the Job.[Required] [Default(&quot;NON&quot;)] [Filter(multi eq)] [Introduced in version 26.1.4.62]

Type: **[Schedule](Systems.Config.Jobs.md#schedule)**  
Category: **System**  
Allowed values for the `Schedule`(Systems.Config.Jobs.md#schedule) data attribute  
Allowed Values (Systems.Config.JobsRepository.Schedule Enum Members)  

| Value | Description |
| ---- | --- |
| None | No schedule - not executed automatically (only manually).. Stored as 'NON'. <br /> Database Value: 'NON' <br /> Model Value: 0 <br /> Domain API Value: 'None' |
| Night | Executed only during night time.. Stored as 'NGH'. <br /> Database Value: 'NGH' <br /> Model Value: 1 <br /> Domain API Value: 'Night' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **None**  
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

