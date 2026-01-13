---
uid: Applications.Telephony.CallDetails
---
# Applications.Telephony.CallDetails Entity

**Namespace:** [Applications.Telephony](Applications.Telephony.md)  

Contains call detail records. Calls are phone calls, video calls and SMS messages. Entity: Cm_Call_Details

## Default Visualization
Default Display Text Format:  
_{CalledPartyNumber}_  
Default Search Members:  
_CalledPartyNumber_  
Code Data Member:  
_CalledPartyNumber_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Telephony.CallDetails](Applications.Telephony.CallDetails.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalledPartyNumber](Applications.Telephony.CallDetails.md#calledpartynumber) | string (80) | The voice number of the party, which received the call. `Required` `Filter(eq;like)` 
| [CallingPartyNumber](Applications.Telephony.CallDetails.md#callingpartynumber) | string (80) | The voice number of the originating party of the call. `Required` `Filter(eq;like)` 
| [CallType](Applications.Telephony.CallDetails.md#calltype) | [CallType](Applications.Telephony.CallDetails.md#calltype) | P=Phone; V=Video; M=Message/SMS. `Required` `Default("P")` `Filter(eq)` 
| [CallUniqueId](Applications.Telephony.CallDetails.md#calluniqueid) | string (32) __nullable__ | The unique id of the call, as reported by the telephone central. null when the central did not report unique Id. Used for integration purposes. 
| [DisplayText](Applications.Telephony.CallDetails.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DurationSeconds](Applications.Telephony.CallDetails.md#durationseconds) | int32 | The duration of the call (in seconds). `Required` `Default(0)` `Filter(ge;le)` 
| [ExternalId](Applications.Telephony.CallDetails.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Telephony.CallDetails.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Applications.Telephony.CallDetails.md#id) | guid |  
| [ObjectVersion](Applications.Telephony.CallDetails.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartTime](Applications.Telephony.CallDetails.md#starttime) | datetime | The starting date and time of the call. `Required` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CalledParty](Applications.Telephony.CallDetails.md#calledparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party, which received the call. null when the party was not determined successfully. `Filter(multi eq)` |
| [CallingParty](Applications.Telephony.CallDetails.md#callingparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party, which originated the call.  null when the party was not determined successfully. `Filter(multi eq)` |
| [ExternalCompany](Applications.Telephony.CallDetails.md#externalcompany) | [Companies](General.Contacts.Companies.md) (nullable) | The company of the external party. It can be the party itself, or the parent party, whichever is company. null when the company cannot be determined. `Filter(multi eq)` |
| [ExternalParty](Applications.Telephony.CallDetails.md#externalparty) | [Parties](General.Contacts.Parties.md) (nullable) | It is either the From or the To party - depending of the direction of the call. Only calls with at least one external party participating are usually logged. null when the respective party was null, or when no external party participated in the call. `Filter(multi eq)` |


## Attribute Details

### CalledPartyNumber

The voice number of the party, which received the call. `Required` `Filter(eq;like)`

_Type_: **string (80)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **80**  
_Show in UI_: **ShownByDefault**  

### CallingPartyNumber

The voice number of the originating party of the call. `Required` `Filter(eq;like)`

_Type_: **string (80)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **80**  
_Show in UI_: **ShownByDefault**  

### CallType

P=Phone; V=Video; M=Message/SMS. `Required` `Default("P")` `Filter(eq)`

_Type_: **[CallType](Applications.Telephony.CallDetails.md#calltype)**  
_Category_: **System**  
Allowed values for the `CallType`(Applications.Telephony.CallDetails.md#calltype) data attribute  
_Allowed Values (Applications.Telephony.CallDetailsRepository.CallType Enum Members)_  

| Value | Description |
| ---- | --- |
| Phone | Phone value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Phone' |
| Video | Video value. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Video' |
| MessageOrSMS | MessageOrSMS value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MessageOrSMS' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Phone**  
_Show in UI_: **ShownByDefault**  

### CallUniqueId

The unique id of the call, as reported by the telephone central. null when the central did not report unique Id. Used for integration purposes.

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DurationSeconds

The duration of the call (in seconds). `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartTime

The starting date and time of the call. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CalledParty

The party, which received the call. null when the party was not determined successfully. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CallingParty

The party, which originated the call.  null when the party was not determined successfully. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExternalCompany

The company of the external party. It can be the party itself, or the parent party, whichever is company. null when the company cannot be determined. `Filter(multi eq)`

_Type_: **[Companies](General.Contacts.Companies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExternalParty

It is either the From or the To party - depending of the direction of the call. Only calls with at least one external party participating are usually logged. null when the respective party was null, or when no external party participated in the call. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
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

