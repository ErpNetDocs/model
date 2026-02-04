---
uid: Regulatory.Excise.ExciseProductCategories
---
# Regulatory.Excise.ExciseProductCategories


Product Category is defined by the taxation and customs authorities. Also specifies the calculation algorithm for the excise. For EU, the product category code is a single character - B,E,I,S,T or W.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseProductCategories  
Base Table: Exc_Excise_Product_Categories  
Introduced In Version: 21.1.3.87  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseProductCategories](Regulatory.Excise.ExciseProductCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalculationAlgorithm](Regulatory.Excise.ExciseProductCategories.md#calculationalgorithm) | [CalculationAlgorithm](Regulatory.Excise.ExciseProductCategories.md#calculationalgorithm) | The calculation algorithm for Tax Base. NOP=No operation - manually set Tax Base; QTY=Qty; QAS=Qty * Alcoholic strength; QAP=Qty * Alcoholic strength / 100. 
| [Code](Regulatory.Excise.ExciseProductCategories.md#code) | string (32) | For EU, the product category code is a single character - B,E,I,S,T or W. 
| [Name](Regulatory.Excise.ExciseProductCategories.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multilanguage String 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseProductCategories.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseProductCategories.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.ExciseProductCategories.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseProductCategories.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseProductCategories.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.ExciseProductCategories.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CalculationAlgorithm

The calculation algorithm for Tax Base. NOP=No operation - manually set Tax Base; QTY=Qty; QAS=Qty * Alcoholic strength; QAP=Qty * Alcoholic strength / 100.

Type: **[CalculationAlgorithm](Regulatory.Excise.ExciseProductCategories.md#calculationalgorithm)**  
Category: **System**  
Allowed values for the `CalculationAlgorithm`(Regulatory.Excise.ExciseProductCategories.md#calculationalgorithm) data attribute  
Allowed Values (Regulatory.Excise.ExciseProductCategoriesRepository.CalculationAlgorithm Enum Members)  

| Value | Description |
| ---- | --- |
| NoОperation | NoОperation value. Stored as 'NOP'. <br /> Database Value: 'NOP' <br /> Model Value: 0 <br /> Domain API Value: 'NoОperation' |
| Qty | Qty value. Stored as 'QTY'. <br /> Database Value: 'QTY' <br /> Model Value: 1 <br /> Domain API Value: 'Qty' |
| QtyByAlcoholicStrength | QtyByAlcoholicStrength value. Stored as 'QAS'. <br /> Database Value: 'QAS' <br /> Model Value: 2 <br /> Domain API Value: 'QtyByAlcoholicStrength' |
| QtyByAlcoholic<br />StrengthDiv100 | QtyByAlcoholic<br />StrengthDiv100 value. Stored as 'QAP'. <br /> Database Value: 'QAP' <br /> Model Value: 3 <br /> Domain API Value: 'QtyByAlcoholic<br />StrengthDiv100' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Code

For EU, the product category code is a single character - B,E,I,S,T or W.

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Name

Multilanguage String

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseProductCategories erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseProductCategories erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseProductCategories

Domain API Entity Type: 
Regulatory_Excise_ExciseProductCategory

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseProductCategories?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseProductCategories?$top=10>

