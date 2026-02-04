---
uid: General.Documents.DocumentFileAttachments
---
# General.Documents.DocumentFileAttachments


Contains files, attached to the documents.

## General
Namespace: [General.Documents](General.Documents.md)  
Repository: General.Documents.DocumentFileAttachments  
Base Table: Gen_Document_File_Attachments  
API access:  ReadWrite  

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Renames

Old name: General.DocumentFileAttachments  
New name: General.Documents.DocumentFileAttachments  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Id}. {Document.DocumentNo} {Document.DocumentType.TypeName:T}  
Search Members: Document.DocumentNo  
Name Member: FileName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EmbeddedFileContents](General.Documents.DocumentFileAttachments.md#embeddedfilecontents) | byte[] __nullable__ | The contents of the embedded file. null when the file is linked. 
| [FileName](General.Documents.DocumentFileAttachments.md#filename) | string (128) | The display name of the file. Initially set to the file name (without path) of the linked or the embedded file. `Required` 
| [IsLinked](General.Documents.DocumentFileAttachments.md#islinked) | boolean | True when the document is linked (ony file name is kept). false when the document is embedded. `Required` `Default(false)` `Filter(eq)` 
| [LinkedFilePath](General.Documents.DocumentFileAttachments.md#linkedfilepath) | string (254) __nullable__ | Path to the linked file. null when the file is embedded. 
| [Notes](General.Documents.DocumentFileAttachments.md#notes) | string (max) __nullable__ | Notes for this DocumentFileAttachment. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentFileAttachments.md#document) | [Documents](General.Documents.Documents.md) | The <see cref="Document"/> to which this DocumentFileAttachment belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Documents.DocumentFileAttachments.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentFileAttachments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Documents.DocumentFileAttachments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EmbeddedFileContents

The contents of the embedded file. null when the file is linked.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### FileName

The display name of the file. Initially set to the file name (without path) of the linked or the embedded file. `Required`

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### IsLinked

True when the document is linked (ony file name is kept). false when the document is embedded. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LinkedFilePath

Path to the linked file. null when the file is embedded.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this DocumentFileAttachment.

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

### Document

The <see cref="Document"/> to which this DocumentFileAttachment belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=General.Documents.DocumentFileAttachments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentFileAttachments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentFileAttachments

Domain API Entity Type: 
General_Documents_DocumentFileAttachment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentFileAttachments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentFileAttachments?$top=10>

