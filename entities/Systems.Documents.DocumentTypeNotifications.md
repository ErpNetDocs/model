---
uid: Systems.Documents.DocumentTypeNotifications
---
# Systems.Documents.DocumentTypeNotifications Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Provides notification addresses to be notified upon occurrence of different document events. Entity: Gen_Document_Type_Notifications

## Renames

Old name: **General.DocumentTypeNotifications**  
New name: **Systems.Documents.DocumentTypeNotifications**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Documents.DocumentTypeNotifications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentEvent](Systems.Documents.DocumentTypeNotifications.md#documentevent) | string (254) | The event which will trigger the notification. `Required` `Default("StateChanging")` `Filter(eq)` 
| [FilterXML](Systems.Documents.DocumentTypeNotifications.md#filterxml) | string (max) __nullable__ | Filtering condition for the document. Only documents which match the filter will trigger the event. 
| [Id](Systems.Documents.DocumentTypeNotifications.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentTypeNotifications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StateBitMask](Systems.Documents.DocumentTypeNotifications.md#statebitmask) | int32 | The document states that will trigger the event. `Required` `Default(0)` 
| [StatusChangeDirection](Systems.Documents.DocumentTypeNotifications.md#statuschangedirection) | [StatusChangeDirection](Systems.Documents.DocumentTypeNotifications.md#statuschangedirection) | Direction of status change. Positive when the new status is greater than the previous. Applicable values: Positive '+', Negative '-', No change '0', Any change '*'. `Required` `Default("*")` 
| [ToEmailAddressList](Systems.Documents.DocumentTypeNotifications.md#toemailaddresslist) | string (2048) | List of email addressess to be notified. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Systems.Documents.DocumentTypeNotifications.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type for which this notification is set. `Required` `Filter(multi eq)` `Owner` |
| [UserStatus](Systems.Documents.DocumentTypeNotifications.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | When not null, specifies that the event will be triggered only on this user status. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentEvent

The event which will trigger the notification. `Required` `Default("StateChanging")` `Filter(eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Default Value_: **StateChanging**  
_Show in UI_: **HiddenByDefault**  

### FilterXML

Filtering condition for the document. Only documents which match the filter will trigger the event.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

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

### StateBitMask

The document states that will trigger the event. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### StatusChangeDirection

Direction of status change. Positive when the new status is greater than the previous. Applicable values: Positive '+', Negative '-', No change '0', Any change '*'. `Required` `Default("*")`

_Type_: **[StatusChangeDirection](Systems.Documents.DocumentTypeNotifications.md#statuschangedirection)**  
_Category_: **System**  
Allowed values for the `StatusChangeDirection`(Systems.Documents.DocumentTypeNotifications.md#statuschangedirection) data attribute  
_Allowed Values (Systems.Documents.DocumentTypeNotificationsRepository.StatusChangeDirection Enum Members)_  

| Value | Description |
| ---- | --- |
| AnyChange | AnyChange value. Stored as '*'. <br /> _Database Value:_ '*' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AnyChange' |
| NoChange | NoChange value. Stored as '0'. <br /> _Database Value:_ '0' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'NoChange' |
| PositiveChange | PositiveChange value. Stored as '+'. <br /> _Database Value:_ '+' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'PositiveChange' |
| NegativeChange | NegativeChange value. Stored as '-'. <br /> _Database Value:_ '-' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'NegativeChange' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **AnyChange**  
_Show in UI_: **HiddenByDefault**  

### ToEmailAddressList

List of email addressess to be notified. `Required`

_Type_: **string (2048)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2048**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentType

The document type for which this notification is set. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### UserStatus

When not null, specifies that the event will be triggered only on this user status. `Filter(multi eq)`

_Type_: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeNotifications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeNotifications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentTypeNotifications

Domain API Entity Type: 
Systems_Documents_DocumentTypeNotification

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentTypeNotifications?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentTypeNotifications?$top=10>

