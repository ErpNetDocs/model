---
uid: Systems.Documents.DocumentTypeProperties
---
# Systems.Documents.DocumentTypeProperties


Default user-defined properties, which should be added to new documents.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DocumentTypeProperties  
Base Table: Gen_Document_Type_Properties  
API access:  ReadWrite  

## Renames

Old name: General.DocumentTypeProperties  
New name: Systems.Documents.DocumentTypeProperties  
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
| [DefaultPropertyValue](Systems.Documents.DocumentTypeProperties.md#defaultpropertyvalue) | string (254) __nullable__ | The default value of the property when creating new documents. 
| [DefaultProperty<br />ValueDescription](Systems.Documents.DocumentTypeProperties.md#defaultpropertyvaluedescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Default description value of the property when creating new documents. 
| [DefaultValueId](Systems.Documents.DocumentTypeProperties.md#defaultvalueid) | guid __nullable__ | Internal Id of the default value of the property. `Filter(multi eq)` 
| [LineNo](Systems.Documents.DocumentTypeProperties.md#lineno) | int32 | Line number, unique within the document type. `Required` `Filter(ge;le)` `ORD` 
| [Required](Systems.Documents.DocumentTypeProperties.md#required) | boolean | True if the property is required when creating documents of this type. `Required` `Default(false)` `Filter(eq)` 
| [RequiredFromDate](Systems.Documents.DocumentTypeProperties.md#requiredfromdate) | datetime __nullable__ | When not null, specifies a date, after which the property becomes required for the current document type. The date is compared against the document date. `Filter(ge;le)` 
| [RequiredThruDate](Systems.Documents.DocumentTypeProperties.md#requiredthrudate) | datetime __nullable__ | When not null, specifies a date, up to which the property is required for the current document type. The date is compared against the document date. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Systems.Documents.DocumentTypeProperties.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type, for which to add user-defined properties. `Required` `Filter(multi eq)` `Owner` |
| [EnterpriseCompany](Systems.Documents.DocumentTypeProperties.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, specifies that the current rule is valid only for the specified company. `Filter(multi eq)` |
| [Property](Systems.Documents.DocumentTypeProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The user-defined property, which should be added. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DocumentTypeProperties.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentTypeProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.DocumentTypeProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DefaultPropertyValue

The default value of the property when creating new documents.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### DefaultPropertyValueDescription

Default description value of the property when creating new documents.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DefaultValueId

Internal Id of the default value of the property. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineNo

Line number, unique within the document type. `Required` `Filter(ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.DocumentType.DocumentTypeProperties.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.DocumentType.DocumentTypeProperties.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Required

True if the property is required when creating documents of this type. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### RequiredFromDate

When not null, specifies a date, after which the property becomes required for the current document type. The date is compared against the document date. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RequiredThruDate

When not null, specifies a date, up to which the property is required for the current document type. The date is compared against the document date. `Filter(ge;le)`

Type: **datetime __nullable__**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### DocumentType

The document type, for which to add user-defined properties. `Required` `Filter(multi eq)` `Owner`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When not null, specifies that the current rule is valid only for the specified company. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Property

The user-defined property, which should be added. `Required` `Filter(multi eq)`

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentTypeProperties

Domain API Entity Type: 
Systems_Documents_DocumentTypeProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentTypeProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentTypeProperties?$top=10>

