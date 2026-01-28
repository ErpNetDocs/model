---
uid: Finance.Accounting.TemplateLineProperties
---
# Finance.Accounting.TemplateLineProperties


Contains the way to obtain the values for each required property of both the debit and the credit accounts.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.TemplateLineProperties  
Base Table: Acc_Template_Line_Properties  
API access:  ReadWrite  

## Visualization
Display Format: {TemplateLine.AmountColumnName}  
Search Members: TemplateLine.AmountColumnName  
Name Member: TemplateLine.AmountColumnName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Accounting.TemplateLines](Finance.Accounting.TemplateLines.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConstantValueId](Finance.Accounting.TemplateLineProperties.md#constantvalueid) | guid __nullable__ | The internal Id of a property value, selected as constant value. Applicable only when Property Value Source Type = Constant. `Filter(multi eq)` 
| [IsDebit](Finance.Accounting.TemplateLineProperties.md#isdebit) | boolean | If Is_Debit=true then this property is for the debit account in the template line for which is this record. If Is_Debit=false then the property is for the credit account. `Required` `Default(true)` `Filter(eq)` 
| [PropertyDescription](Finance.Accounting.TemplateLineProperties.md#propertydescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Description for the property value that should be used when the description can't be determined by the source (e.g. when the source type is constant). 
| [PropertyNo](Finance.Accounting.TemplateLineProperties.md#propertyno) | int32 | The ordinal position of the property value in the item key of the account. `Required` `Filter(eq)` 
| [PropertyValueSource](Finance.Accounting.TemplateLineProperties.md#propertyvaluesource) | string (2000) | Source for the property value according to the chosen source type. `Required` 
| [PropertyValueSourceType](Finance.Accounting.TemplateLineProperties.md#propertyvaluesourcetype) | string (64) | Type of source for the property value. For example: System properties, User properties for document, Constant, ... `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Property](Finance.Accounting.TemplateLineProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The property which value will be included in the item key of the account. `Required` `Filter(multi eq)` |
| [TemplateLine](Finance.Accounting.TemplateLineProperties.md#templateline) | [TemplateLines](Finance.Accounting.TemplateLines.md) | The <see cref="TemplateLine"/> to which this TemplateLineProperty belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.TemplateLineProperties.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.TemplateLineProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Accounting.TemplateLineProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConstantValueId

The internal Id of a property value, selected as constant value. Applicable only when Property Value Source Type = Constant. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IsDebit

If Is_Debit=true then this property is for the debit account in the template line for which is this record. If Is_Debit=false then the property is for the credit account. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **CannotBeShown**  

### PropertyDescription

Description for the property value that should be used when the description can't be determined by the source (e.g. when the source type is constant).

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PropertyNo

The ordinal position of the property value in the item key of the account. `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PropertyValueSource

Source for the property value according to the chosen source type. `Required`

Type: **string (2000)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2000**  
Show in UI: **ShownByDefault**  

### PropertyValueSourceType

Type of source for the property value. For example: System properties, User properties for document, Constant, ... `Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### Property

The property which value will be included in the item key of the account. `Required` `Filter(multi eq)`

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TemplateLine

The <see cref="TemplateLine"/> to which this TemplateLineProperty belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[TemplateLines](Finance.Accounting.TemplateLines.md)**  
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

[!list limit=1000 erp.entity=Finance.Accounting.TemplateLineProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.TemplateLineProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_TemplateLineProperties

Domain API Entity Type: 
Finance_Accounting_TemplateLineProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_TemplateLineProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TemplateLineProperties?$top=10>

