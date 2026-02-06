---
uid: Regulatory.Vat.DeclarationLines
---
# Regulatory.Vat.DeclarationLines


Contains the VAT declaration lines for declaration, issued by the enterprise company, according to the eligible legislation.

## General
Namespace: [Regulatory.Vat](Regulatory.Vat.md)  
Repository: Regulatory.Vat.DeclarationLines  
Base Table: VAT_Declaration_Lines  
Introduced In Version: 22.1.4.22  
API access:  ReadWrite  

## Renames

Old name: Finance.Vat.DeclarationLines  
New name: Regulatory.Vat.DeclarationLines  
Version: 26.2.0.99  
Case: 39297  



## Visualization
Display Format: {LineNo}. {Declaration.DocumentNo} {Declaration.DocumentType.TypeName:T}  
Search Members: Declaration.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Vat.Declarations](Regulatory.Vat.Declarations.md)  
Aggregate Root:  
[Regulatory.Vat.Declarations](Regulatory.Vat.Declarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountBase](Regulatory.Vat.DeclarationLines.md#amountbase) | [Amount (14, 2)](../data-types.md#amount) | Declared value in base currency.[Currency: Declaration.BaseCurrency] [Required] [Default(0)] [Filter(eq;ge;le)] 
| [LineNo](Regulatory.Vat.DeclarationLines.md#lineno) | int32 | Consecutive line number within the document.[Required] 
| [Notes](Regulatory.Vat.DeclarationLines.md#notes) | string (max) __nullable__ | Notes for this DeclarationLine. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxType](Regulatory.Vat.DeclarationLines.md#boxtype) | [BoxTypes](Regulatory.Vat.BoxTypes.md) | Type of box in VAT declaration. |
| [Declaration](Regulatory.Vat.DeclarationLines.md#declaration) | [Declarations](Regulatory.Vat.Declarations.md) | The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Regulatory.Vat.DeclarationLines.md#document) | [Declarations](Regulatory.Vat.Declarations.md) | The owner document. The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Vat.DeclarationLines.md#id) | guid |  
| [ObjectVersion](Regulatory.Vat.DeclarationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Vat.DeclarationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AmountBase

Declared value in base currency.[Currency: Declaration.BaseCurrency] [Required] [Default(0)] [Filter(eq;ge;le)]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number within the document.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Declaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Declaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this DeclarationLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### BoxType

Type of box in VAT declaration.

Type: **[BoxTypes](Regulatory.Vat.BoxTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Declaration

The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Declarations](Regulatory.Vat.Declarations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)`

Type: **[Declarations](Regulatory.Vat.Declarations.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Regulatory.Vat.DeclarationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Vat.DeclarationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Vat_DeclarationLines

Domain API Entity Type: 
Regulatory_Vat_DeclarationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_DeclarationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_DeclarationLines?$top=10>

