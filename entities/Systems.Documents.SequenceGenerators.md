---
uid: Systems.Documents.SequenceGenerators
---
# Systems.Documents.SequenceGenerators


Contains one or more sequence generators for each sequence. Many sequence generators for one sequence are used when the generators must be selected conditionally or when more generators are needed for parallel numbering.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.SequenceGenerators  
Base Table: Gen_Sequence_Generators  
API access:  ReadWrite  

## Renames

Old name: General.SequenceGenerators  
New name: Systems.Documents.SequenceGenerators  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Sequence.Name}  
Search Members: Sequence.Name  
Name Member: Sequence.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.Sequences](Systems.Documents.Sequences.md)  
Aggregate Root:  
[Systems.Documents.Sequences](Systems.Documents.Sequences.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowExplicitNumbering](Systems.Documents.SequenceGenerators.md#allowexplicitnumbering) | boolean | Allows to assign numbers explicitely regardless of the next value of the generator. If numbers aren't assigned explicitely then the generator works as usual.`Required` `Default(false)` 
| [NextValue](Systems.Documents.SequenceGenerators.md#nextvalue) | string (16) | The next number that will be issued by the sequence`Required` `Default(&quot;0000000001&quot;)` 
| [SequencePriority](Systems.Documents.SequenceGenerators.md#sequencepriority) | int32 | The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True`<br />Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Documents.SequenceGenerators.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this SequenceGenerator applies. `Required` `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Systems.Documents.SequenceGenerators.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. `Filter(multi eq)` |
| [ResponsiblePerson](Systems.Documents.SequenceGenerators.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | If this column is filled then the generator is designated for use only in documents with the specified responsible person. |
| [Sequence](Systems.Documents.SequenceGenerators.md#sequence) | [Sequences](Systems.Documents.Sequences.md) | The <see cref="Sequence"/> to which this SequenceGenerator belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.SequenceGenerators.md#id) | guid |  
| [ObjectVersion](Systems.Documents.SequenceGenerators.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.SequenceGenerators.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AllowExplicitNumbering

Allows to assign numbers explicitely regardless of the next value of the generator. If numbers aren't assigned explicitely then the generator works as usual.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### NextValue

The next number that will be issued by the sequence`Required` `Default(&quot;0000000001&quot;)`

Type: **string (16)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Default Value: **0000000001**  
Show in UI: **ShownByDefault**  

### SequencePriority

The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True`Required` `Default(1)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### EnterpriseCompany

The Enterprise Company to which this SequenceGenerator applies. `Required` `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResponsiblePerson

If this column is filled then the generator is designated for use only in documents with the specified responsible person.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Sequence

The <see cref="Sequence"/> to which this SequenceGenerator belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Sequences](Systems.Documents.Sequences.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Systems.Documents.SequenceGenerators erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.SequenceGenerators erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_SequenceGenerators

Domain API Entity Type: 
Systems_Documents_SequenceGenerator

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_SequenceGenerators?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_SequenceGenerators?$top=10>

