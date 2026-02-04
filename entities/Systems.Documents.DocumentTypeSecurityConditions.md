---
uid: Systems.Documents.DocumentTypeSecurityConditions
---
# Systems.Documents.DocumentTypeSecurityConditions


Provides rules to conditionally secure new documents.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DocumentTypeSecurityConditions  
Base Table: Gen_Document_Type_Security_Conditions  
API access:  ReadWrite  

## Renames

Old name: General.DocumentTypeSecurityConditions  
New name: Systems.Documents.DocumentTypeSecurityConditions  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {DocumentType.EntityName}  
Search Members: DocumentType.EntityName  
Name Member: DocumentType.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionFilterXml](Systems.Documents.DocumentTypeSecurityConditions.md#conditionfilterxml) | dataaccessfilter | Specifies the documents, for which the current rule is applicable. The XML filter is compared against new documents and the rule is applicable when they match. 
| [Description](Systems.Documents.DocumentTypeSecurityConditions.md#description) | string (254) | The description of this DocumentTypeSecurity<br />Condition. `Required` `Filter(eq;like)` 
| [Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority) | [Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority) | Priority of the rule against other rules, which are also applicable. Only the highest priority rule is selected. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentAccessKey](Systems.Documents.DocumentTypeSecurityConditions.md#documentaccesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | The access key, which will be used to secure new documents, when this rule is selected. |
| [DocumentType](Systems.Documents.DocumentTypeSecurityConditions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type, whose documents will be secured by the current rule. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DocumentTypeSecurityConditions.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentTypeSecurityConditions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.DocumentTypeSecurityConditions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConditionFilterXml

Specifies the documents, for which the current rule is applicable. The XML filter is compared against new documents and the rule is applicable when they match.

Type: **dataaccessfilter**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Description

The description of this DocumentTypeSecurityCondition. `Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Priority

Priority of the rule against other rules, which are also applicable. Only the highest priority rule is selected.

Type: **[Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority)**  
Category: **System**  
Generic enum type for Priority properties  
Allowed Values (General.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Lowest' |
| Low | Low value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
| Medium | Medium value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Medium' |
| High | High value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'High' |
| Highest | Highest value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Highest' |

Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **3**  
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

### DocumentAccessKey

The access key, which will be used to secure new documents, when this rule is selected.

Type: **[AccessKeys](Systems.Security.AccessKeys.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### DocumentType

The document type, whose documents will be secured by the current rule.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeSecurityConditions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeSecurityConditions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentTypeSecurityConditions

Domain API Entity Type: 
Systems_Documents_DocumentTypeSecurityCondition

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentTypeSecurityConditions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentTypeSecurityConditions?$top=10>

