---
uid: Systems.Monitoring.InformationMessages
---
# Systems.Monitoring.InformationMessages Entity

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Contains information messages, generated by various system processes. Entity: Sys_Information_Messages

## Renames

Old name: **Systems.Core.InformationMessages**  
New name: **Systems.Monitoring.InformationMessages**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{InformationMessageType} - {ProcessDescription}_  
Default Search Members:  
_MachineName_  
Name Data Member:  
_MachineName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.InformationMessages](Systems.Monitoring.InformationMessages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Monitoring.InformationMessages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Monitoring.InformationMessages.md#id) | guid |  
| [InformationMessageTime](Systems.Monitoring.InformationMessages.md#informationmessagetime) | datetime | Date and time when thet message occurred. `Required` `Default(Now)` `Filter(ge;le)` `ORD` `ReadOnly` 
| [InformationMessageType](Systems.Monitoring.InformationMessages.md#informationmessagetype) | [InformationMessageType](Systems.Monitoring.InformationMessages.md#informationmessagetype) | Type of the information message: 'INF' = Information, 'WRN' = Warning, Error = 'ERR'. `Required` `Default("INF")` `Filter(multi eq)` `ReadOnly` 
| [MachineName](Systems.Monitoring.InformationMessages.md#machinename) | string (128) | Machine name of the computer from which the process which creates the message has been initiated. `Required` `ReadOnly` 
| [Message](Systems.Monitoring.InformationMessages.md#message) | string (max) | The actual content of the information message. `Required` `Filter(like)` `ReadOnly` 
| [ObjectVersion](Systems.Monitoring.InformationMessages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProcessDescription](Systems.Monitoring.InformationMessages.md#processdescription) | string (254) | Name or description of the process that creates the message. `Required` `Filter(eq;like)` `ReadOnly` 
| [URL](Systems.Monitoring.InformationMessages.md#url) | string (254) __nullable__ | URL of the record that has posted the information message. `Filter(eq)` 
| [UserName](Systems.Monitoring.InformationMessages.md#username) | string (128) | Login name of the user that has initiated the process which creates the message. `Required` `Filter(eq)` `ReadOnly` 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InformationMessageTime

Date and time when thet message occurred. `Required` `Default(Now)` `Filter(ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### InformationMessageType

Type of the information message: 'INF' = Information, 'WRN' = Warning, Error = 'ERR'. `Required` `Default("INF")` `Filter(multi eq)` `ReadOnly`

_Type_: **[InformationMessageType](Systems.Monitoring.InformationMessages.md#informationmessagetype)**  
_Category_: **System**  
Allowed values for the `InformationMessageType`(Systems.Monitoring.InformationMessages.md#informationmessagetype) data attribute  
_Allowed Values (Systems.Monitoring.InformationMessagesRepository.InformationMessageType Enum Members)_  

| Value | Description |
| ---- | --- |
| Information | Information value. Stored as 'INF'. <br /> _Database Value:_ 'INF' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Information' |
| Warning | Warning value. Stored as 'WRN'. <br /> _Database Value:_ 'WRN' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Warning' |
| Error | Return error message for the Action Field.. Stored as 'ERR'. <br /> _Database Value:_ 'ERR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Error' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Information**  
_Show in UI_: **ShownByDefault**  

### MachineName

Machine name of the computer from which the process which creates the message has been initiated. `Required` `ReadOnly`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Message

The actual content of the information message. `Required` `Filter(like)` `ReadOnly`

_Type_: **string (max)**  
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

### ProcessDescription

Name or description of the process that creates the message. `Required` `Filter(eq;like)` `ReadOnly`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### URL

URL of the record that has posted the information message. `Filter(eq)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### UserName

Login name of the user that has initiated the process which creates the message. `Required` `Filter(eq)` `ReadOnly`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
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

[!list limit=1000 erp.entity=Systems.Monitoring.InformationMessages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Monitoring.InformationMessages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_InformationMessages?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_InformationMessages?$top=10>

