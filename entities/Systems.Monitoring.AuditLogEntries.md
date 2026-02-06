---
uid: Systems.Monitoring.AuditLogEntries
---
# Systems.Monitoring.AuditLogEntries


Information about the count and the size of audit log entries, grouped by application name, event class, entity name and event time.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.AuditLogEntries  
Base Table: Sys_Audit_Log_Entries  
Introduced In Version: 18.2  
API access:  ReadOnly  

## Renames

Old name: Systems.Core.AuditLogEntries  
New name: Systems.Monitoring.AuditLogEntries  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ApplicationName}  
Search Members: ApplicationName  
Name Member: ApplicationName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  0 - Do not track changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AuditLogEntries](Systems.Monitoring.AuditLogEntries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.AuditLogEntries.md#applicationname) | string (64) __nullable__ | The client application that triggered the events. Null when unknown or N/A.[Filter(eq;like)] 
| [Details](Systems.Monitoring.AuditLogEntries.md#details) | string (max) __nullable__ | Detailed contents of the event. Contents depend on the Event Type and Event Name. 
| [EntityItemId](Systems.Monitoring.AuditLogEntries.md#entityitemid) | guid __nullable__ | The Id of the record, which is referenced by the event. Null when unknown or N/A. `Filter(multi eq)` 
| [EntityName](Systems.Monitoring.AuditLogEntries.md#entityname) | string (64) __nullable__ | The entity, which is being referenced by the events. Null when unknown or N/A.[Filter(eq;like)] 
| [EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass) | [EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass) | The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events; P=Presence changes.[Required] [Filter(multi eq)] 
| [EventName](Systems.Monitoring.AuditLogEntries.md#eventname) | string (128) __nullable__ | Specific event or method name. Contents depend on the Event Type. Null when N/A.[Filter(eq;like)] 
| [EventTimeUtc](Systems.Monitoring.AuditLogEntries.md#eventtimeutc) | datetime | The exact date and time (in Utc) when the event occurred.[Required] [Default(Now)] [Filter(ge;le)] [ORD] 
| [EventType](Systems.Monitoring.AuditLogEntries.md#eventtype) | [EventType](Systems.Monitoring.AuditLogEntries.md#eventtype) | Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event; PSA=Change presence to Available; PSD=Change presence to DND; PSB=Change presence to Busy; PSW=Change presence to Away; PSO=Change presence to Offline.[Required] [Filter(multi eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PersonalDataProcess](Systems.Monitoring.AuditLogEntries.md#personaldataprocess) | [PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable) | The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A. |
| [User](Systems.Monitoring.AuditLogEntries.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user account under which the event has occurred. Null only for events which are not user-specific. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Monitoring.AuditLogEntries.md#id) | guid |  
| [ObjectVersion](Systems.Monitoring.AuditLogEntries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Monitoring.AuditLogEntries.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.AuditLogEntries.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Monitoring.AuditLogEntries.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Monitoring.AuditLogEntries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplicationName

The client application that triggered the events. Null when unknown or N/A.[Filter(eq;like)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Details

Detailed contents of the event. Contents depend on the Event Type and Event Name.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### EntityItemId

The Id of the record, which is referenced by the event. Null when unknown or N/A. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EntityName

The entity, which is being referenced by the events. Null when unknown or N/A.[Filter(eq;like)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### EventClass

The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events; P=Presence changes.[Required] [Filter(multi eq)]

Type: **[EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass)**  
Category: **System**  
Allowed values for the `EventClass`(Systems.Monitoring.AuditLogEntries.md#eventclass) data attribute  
Allowed Values (Systems.Monitoring.AuditLogEntriesRepository.EventClass Enum Members)  

| Value | Description |
| ---- | --- |
| Entity | Entity value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 0 <br /> Domain API Value: 'Entity' |
| Authentication | Authentication value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 1 <br /> Domain API Value: 'Authentication' |
| Server | Server value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 2 <br /> Domain API Value: 'Server' |
| Presence | Presence value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 3 <br /> Domain API Value: 'Presence' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EventName

Specific event or method name. Contents depend on the Event Type. Null when N/A.[Filter(eq;like)]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### EventTimeUtc

The exact date and time (in Utc) when the event occurred.[Required] [Default(Now)] [Filter(ge;le)] [ORD]

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### EventType

Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event; PSA=Change presence to Available; PSD=Change presence to DND; PSB=Change presence to Busy; PSW=Change presence to Away; PSO=Change presence to Offline.[Required] [Filter(multi eq)]

Type: **[EventType](Systems.Monitoring.AuditLogEntries.md#eventtype)**  
Category: **System**  
Allowed values for the `EventType`(Systems.Monitoring.AuditLogEntries.md#eventtype) data attribute  
Allowed Values (Systems.Monitoring.AuditLogEntriesRepository.EventType Enum Members)  

| Value | Description |
| ---- | --- |
| ReadOneRecordById | ReadOneRecordById value. Stored as 'EID'. <br /> Database Value: 'EID' <br /> Model Value: 0 <br /> Domain API Value: 'ReadOneRecordById' |
| LoadManyRecords | LoadManyRecords value. Stored as 'ELD'. <br /> Database Value: 'ELD' <br /> Model Value: 1 <br /> Domain API Value: 'LoadManyRecords' |
| CreateRecord | CreateRecord value. Stored as 'ECR'. <br /> Database Value: 'ECR' <br /> Model Value: 2 <br /> Domain API Value: 'CreateRecord' |
| UpdateData | UpdateData value. Stored as 'EUP'. <br /> Database Value: 'EUP' <br /> Model Value: 3 <br /> Domain API Value: 'UpdateData' |
| DeleteRecord | DeleteRecord value. Stored as 'EDE'. <br /> Database Value: 'EDE' <br /> Model Value: 4 <br /> Domain API Value: 'DeleteRecord' |
| CallMethod | CallMethod value. Stored as 'EMT'. <br /> Database Value: 'EMT' <br /> Model Value: 5 <br /> Domain API Value: 'CallMethod' |
| OtherEntityEvent | OtherEntityEvent value. Stored as 'ETH'. <br /> Database Value: 'ETH' <br /> Model Value: 6 <br /> Domain API Value: 'OtherEntityEvent' |
| Login | Login value. Stored as 'AIN'. <br /> Database Value: 'AIN' <br /> Model Value: 7 <br /> Domain API Value: 'Login' |
| LogOut | LogOut value. Stored as 'AOU'. <br /> Database Value: 'AOU' <br /> Model Value: 8 <br /> Domain API Value: 'LogOut' |
| SignUp | SignUp value. Stored as 'AUP'. <br /> Database Value: 'AUP' <br /> Model Value: 9 <br /> Domain API Value: 'SignUp' |
| LoginFailed | LoginFailed value. Stored as 'AFL'. <br /> Database Value: 'AFL' <br /> Model Value: 10 <br /> Domain API Value: 'LoginFailed' |
| ChangePassword | ChangePassword value. Stored as 'APW'. <br /> Database Value: 'APW' <br /> Model Value: 11 <br /> Domain API Value: 'ChangePassword' |
| OtherAuthEvent | OtherAuthEvent value. Stored as 'ATH'. <br /> Database Value: 'ATH' <br /> Model Value: 12 <br /> Domain API Value: 'OtherAuthEvent' |
| OtherServerEvent | OtherServerEvent value. Stored as 'STH'. <br /> Database Value: 'STH' <br /> Model Value: 13 <br /> Domain API Value: 'OtherServerEvent' |
| AuthPresenceChange | AuthPresenceChange value. Stored as 'APC'. <br /> Database Value: 'APC' <br /> Model Value: 14 <br /> Domain API Value: 'AuthPresenceChange' |
| ChangePresenceToAvailable | ChangePresenceToAvailable value. Stored as 'PSA'. <br /> Database Value: 'PSA' <br /> Model Value: 15 <br /> Domain API Value: 'ChangePresenceToAvailable' |
| ChangePresenceToDND | ChangePresenceToDND value. Stored as 'PSD'. <br /> Database Value: 'PSD' <br /> Model Value: 16 <br /> Domain API Value: 'ChangePresenceToDND' |
| ChangePresenceToBusy | ChangePresenceToBusy value. Stored as 'PSB'. <br /> Database Value: 'PSB' <br /> Model Value: 17 <br /> Domain API Value: 'ChangePresenceToBusy' |
| ChangePresenceToAway | ChangePresenceToAway value. Stored as 'PSW'. <br /> Database Value: 'PSW' <br /> Model Value: 18 <br /> Domain API Value: 'ChangePresenceToAway' |
| ChangePresenceToOffline | ChangePresenceToOffline value. Stored as 'PSO'. <br /> Database Value: 'PSO' <br /> Model Value: 19 <br /> Domain API Value: 'ChangePresenceToOffline' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### PersonalDataProcess

The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A.

Type: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user account under which the event has occurred. Null only for events which are not user-specific.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Monitoring.AuditLogEntries erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Monitoring.AuditLogEntries erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Monitoring_AuditLogEntries

Domain API Entity Type: 
Systems_Monitoring_AuditLogEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_AuditLogEntries?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_AuditLogEntries?$top=10>

