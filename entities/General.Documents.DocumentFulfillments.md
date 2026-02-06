---
uid: General.Documents.DocumentFulfillments
---
# General.Documents.DocumentFulfillments


Fulfillment ledger for documents.

## General
Namespace: [General.Documents](General.Documents.md)  
Repository: General.Documents.DocumentFulfillments  
Base Table: Gen_Document_Fulfillments  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Renames

Old name: General.DocumentFulfillments  
New name: General.Documents.DocumentFulfillments  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Id}. {Document.DocumentNo} {Document.DocumentType.TypeName:T}  
Search Members: Document.DocumentNo  
Name Member: DestinationEntityName  
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
| [CreationTimeUtc](General.Documents.DocumentFulfillments.md#creationtimeutc) | datetime | The exact time in UTC, when the fulfillment was created in the system.[Required] [Default(NowUtc)] [Filter(multi eq;ge;le)] 
| [DestinationEntityName](General.Documents.DocumentFulfillments.md#destinationentityname) | string (64) | The name of the entity which fulfills the line. Used to differentiate between different fulfillment types. For example, sales order line can be fulfilled, for different purposes, by store order line and invoice order line.[Required] [Default(&quot;&quot;)] [Filter(eq)] [Introduced in version 22.1.4.7] 
| [DocumentLineId](General.Documents.DocumentFulfillments.md#documentlineid) | guid | The Id of the fulfilled line within the document. The attribute contains the Id and is not a reference, because it references different entities depending on document entity type and line type. `Required` `Filter(multi eq)` 
| [FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype) | [FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype) | Type of fulfillment: P=Planned; C=Completed.[Required] [Filter(multi eq)] [Introduced in version 21.1.1.26] 
| [IsFinal](General.Documents.DocumentFulfillments.md#isfinal) | boolean | Specifies whether this fulfillment finalizes the line, regardless of any remaining quantities.[Required] [Filter(eq)] 
| [LineNo](General.Documents.DocumentFulfillments.md#lineno) | int32 __nullable__ | Line number. Used for human-readability of the fulfillment. NULL if the lines do not support line numbers or the line number is unknown.[Filter(multi eq;ge;le)] [Introduced in version 21.1.1.26] 
| [LineType](General.Documents.DocumentFulfillments.md#linetype) | string (1) | Detail (line) type, for example materials, services, etc. L=Line. Other values are defined by the document entity type.[Required] [Default(&quot;L&quot;)] [Filter(multi eq)] [Introduced in version 21.1.1.26] 
| [QuantityBase](General.Documents.DocumentFulfillments.md#quantitybase) | decimal (12, 3) | Fulfilled quantity in the base measurement unit of the product.[Required] [Filter(multi eq;ge;le)] [Introduced in version 21.1.1.33] 
| [StandardQuantity](General.Documents.DocumentFulfillments.md#standardquantity) | decimal (12, 3) | The theoretical quantity according to the current measurement dimensions for the product. Used to measure the execution.[Required] [Introduced in version 22.1.4.52] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](General.Documents.DocumentFulfillments.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the record. |
| [Document](General.Documents.DocumentFulfillments.md#document) | [Documents](General.Documents.Documents.md) | The Document, which is fulfilled. |
| [Lot](General.Documents.DocumentFulfillments.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot, which was fulfilled. NULL when the fulfillment was not for a specific lot. |
| [ParentFulfillment](General.Documents.DocumentFulfillments.md#parentfulfillment) | [DocumentFulfillments](General.Documents.DocumentFulfillments.md) (nullable) | The parent document fulfillment. Used when the information of the current fulfillment is inherited by another document fulfillment, usually created by another module. |
| [Product](General.Documents.DocumentFulfillments.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which is fulfilled. |
| [ProductVariant](General.Documents.DocumentFulfillments.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was fulfilled. NULL when the fulfillment was not for a product variant. |
| [SerialNumber](General.Documents.DocumentFulfillments.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number, which was fulfilled. NULL when the fulfillment was not for a specific serial number. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Documents.DocumentFulfillments.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentFulfillments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Documents.DocumentFulfillments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTimeUtc

The exact time in UTC, when the fulfillment was created in the system.[Required] [Default(NowUtc)] [Filter(multi eq;ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### DestinationEntityName

The name of the entity which fulfills the line. Used to differentiate between different fulfillment types. For example, sales order line can be fulfilled, for different purposes, by store order line and invoice order line.[Required] [Default(&quot;&quot;)] [Filter(eq)] [Introduced in version 22.1.4.7]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Default Value: ****  
Show in UI: **ShownByDefault**  

### DocumentLineId

The Id of the fulfilled line within the document. The attribute contains the Id and is not a reference, because it references different entities depending on document entity type and line type. `Required` `Filter(multi eq)`

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### FulfillmentType

Type of fulfillment: P=Planned; C=Completed.[Required] [Filter(multi eq)] [Introduced in version 21.1.1.26]

Type: **[FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype)**  
Category: **System**  
Allowed values for the `FulfillmentType`(General.Documents.DocumentFulfillments.md#fulfillmenttype) data attribute  
Allowed Values (General.Documents.DocumentFulfillmentsRepository.FulfillmentType Enum Members)  

| Value | Description |
| ---- | --- |
| Planned | Planned value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Planned' |
| Completed | Completed value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Completed' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsFinal

Specifies whether this fulfillment finalizes the line, regardless of any remaining quantities.[Required] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Line number. Used for human-readability of the fulfillment. NULL if the lines do not support line numbers or the line number is unknown.[Filter(multi eq;ge;le)] [Introduced in version 21.1.1.26]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineType

Detail (line) type, for example materials, services, etc. L=Line. Other values are defined by the document entity type.[Required] [Default(&quot;L&quot;)] [Filter(multi eq)] [Introduced in version 21.1.1.26]

Type: **string (1)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **1**  
Default Value: **L**  
Show in UI: **ShownByDefault**  

### QuantityBase

Fulfilled quantity in the base measurement unit of the product.[Required] [Filter(multi eq;ge;le)] [Introduced in version 21.1.1.33]

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardQuantity

The theoretical quantity according to the current measurement dimensions for the product. Used to measure the execution.[Required] [Introduced in version 22.1.4.52]

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### CreationUser

The user, who created the record.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The Document, which is fulfilled.

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### Lot

The lot, which was fulfilled. NULL when the fulfillment was not for a specific lot.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentFulfillment

The parent document fulfillment. Used when the information of the current fulfillment is inherited by another document fulfillment, usually created by another module.

Type: **[DocumentFulfillments](General.Documents.DocumentFulfillments.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, which is fulfilled.

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The product variant, which was fulfilled. NULL when the fulfillment was not for a product variant.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

The serial number, which was fulfilled. NULL when the fulfillment was not for a specific serial number.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Documents.DocumentFulfillments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentFulfillments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentFulfillments

Domain API Entity Type: 
General_Documents_DocumentFulfillment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentFulfillments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentFulfillments?$top=10>

