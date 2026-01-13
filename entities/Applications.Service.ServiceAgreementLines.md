---
uid: Applications.Service.ServiceAgreementLines
---
# Applications.Service.ServiceAgreementLines Entity

**Namespace:** [Applications.Service](Applications.Service.md)  

Service agreement lines represent the individual serviced objects that are covered by the service agreement. Entity: Srv_Service_Agreement_Lines

## Default Visualization
Default Display Text Format:  
_{Id}. {ServiceAgreement.DocumentNo} {ServiceAgreement.DocumentType.TypeName:T}_  
Default Search Members:  
_ServiceAgreement.DocumentNo_  
Name Data Member:  
_ServiceAgreement.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  
Aggregate Root:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Service.ServiceAgreementLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Service.ServiceAgreementLines.md#id) | guid |  
| [LineEndDateTime](Applications.Service.ServiceAgreementLines.md#lineenddatetime) | datetime | The ending date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)` 
| [LineNo](Applications.Service.ServiceAgreementLines.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)` 
| [LineStartDateTime](Applications.Service.ServiceAgreementLines.md#linestartdatetime) | datetime | The starting date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)` 
| [Notes](Applications.Service.ServiceAgreementLines.md#notes) | string (254) __nullable__ | Notes for this ServiceAgreementLine. 
| [ObjectVersion](Applications.Service.ServiceAgreementLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineNo](Applications.Service.ServiceAgreementLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Introduced in version 22.1.5.18` 
| [Quantity](Applications.Service.ServiceAgreementLines.md#quantity) | decimal (14, 3) | The quantity of the service object that is included in the agreement. `Required` `Default(1)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.Service.ServiceAgreementLines.md#document) | [ServiceAgreements](Applications.Service.ServiceAgreements.md) | The owner document. The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)` |
| [ParentDocument](Applications.Service.ServiceAgreementLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [ServiceAgreement](Applications.Service.ServiceAgreementLines.md#serviceagreement) | [ServiceAgreements](Applications.Service.ServiceAgreements.md) | The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ServiceObject](Applications.Service.ServiceAgreementLines.md#serviceobject) | [ServiceObjects](Applications.Service.ServiceObjects.md) | The service object, which is covered by the current agreement. `Required` `Filter(multi eq)` |
| [ServiceType](Applications.Service.ServiceAgreementLines.md#servicetype) | [ServiceTypes](Applications.Service.ServiceTypes.md) | The type (level) of service that is agreed. `Required` `Filter(multi eq)` |


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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineEndDateTime

The ending date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ServiceAgreement.EndDateTime`

_Front-End Recalc Expressions:_  
`obj.ServiceAgreement.EndDateTime`
### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ServiceAgreement.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ServiceAgreement.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStartDateTime

The starting date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ServiceAgreement.StartDateTime`

_Front-End Recalc Expressions:_  
`obj.ServiceAgreement.StartDateTime`
### Notes

Notes for this ServiceAgreementLine.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Introduced in version 22.1.5.18`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Quantity

The quantity of the service object that is included in the agreement. `Required` `Default(1)` `Filter(ge;le)`

_Type_: **decimal (14, 3)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The owner document. The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ServiceAgreement

The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ServiceObject

The service object, which is covered by the current agreement. `Required` `Filter(multi eq)`

_Type_: **[ServiceObjects](Applications.Service.ServiceObjects.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ServiceType

The type (level) of service that is agreed. `Required` `Filter(multi eq)`

_Type_: **[ServiceTypes](Applications.Service.ServiceTypes.md)**  
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

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceAgreementLines

Domain API Entity Type: 
Applications_Service_ServiceAgreementLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceAgreementLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceAgreementLines?$top=10>

