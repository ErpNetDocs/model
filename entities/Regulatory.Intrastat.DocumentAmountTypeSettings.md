---
uid: Regulatory.Intrastat.DocumentAmountTypeSettings
---
# Regulatory.Intrastat.DocumentAmountTypeSettings


Specifies the additional amounts, which are added to the invoiced and statistical values.

## General
Namespace: [Regulatory.Intrastat](Regulatory.Intrastat.md)  
Repository: Regulatory.Intrastat.DocumentAmountTypeSettings  
Base Table: Its_Document_Amount_Type_Settings  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentAmountType.AmountTypeName:T}  
Search Members: DocumentAmountType.AmountTypeName  
Name Member: DocumentAmountType.AmountTypeName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AddToInvoicedValue](Regulatory.Intrastat.DocumentAmountTypeSettings.md#addtoinvoicedvalue) | boolean | 1= to add the amount to the invoiced value, 0=otherwise 
| [AddToStatisticalValue](Regulatory.Intrastat.DocumentAmountTypeSettings.md#addtostatisticalvalue) | boolean | 1= to add the amount to the statistical value, 0=otherwise 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentAmountType](Regulatory.Intrastat.DocumentAmountTypeSettings.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) | The amount type which will be added to the invoiced or the statistical value |
| [EnterpriseCompany](Regulatory.Intrastat.DocumentAmountTypeSettings.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the setting is valid |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Intrastat.DocumentAmountTypeSettings.md#id) | guid |  
| [ObjectVersion](Regulatory.Intrastat.DocumentAmountTypeSettings.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Intrastat.DocumentAmountTypeSettings.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AddToInvoicedValue

1= to add the amount to the invoiced value, 0=otherwise

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AddToStatisticalValue

1= to add the amount to the statistical value, 0=otherwise

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
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

### DocumentAmountType

The amount type which will be added to the invoiced or the statistical value

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company for which the setting is valid

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Intrastat.DocumentAmountTypeSettings erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Intrastat.DocumentAmountTypeSettings erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Intrastat_DocumentAmountTypeSettings

Domain API Entity Type: 
Regulatory_Intrastat_DocumentAmountTypeSetting

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Intrastat_DocumentAmountTypeSettings?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Intrastat_DocumentAmountTypeSettings?$top=10>

