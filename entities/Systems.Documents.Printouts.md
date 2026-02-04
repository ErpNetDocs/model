---
uid: Systems.Documents.Printouts
---
# Systems.Documents.Printouts


Contains data about binding of printout layouts to specific user-defined document types.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.Printouts  
Base Table: Gen_Printouts  
API access:  ReadWrite  

## Renames

Old name: General.Printouts  
New name: Systems.Documents.Printouts  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
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
| [AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate) | [AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate) | The minimal document state on wich is permited to print this printout 
| [ApplicationName](Systems.Documents.Printouts.md#applicationname) | string (64) | The application which stored and uses the printout 
| [BackwardCompatibility](Systems.Documents.Printouts.md#backwardcompatibility) | boolean | Supports the old data format. 
| [Copies](Systems.Documents.Printouts.md#copies) | int32 | Number of copies that will be printed when the user choses 'Print multiple'. 
| [Definition](Systems.Documents.Printouts.md#definition) | string (max) __nullable__ | The contents of the printout. 
| [DefinitionFormat](Systems.Documents.Printouts.md#definitionformat) | string (16) __nullable__ | System format of the printout definition. 
| [IsDefault](Systems.Documents.Printouts.md#isdefault) | boolean | If True this printout will be used in direct print or print preview. 
| [Name](Systems.Documents.Printouts.md#name) | string (64) | Name of the printout. 
| [Notes](Systems.Documents.Printouts.md#notes) | string (512) __nullable__ | Notes for this Printout. 
| [Ord](Systems.Documents.Printouts.md#ord) | int32 | Order in the multiple print. 0 means that the printout does not participate. 
| [OrdFilterXml](Systems.Documents.Printouts.md#ordfilterxml) | dataaccessfilter __nullable__ | The condition, required to be matched in order for the printout to be executed upon "Print All" command. 
| [OrdPriority](Systems.Documents.Printouts.md#ordpriority) | int32 __nullable__ | Ordinal position and priority of the printout, in regard to other printouts within the current document type. Used for sorting, when executing printouts with "Print All" command. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Systems.Documents.Printouts.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type to which this printout layout is bound. |
| [EnterpriseCompany](Systems.Documents.Printouts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Printout applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FiscalReceiptTemplate](Systems.Documents.Printouts.md#fiscalreceipttemplate) | [FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md) (nullable) | Template for customizing the fiscal receipt. |
| [PrintoutLayout](Systems.Documents.Printouts.md#printoutlayout) | [PrintoutLayouts](Systems.Documents.PrintoutLayouts.md) (nullable) | The printout layout, that is bound to the document type. |
| [Report](Systems.Documents.Printouts.md#report) | [DataSources](Systems.Documents.DataSources.md) (nullable) | A report that contains the set of data that will be loaded in the printout. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.Printouts.md#id) | guid |  
| [ObjectVersion](Systems.Documents.Printouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.Printouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AllowPrintingOnState

The minimal document state on wich is permited to print this printout

Type: **[AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate)**  
Category: **System**  
Allowed values for the `AllowPrintingOnState`(Systems.Documents.Printouts.md#allowprintingonstate) data attribute  
Allowed Values (Systems.Documents.PrintoutsRepository.AllowPrintingOnState Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Planned | Planned value. Stored as 10. <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Completed value. Stored as 40. <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | Closed value. Stored as 50. <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ApplicationName

The application which stored and uses the printout

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **CannotBeShown**  

Back-End Default Expression:  
`obj.Transaction.ApplicationName`

### BackwardCompatibility

Supports the old data format.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **CannotBeShown**  

### Copies

Number of copies that will be printed when the user choses 'Print multiple'.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### Definition

The contents of the printout.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### DefinitionFormat

System format of the printout definition.

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Default Value: **default**  
Show in UI: **CannotBeShown**  

### IsDefault

If True this printout will be used in direct print or print preview.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

Name of the printout.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Printout.

Type: **string (512) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **512**  
Show in UI: **ShownByDefault**  

### Ord

Order in the multiple print. 0 means that the printout does not participate.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### OrdFilterXml

The condition, required to be matched in order for the printout to be executed upon "Print All" command.

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrdPriority

Ordinal position and priority of the printout, in regard to other printouts within the current document type. Used for sorting, when executing printouts with "Print All" command.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

The document type to which this printout layout is bound.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### EnterpriseCompany

The Enterprise Company to which this Printout applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### FiscalReceiptTemplate

Template for customizing the fiscal receipt.

Type: **[FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrintoutLayout

The printout layout, that is bound to the document type.

Type: **[PrintoutLayouts](Systems.Documents.PrintoutLayouts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Report

A report that contains the set of data that will be loaded in the printout.

Type: **[DataSources](Systems.Documents.DataSources.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


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

[!list limit=1000 erp.entity=Systems.Documents.Printouts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.Printouts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_Printouts

Domain API Entity Type: 
Systems_Documents_Printout

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_Printouts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_Printouts?$top=10>

