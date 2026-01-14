---
uid: Applications.PersonalData.DataSubjectRightRequests
---
# Applications.PersonalData.DataSubjectRightRequests Entity

**Namespace:** [Applications.PersonalData](Applications.PersonalData.md)  

Contains user requests for application of user rights. Entity: Pdm_Data_Subject_Right_Requests (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{Id}: {EnterpriseCompanyId}_  
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
* [Applications.PersonalData.DataSubjectRightRequests](Applications.PersonalData.DataSubjectRightRequests.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Applications.PersonalData.DataSubjectRightRequests.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [CompletedOnUtc](Applications.PersonalData.DataSubjectRightRequests.md#completedonutc) | datetime __nullable__ | Date and time (in UTC), when the requested right was implemented by the responsible entity. Null if the request is still not implemented. `Filter(ge;le)` 
| [CreatedOnUtc](Applications.PersonalData.DataSubjectRightRequests.md#createdonutc) | datetime | The date and time (in UTC), when the request was created. `Required` `Default(Now)` `Filter(ge;le)` 
| [DisplayText](Applications.PersonalData.DataSubjectRightRequests.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Applications.PersonalData.DataSubjectRightRequests.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.DataSubjectRightRequests.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Applications.PersonalData.DataSubjectRightRequests.md#id) | guid |  
| [Notes](Applications.PersonalData.DataSubjectRightRequests.md#notes) | string (max) __nullable__ | This should usually contain detailed implementation notes. 
| [ObjectVersion](Applications.PersonalData.DataSubjectRightRequests.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright) | [RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright) | The requested right, according to GDPR and other personal data regulations.  REC=Rectify; ERA=Erasure; RES=Restrict; POR=Portability; OBJ=Object; OTH=Other. `Required` `Filter(eq)` 
| [Status](Applications.PersonalData.DataSubjectRightRequests.md#status) | [Status](Applications.PersonalData.DataSubjectRightRequests.md#status) | The status of the request. 1=Requested; 2=Reviewing; 3=Executing; 4=Implemented; 5=Denied. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedByUser](Applications.PersonalData.DataSubjectRightRequests.md#completedbyuser) | [Users](Systems.Security.Users.md) (nullable) | The internal user account, which marked the request as implemented. Null when the request is still not implemented, or when the user is unknown. `Filter(multi eq)` `ReadOnly` |
| [CreatedByUser](Applications.PersonalData.DataSubjectRightRequests.md#createdbyuser) | [Users](Systems.Security.Users.md) (nullable) | The user account, which was used to create the request. Null when the request was created internally, on behalf of the external person. `Filter(multi eq)` `ReadOnly` |
| [EnterpriseCompany](Applications.PersonalData.DataSubjectRightRequests.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company, to which the request was made. `Required` `Filter(multi eq)` |
| [Person](Applications.PersonalData.DataSubjectRightRequests.md#person) | [Persons](General.Contacts.Persons.md) | The person, whose data will be corrected with the request. . `Required` `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CompletedOnUtc

Date and time (in UTC), when the requested right was implemented by the responsible entity. Null if the request is still not implemented. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreatedOnUtc

The date and time (in UTC), when the request was created. `Required` `Default(Now)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

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

### Notes

This should usually contain detailed implementation notes.

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

### RequestedRight

The requested right, according to GDPR and other personal data regulations.  REC=Rectify; ERA=Erasure; RES=Restrict; POR=Portability; OBJ=Object; OTH=Other. `Required` `Filter(eq)`

_Type_: **[RequestedRight](Applications.PersonalData.DataSubjectRightRequests.md#requestedright)**  
_Category_: **System**  
Allowed values for the `RequestedRight`(Applications.PersonalData.DataSubjectRightRequests.md#requestedright) data attribute  
_Allowed Values (Applications.PersonalData.DataSubjectRightRequestsRepository.RequestedRight Enum Members)_  

| Value | Description |
| ---- | --- |
| Rectify | Rectify value. Stored as 'REC'. <br /> _Database Value:_ 'REC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Rectify' |
| Erasure | Erasure value. Stored as 'ERA'. <br /> _Database Value:_ 'ERA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Erasure' |
| Restrict | Restrict value. Stored as 'RES'. <br /> _Database Value:_ 'RES' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Restrict' |
| Portability | Portability value. Stored as 'POR'. <br /> _Database Value:_ 'POR' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Portability' |
| Object | Object value. Stored as 'OBJ'. <br /> _Database Value:_ 'OBJ' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Object' |
| Other | Other value. Stored as 'OTH'. <br /> _Database Value:_ 'OTH' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Status

The status of the request. 1=Requested; 2=Reviewing; 3=Executing; 4=Implemented; 5=Denied. `Required`

_Type_: **[Status](Applications.PersonalData.DataSubjectRightRequests.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Applications.PersonalData.DataSubjectRightRequests.md#status) data attribute  
_Allowed Values (Applications.PersonalData.DataSubjectRightRequestsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| Requested | Requested value. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Requested' |
| Reviewing | Reviewing value. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Reviewing' |
| Executing | Executing value. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Executing' |
| Implemented | Implemented value. Stored as '4'. <br /> _Database Value:_ '4' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Implemented' |
| Denied | Denied value. Stored as '5'. <br /> _Database Value:_ '5' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Denied' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CompletedByUser

The internal user account, which marked the request as implemented. Null when the request is still not implemented, or when the user is unknown. `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CreatedByUser

The user account, which was used to create the request. Null when the request was created internally, on behalf of the external person. `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company, to which the request was made. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

The person, whose data will be corrected with the request. . `Required` `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md)**  
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

