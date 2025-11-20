---
uid: Systems.Monitoring.AuditLogEntries
---
# Systems.Monitoring.AuditLogEntries Entity

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Each record represents the occurrence of one logged event. Entity: Sys_Audit_Log_Entries (Introduced in version 18.2)

## Renames

Old name: **Systems.Core.AuditLogEntries**  
New name: **Systems.Monitoring.AuditLogEntries**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{ApplicationName}_  
Default Search Members:  
_ApplicationName_  
Name Data Member:  
_ApplicationName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadOnly_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _0 - Do not track changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AuditLogEntries](Systems.Monitoring.AuditLogEntries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.AuditLogEntries.md#applicationname) | string (64) __nullable__ | The client application that triggered the event. Null when unknown or N/A. `Filter(eq;like)` 
| [Details](Systems.Monitoring.AuditLogEntries.md#details) | string (max) __nullable__ | Detailed contents of the event. Contents depend on the Event Type and Event Name. 
| [DisplayText](Systems.Monitoring.AuditLogEntries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityItemId](Systems.Monitoring.AuditLogEntries.md#entityitemid) | guid __nullable__ | The Id of the record, which is referenced by the event. Null when unknown or N/A. `Filter(multi eq)` 
| [EntityName](Systems.Monitoring.AuditLogEntries.md#entityname) | string (64) __nullable__ | The entity, which is being referenced by the event. Null when unknown or N/A. `Filter(eq;like)` 
| [EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass) | [EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass) | The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events; P=Presence changes. `Required` `Filter(multi eq)` 
| [EventName](Systems.Monitoring.AuditLogEntries.md#eventname) | string (128) __nullable__ | Specific event or method name. Contents depend on the Event Type. Null when N/A. `Filter(eq;like)` 
| [EventTimeUtc](Systems.Monitoring.AuditLogEntries.md#eventtimeutc) | datetime | The exact date and time (in Utc) when the event occurred. `Required` `Default(Now)` `Filter(ge;le)` `ORD` 
| [EventType](Systems.Monitoring.AuditLogEntries.md#eventtype) | [EventType](Systems.Monitoring.AuditLogEntries.md#eventtype) | Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event. `Required` `Filter(multi eq)` 
| [ExternalId](Systems.Monitoring.AuditLogEntries.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.AuditLogEntries.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Monitoring.AuditLogEntries.md#id) | guid |  
| [ObjectVersion](Systems.Monitoring.AuditLogEntries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PersonalDataProcess](Systems.Monitoring.AuditLogEntries.md#personaldataprocess) | [PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable) | The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A. `Filter(multi eq)` |
| [User](Systems.Monitoring.AuditLogEntries.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user account under which the event has occurred. Null only for events which are not user-specific. `Filter(multi eq)` |


## Attribute Details

### ApplicationName

The client application that triggered the event. Null when unknown or N/A. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Details

Detailed contents of the event. Contents depend on the Event Type and Event Name.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityItemId

The Id of the record, which is referenced by the event. Null when unknown or N/A. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EntityName

The entity, which is being referenced by the event. Null when unknown or N/A. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### EventClass

The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events; P=Presence changes. `Required` `Filter(multi eq)`

_Type_: **[EventClass](Systems.Monitoring.AuditLogEntries.md#eventclass)**  
_Category_: **System**  
Allowed values for the `EventClass`(Systems.Monitoring.AuditLogEntries.md#eventclass) data attribute  
_Allowed Values (Systems.Monitoring.AuditLogEntriesRepository.EventClass Enum Members)_  

| Value | Description |
| ---- | --- |
| Entity | Entity value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Entity' |
| Authentication | Authentication value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Authentication' |
| Server | Server value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Server' |
| Presence | Presence value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Presence' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### EventName

Specific event or method name. Contents depend on the Event Type. Null when N/A. `Filter(eq;like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### EventTimeUtc

The exact date and time (in Utc) when the event occurred. `Required` `Default(Now)` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### EventType

Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event. `Required` `Filter(multi eq)`

_Type_: **[EventType](Systems.Monitoring.AuditLogEntries.md#eventtype)**  
_Category_: **System**  
Allowed values for the `EventType`(Systems.Monitoring.AuditLogEntries.md#eventtype) data attribute  
_Allowed Values (Systems.Monitoring.AuditLogEntriesRepository.EventType Enum Members)_  

| Value | Description |
| ---- | --- |
| ReadOneRecordById | ReadOneRecordById value. Stored as 'EID'. <br /> _Database Value:_ 'EID' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ReadOneRecordById' |
| LoadManyRecords | LoadManyRecords value. Stored as 'ELD'. <br /> _Database Value:_ 'ELD' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'LoadManyRecords' |
| CreateRecord | CreateRecord value. Stored as 'ECR'. <br /> _Database Value:_ 'ECR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'CreateRecord' |
| UpdateData | UpdateData value. Stored as 'EUP'. <br /> _Database Value:_ 'EUP' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'UpdateData' |
| DeleteRecord | DeleteRecord value. Stored as 'EDE'. <br /> _Database Value:_ 'EDE' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'DeleteRecord' |
| CallMethod | CallMethod value. Stored as 'EMT'. <br /> _Database Value:_ 'EMT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CallMethod' |
| OtherEntityEvent | OtherEntityEvent value. Stored as 'ETH'. <br /> _Database Value:_ 'ETH' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'OtherEntityEvent' |
| Login | Login value. Stored as 'AIN'. <br /> _Database Value:_ 'AIN' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Login' |
| LogOut | LogOut value. Stored as 'AOU'. <br /> _Database Value:_ 'AOU' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'LogOut' |
| SignUp | SignUp value. Stored as 'AUP'. <br /> _Database Value:_ 'AUP' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'SignUp' |
| LoginFailed | LoginFailed value. Stored as 'AFL'. <br /> _Database Value:_ 'AFL' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'LoginFailed' |
| ChangePassword | ChangePassword value. Stored as 'APW'. <br /> _Database Value:_ 'APW' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'ChangePassword' |
| OtherAuthEvent | OtherAuthEvent value. Stored as 'ATH'. <br /> _Database Value:_ 'ATH' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'OtherAuthEvent' |
| OtherServerEvent | OtherServerEvent value. Stored as 'STH'. <br /> _Database Value:_ 'STH' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'OtherServerEvent' |
| AuthPresenceChange | AuthPresenceChange value. Stored as 'APC'. <br /> _Database Value:_ 'APC' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'AuthPresenceChange' |

_Supported Filters_: **Equals, EqualsIn**  
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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### PersonalDataProcess

The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A. `Filter(multi eq)`

_Type_: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user account under which the event has occurred. Null only for events which are not user-specific. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
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

