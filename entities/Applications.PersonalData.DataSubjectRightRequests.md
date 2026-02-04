---
uid: Applications.PersonalData.DataSubjectRightRequests
---
# Applications.PersonalData.DataSubjectRightRequests


Contains user requests for application of user rights.

## General
Namespace: [Applications.PersonalData](Applications.PersonalData.md)  
Repository: Applications.PersonalData.DataSubjectRightRequests  
Base Table: Pdm_Data_Subject_Right_Requests  
Introduced In Version: 18.2  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {EnterpriseCompanyId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.PersonalData.DataSubjectRightRequests](Applications.PersonalData.DataSubjectRightRequests.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedOnUtc](Applications.PersonalData.DataSubjectRightRequests.md#completedonutc) | datetime __nullable__ | Date and time (in UTC), when the requested right was implemented by the responsible entity. Null if the request is still not implemented. `Filter(ge;le)` 
| [CreatedOnUtc](Applications.PersonalData.DataSubjectRightRequests.md#createdonutc) | datetime | The date and time (in UTC), when the request was created. `Required` `Default(Now)` `Filter(ge;le)` 
| [Notes](Applications.PersonalData.DataSubjectRightRequests.md#notes) | string (max) __nullable__ | This should usually contain detailed implementation notes. 
| [RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright) | [RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright) | The requested right, according to GDPR and other personal data regulations.  REC=Rectify; ERA=Erasure; RES=Restrict; POR=Portability; OBJ=Object; OTH=Other. `Required` `Filter(eq)` 
| [Status](Applications.PersonalData.DataSubjectRightRequests.md#status) | [Status](Applications.PersonalData.DataSubjectRightRequests.md#status) | The status of the request. 1=Requested; 2=Reviewing; 3=Executing; 4=Implemented; 5=Denied. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedByUser](Applications.PersonalData.DataSubjectRightRequests.md#completedbyuser) | [Users](Systems.Security.Users.md) (nullable) | The internal user account, which marked the request as implemented. Null when the request is still not implemented, or when the user is unknown. `Filter(multi eq)` `ReadOnly` |
| [CreatedByUser](Applications.PersonalData.DataSubjectRightRequests.md#createdbyuser) | [Users](Systems.Security.Users.md) (nullable) | The user account, which was used to create the request. Null when the request was created internally, on behalf of the external person. `Filter(multi eq)` `ReadOnly` |
| [EnterpriseCompany](Applications.PersonalData.DataSubjectRightRequests.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company, to which the request was made. `Required` `Filter(multi eq)` |
| [Person](Applications.PersonalData.DataSubjectRightRequests.md#person) | [Persons](General.Contacts.Persons.md) | The person, whose data will be corrected with the request. . `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.PersonalData.DataSubjectRightRequests.md#id) | guid |  
| [ObjectVersion](Applications.PersonalData.DataSubjectRightRequests.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.PersonalData.DataSubjectRightRequests.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.DataSubjectRightRequests.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.PersonalData.DataSubjectRightRequests.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.PersonalData.DataSubjectRightRequests.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CompletedOnUtc

Date and time (in UTC), when the requested right was implemented by the responsible entity. Null if the request is still not implemented. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreatedOnUtc

The date and time (in UTC), when the request was created. `Required` `Default(Now)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Notes

This should usually contain detailed implementation notes.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RequestedRight

The requested right, according to GDPR and other personal data regulations.  REC=Rectify; ERA=Erasure; RES=Restrict; POR=Portability; OBJ=Object; OTH=Other. `Required` `Filter(eq)`

Type: **[RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright)**  
Category: **System**  
Allowed values for the `RequestedRight`(Applications.PersonalData.DataSubjectRightRequests.md#requestedright) data attribute  
Allowed Values (Applications.PersonalData.DataSubjectRightRequestsRepository.RequestedRight Enum Members)  

| Value | Description |
| ---- | --- |
| Rectify | Rectify value. Stored as 'REC'. <br /> Database Value: 'REC' <br /> Model Value: 0 <br /> Domain API Value: 'Rectify' |
| Erasure | Erasure value. Stored as 'ERA'. <br /> Database Value: 'ERA' <br /> Model Value: 1 <br /> Domain API Value: 'Erasure' |
| Restrict | Restrict value. Stored as 'RES'. <br /> Database Value: 'RES' <br /> Model Value: 2 <br /> Domain API Value: 'Restrict' |
| Portability | Portability value. Stored as 'POR'. <br /> Database Value: 'POR' <br /> Model Value: 3 <br /> Domain API Value: 'Portability' |
| Object | Object value. Stored as 'OBJ'. <br /> Database Value: 'OBJ' <br /> Model Value: 4 <br /> Domain API Value: 'Object' |
| Other | Other value. Stored as 'OTH'. <br /> Database Value: 'OTH' <br /> Model Value: 5 <br /> Domain API Value: 'Other' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Status

The status of the request. 1=Requested; 2=Reviewing; 3=Executing; 4=Implemented; 5=Denied. `Required`

Type: **[Status](Applications.PersonalData.DataSubjectRightRequests.md#status)**  
Category: **System**  
Allowed values for the `Status`(Applications.PersonalData.DataSubjectRightRequests.md#status) data attribute  
Allowed Values (Applications.PersonalData.DataSubjectRightRequestsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| Requested | Requested value. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'Requested' |
| Reviewing | Reviewing value. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'Reviewing' |
| Executing | Executing value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'Executing' |
| Implemented | Implemented value. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'Implemented' |
| Denied | Denied value. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'Denied' |

Supported Filters: **NotFilterable**  
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

### CompletedByUser

The internal user account, which marked the request as implemented. Null when the request is still not implemented, or when the user is unknown. `Filter(multi eq)` `ReadOnly`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CreatedByUser

The user account, which was used to create the request. Null when the request was created internally, on behalf of the external person. `Filter(multi eq)` `ReadOnly`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company, to which the request was made. `Required` `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Person

The person, whose data will be corrected with the request. . `Required` `Filter(multi eq)`

Type: **[Persons](General.Contacts.Persons.md)**  
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

[!list limit=1000 erp.entity=Applications.PersonalData.DataSubjectRightRequests erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.PersonalData.DataSubjectRightRequests erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_PersonalData_DataSubjectRightRequests

Domain API Entity Type: 
Applications_PersonalData_DataSubjectRightRequest

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_PersonalData_DataSubjectRightRequests?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_PersonalData_DataSubjectRightRequests?$top=10>

