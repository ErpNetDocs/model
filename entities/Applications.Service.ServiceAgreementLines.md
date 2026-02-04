---
uid: Applications.Service.ServiceAgreementLines
---
# Applications.Service.ServiceAgreementLines


Service agreement lines represent the individual serviced objects that are covered by the service agreement.

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceAgreementLines  
Base Table: Srv_Service_Agreement_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {Id}. {ServiceAgreement.DocumentNo} {ServiceAgreement.DocumentType.TypeName:T}  
Search Members: ServiceAgreement.DocumentNo  
Name Member: ServiceAgreement.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  
Aggregate Root:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineEndDateTime](Applications.Service.ServiceAgreementLines.md#lineenddatetime) | datetime | The ending date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)` 
| [LineNo](Applications.Service.ServiceAgreementLines.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)` 
| [LineStartDateTime](Applications.Service.ServiceAgreementLines.md#linestartdatetime) | datetime | The starting date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)` 
| [Notes](Applications.Service.ServiceAgreementLines.md#notes) | string (254) __nullable__ | Notes for this ServiceAgreementLine. 
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


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceAgreementLines.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceAgreementLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Service.ServiceAgreementLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineEndDateTime

The ending date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ServiceAgreement.EndDateTime`

Front-End Recalc Expressions:  
`obj.ServiceAgreement.EndDateTime`
### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ServiceAgreement.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ServiceAgreement.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStartDateTime

The starting date and time of the agreement coverage for the current line. `Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ServiceAgreement.StartDateTime`

Front-End Recalc Expressions:  
`obj.ServiceAgreement.StartDateTime`
### Notes

Notes for this ServiceAgreementLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Introduced in version 22.1.5.18`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity of the service object that is included in the agreement. `Required` `Default(1)` `Filter(ge;le)`

Type: **decimal (14, 3)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **1**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)`

Type: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceAgreement

The <see cref="ServiceAgreement"/> to which this ServiceAgreementLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ServiceObject

The service object, which is covered by the current agreement. `Required` `Filter(multi eq)`

Type: **[ServiceObjects](Applications.Service.ServiceObjects.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceType

The type (level) of service that is agreed. `Required` `Filter(multi eq)`

Type: **[ServiceTypes](Applications.Service.ServiceTypes.md)**  
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

