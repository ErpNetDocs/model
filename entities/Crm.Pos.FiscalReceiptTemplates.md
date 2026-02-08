---
uid: Crm.Pos.FiscalReceiptTemplates
---
# Crm.Pos.FiscalReceiptTemplates


Templates for customizing the printouts of fiscal receipts.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.FiscalReceiptTemplates  
Base Table: Pos_Fiscal_Receipt_Templates  
Introduced In Version: 24.1.1.50  
API access:  ReadWrite  

## Visualization
Display Format: {TemplateName}  
Search Members: TemplateName  
Name Member: TemplateName  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CustomFooter](Crm.Pos.FiscalReceiptTemplates.md#customfooter) | string (256) __nullable__ | User-defined footer printed at the end of the document (interpolated string). 
| [CustomHeader](Crm.Pos.FiscalReceiptTemplates.md#customheader) | string (256) __nullable__ | User-defined header printed at the beginning of the document (interpolated string). 
| [CustomRowFooter](Crm.Pos.FiscalReceiptTemplates.md#customrowfooter) | string (256) __nullable__ | User-defined footer printed after each row (interpolated string). 
| [CustomRowHeader](Crm.Pos.FiscalReceiptTemplates.md#customrowheader) | string (256) __nullable__ | User-defined header printed before each row (interpolated string). 
| [PrintSystemHeader](Crm.Pos.FiscalReceiptTemplates.md#printsystemheader) | boolean | Denotes whether to print the system-defined header for the document.`Required` `Default(true)` `Filter(eq)` 
| [PrintSystemRowHeader](Crm.Pos.FiscalReceiptTemplates.md#printsystemrowheader) | boolean | Denotes whether to print the system-defined header for each row.`Required` `Default(true)` `Filter(eq)` 
| [TemplateKind](Crm.Pos.FiscalReceiptTemplates.md#templatekind) | [TemplateKind](Crm.Pos.FiscalReceiptTemplates.md#templatekind) | Specifies the entity type, for which the template can be used. Template strings can refer to the attributes of the specified entity type.`Required` `Default(&quot;S&quot;)` `Filter(multi eq)` `Introduced in version 24.1.5.7` 
| [TemplateName](Crm.Pos.FiscalReceiptTemplates.md#templatename) | string (64) | The unique name of the printing template.`Required` `Filter(eq;like)` `ORD` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.FiscalReceiptTemplates.md#id) | guid |  
| [ObjectVersion](Crm.Pos.FiscalReceiptTemplates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.FiscalReceiptTemplates.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.FiscalReceiptTemplates.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.FiscalReceiptTemplates.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.FiscalReceiptTemplates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CustomFooter

User-defined footer printed at the end of the document (interpolated string).

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### CustomHeader

User-defined header printed at the beginning of the document (interpolated string).

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### CustomRowFooter

User-defined footer printed after each row (interpolated string).

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### CustomRowHeader

User-defined header printed before each row (interpolated string).

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### PrintSystemHeader

Denotes whether to print the system-defined header for the document.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### PrintSystemRowHeader

Denotes whether to print the system-defined header for each row.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### TemplateKind

Specifies the entity type, for which the template can be used. Template strings can refer to the attributes of the specified entity type.`Required` `Default(&quot;S&quot;)` `Filter(multi eq)` `Introduced in version 24.1.5.7`

Type: **[TemplateKind](Crm.Pos.FiscalReceiptTemplates.md#templatekind)**  
Category: **System**  
Allowed values for the `TemplateKind`(Crm.Pos.FiscalReceiptTemplates.md#templatekind) data attribute  
Allowed Values (Crm.Pos.FiscalReceiptTemplatesRepository.TemplateKind Enum Members)  

| Value | Description |
| ---- | --- |
| SalesOrders | Sales Orders entity type. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'SalesOrders' |
| Invoices | Invoices entity type. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 1 <br /> Domain API Value: 'Invoices' |
| Payments | Payments entity type. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 2 <br /> Domain API Value: 'Payments' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **SalesOrders**  
Show in UI: **ShownByDefault**  

### TemplateName

The unique name of the printing template.`Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

[!list limit=1000 erp.entity=Crm.Pos.FiscalReceiptTemplates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.FiscalReceiptTemplates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_FiscalReceiptTemplates

Domain API Entity Type: 
Crm_Pos_FiscalReceiptTemplate

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_FiscalReceiptTemplates?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_FiscalReceiptTemplates?$top=10>

