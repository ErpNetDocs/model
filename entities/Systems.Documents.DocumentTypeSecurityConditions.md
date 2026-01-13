---
uid: Systems.Documents.DocumentTypeSecurityConditions
---
# Systems.Documents.DocumentTypeSecurityConditions Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Provides rules to conditionally secure new documents. Entity: Gen_Document_Type_Security_Conditions

## Renames

Old name: **General.DocumentTypeSecurityConditions**  
New name: **Systems.Documents.DocumentTypeSecurityConditions**  
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
| [ConditionFilterXml](Systems.Documents.DocumentTypeSecurityConditions.md#conditionfilterxml) | dataaccessfilter | Specifies the documents, for which the current rule is applicable. The XML filter is compared against new documents and the rule is applicable when they match. `Unit: obj.DocumentType.EntityName` `Required` 
| [Description](Systems.Documents.DocumentTypeSecurityConditions.md#description) | string (254) | The description of this DocumentTypeSecurity<br />Condition. `Required` `Filter(eq;like)` 
| [DisplayText](Systems.Documents.DocumentTypeSecurityConditions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Documents.DocumentTypeSecurityConditions.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentTypeSecurityConditions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority) | [Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority) | Priority of the rule against other rules, which are also applicable. Only the highest priority rule is selected. `Required` `Default(3)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentAccessKey](Systems.Documents.DocumentTypeSecurityConditions.md#documentaccesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | The access key, which will be used to secure new documents, when this rule is selected. `Required` `Filter(multi eq)` |
| [DocumentType](Systems.Documents.DocumentTypeSecurityConditions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type, whose documents will be secured by the current rule. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ConditionFilterXml

Specifies the documents, for which the current rule is applicable. The XML filter is compared against new documents and the rule is applicable when they match. `Unit: obj.DocumentType.EntityName` `Required`

_Type_: **dataaccessfilter**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Description

The description of this DocumentTypeSecurityCondition. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Priority

Priority of the rule against other rules, which are also applicable. Only the highest priority rule is selected. `Required` `Default(3)` `Filter(ge;le)`

_Type_: **[Priority](Systems.Documents.DocumentTypeSecurityConditions.md#priority)**  
_Category_: **System**  
Generic enum type for Priority properties  
_Allowed Values (General.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Low | Low value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
| Medium | Medium value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Medium' |
| High | High value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **3**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentAccessKey

The access key, which will be used to secure new documents, when this rule is selected. `Required` `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### DocumentType

The document type, whose documents will be secured by the current rule. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

