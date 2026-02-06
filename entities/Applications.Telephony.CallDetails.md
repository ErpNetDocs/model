---
uid: Applications.Telephony.CallDetails
---
# Applications.Telephony.CallDetails


Contains call detail records. Calls are phone calls, video calls and SMS messages.

## General
Namespace: [Applications.Telephony](Applications.Telephony.md)  
Repository: Applications.Telephony.CallDetails  
Base Table: Cm_Call_Details  
API access:  ReadWrite  

## Visualization
Display Format: {CalledPartyNumber}  
Search Members: CalledPartyNumber  
Code Member: CalledPartyNumber  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Telephony.CallDetails](Applications.Telephony.CallDetails.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalledPartyNumber](Applications.Telephony.CallDetails.md#calledpartynumber) | string (80) | The voice number of the party, which received the call[Required] [Filter(eq;like)] 
| [CallingPartyNumber](Applications.Telephony.CallDetails.md#callingpartynumber) | string (80) | The voice number of the originating party of the call[Required] [Filter(eq;like)] 
| [CallType](Applications.Telephony.CallDetails.md#calltype) | [CallType](Applications.Telephony.CallDetails.md#calltype) | P=Phone; V=Video; M=Message/SMS[Required] [Default(&quot;P&quot;)] [Filter(eq)] 
| [CallUniqueId](Applications.Telephony.CallDetails.md#calluniqueid) | string (32) __nullable__ | The unique id of the call, as reported by the telephone central. NULL when the central did not report unique Id. Used for integration purposes 
| [DurationSeconds](Applications.Telephony.CallDetails.md#durationseconds) | int32 | The duration of the call (in seconds)[Required] [Default(0)] [Filter(ge;le)] 
| [StartTime](Applications.Telephony.CallDetails.md#starttime) | datetime | The starting date and time of the call[Required] [Filter(ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CalledParty](Applications.Telephony.CallDetails.md#calledparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party, which received the call. NULL when the party was not determined successfully |
| [CallingParty](Applications.Telephony.CallDetails.md#callingparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party, which originated the call.  NULL when the party was not determined successfully |
| [ExternalCompany](Applications.Telephony.CallDetails.md#externalcompany) | [Companies](General.Contacts.Companies.md) (nullable) | The company of the external party. It can be the party itself, or the parent party, whichever is company. NULL when the company cannot be determined |
| [ExternalParty](Applications.Telephony.CallDetails.md#externalparty) | [Parties](General.Contacts.Parties.md) (nullable) | It is either the From or the To party - depending of the direction of the call. Only calls with at least one external party participating are usually logged. NULL when the respective party was null, or when no external party participated in the call |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Telephony.CallDetails.md#id) | guid |  
| [ObjectVersion](Applications.Telephony.CallDetails.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Telephony.CallDetails.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Telephony.CallDetails.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Telephony.CallDetails.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Telephony.CallDetails.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CalledPartyNumber

The voice number of the party, which received the call[Required] [Filter(eq;like)]

Type: **string (80)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **80**  
Show in UI: **ShownByDefault**  

### CallingPartyNumber

The voice number of the originating party of the call[Required] [Filter(eq;like)]

Type: **string (80)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **80**  
Show in UI: **ShownByDefault**  

### CallType

P=Phone; V=Video; M=Message/SMS[Required] [Default(&quot;P&quot;)] [Filter(eq)]

Type: **[CallType](Applications.Telephony.CallDetails.md#calltype)**  
Category: **System**  
Allowed values for the `CallType`(Applications.Telephony.CallDetails.md#calltype) data attribute  
Allowed Values (Applications.Telephony.CallDetailsRepository.CallType Enum Members)  

| Value | Description |
| ---- | --- |
| Phone | Phone value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Phone' |
| Video | Video value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 1 <br /> Domain API Value: 'Video' |
| MessageOrSMS | MessageOrSMS value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'MessageOrSMS' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Phone**  
Show in UI: **ShownByDefault**  

### CallUniqueId

The unique id of the call, as reported by the telephone central. NULL when the central did not report unique Id. Used for integration purposes

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### DurationSeconds

The duration of the call (in seconds)[Required] [Default(0)] [Filter(ge;le)]

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### StartTime

The starting date and time of the call[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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

### CalledParty

The party, which received the call. NULL when the party was not determined successfully

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CallingParty

The party, which originated the call.  NULL when the party was not determined successfully

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExternalCompany

The company of the external party. It can be the party itself, or the parent party, whichever is company. NULL when the company cannot be determined

Type: **[Companies](General.Contacts.Companies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExternalParty

It is either the From or the To party - depending of the direction of the call. Only calls with at least one external party participating are usually logged. NULL when the respective party was null, or when no external party participated in the call

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.Telephony.CallDetails erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Telephony.CallDetails erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Telephony_CallDetails

Domain API Entity Type: 
Applications_Telephony_CallDetail

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Telephony_CallDetails?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Telephony_CallDetails?$top=10>

