---
uid: Logistics.Inventory.Lots
---
# Logistics.Inventory.Lots


Warehouse lots. They contain one row for each specific product, status, production batch and other specific warehousing conditions. Lot status can block certain operations.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.Lots  
Base Table: Inv_Lots  
API access:  ReadWrite  

## Visualization
Display Format: {Number}  
Search Members: Number  
Code Member: Number  
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.Lots](Logistics.Inventory.Lots.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AlcoholicStrength](Logistics.Inventory.Lots.md#alcoholicstrength) | decimal (5, 2) | Percentage of pure alcohol used in excise duty reporting. 
| [Description](Logistics.Inventory.Lots.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The description of this Lot. 
| [ExpiryDate](Logistics.Inventory.Lots.md#expirydate) | datetime __nullable__ | Expiry date for this lot. 
| [LicenseNo](Logistics.Inventory.Lots.md#licenseno) | string (50) __nullable__ | The license number for this lot. Null when license number is N/A or unknown. 
| [Number](Logistics.Inventory.Lots.md#number) | string (30) | The unique number of the Lot. May contain characters, if required. `Required` `Filter(eq;like)` `ORD` 
| [ProductionBatchId](Logistics.Inventory.Lots.md#productionbatchid) | guid __nullable__ | Non-null if the production batch is known. Production batches are automatically created for internal production, but can also be used for specifying production batches for purchased goods. `Filter(multi eq)` 
| [PurchaseLotNumber](Logistics.Inventory.Lots.md#purchaselotnumber) | string (30) __nullable__ | Identification of the purchase lost with which the products from this store lot are received. E.g. the document number of the Receiving order. 
| [ReceiptDate](Logistics.Inventory.Lots.md#receiptdate) | date __nullable__ | The date of the first receipt of products in this lot. 
| [Status](Logistics.Inventory.Lots.md#status) | [Status](Logistics.Inventory.Lots.md#status) | Status of the warehouse lot. Minus statuses describe blocked conditions.
-3 blocked for document (sales or service order)
-2 blocked for party
-1 blocked for inspection
0 free to use 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BlockedForDocument](Logistics.Inventory.Lots.md#blockedfordocument) | [Documents](General.Documents.Documents.md) (nullable) | If non-null, contains the document for which the lot is blocked |
| [BlockedForParty](Logistics.Inventory.Lots.md#blockedforparty) | [Parties](General.Contacts.Parties.md) (nullable) | Non-NULL when the warehouse lot is blocked specifically for some party |
| [CertificateDocument](Logistics.Inventory.Lots.md#certificatedocument) | [Documents](General.Documents.Documents.md) (nullable) | Document, containing the certificate for this lot. |
| [ExciseMeasuringTransaction](Logistics.Inventory.Lots.md#excisemeasuringtransaction) | [MeasuringTransactions](Regulatory.Excise.MeasuringTransactions.md) (nullable) | When the lot was created in an excise controlled environment, specifies the measuring transaction which was used to create the lot. |
| [Product](Logistics.Inventory.Lots.md#product) | [Products](General.Products.Products.md) | The product to which the lot is bound |
| [ReceiptStoreTransaction](Logistics.Inventory.Lots.md#receiptstoretransaction) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) (nullable) | The store receipt transaction, which created the lot. NULL if the lot is manually created |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.Lots.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.Lots.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Inventory.Lots.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Inventory.Lots.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Inventory.Lots.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Inventory.Lots.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AlcoholicStrength

Percentage of pure alcohol used in excise duty reporting.

Type: **decimal (5, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Description

The description of this Lot.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ExpiryDate

Expiry date for this lot.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicenseNo

The license number for this lot. Null when license number is N/A or unknown.

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### Number

The unique number of the Lot. May contain characters, if required. `Required` `Filter(eq;like)` `ORD`

Type: **string (30)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.GetNextDefaultLotNumber( )`

### ProductionBatchId

Non-null if the production batch is known. Production batches are automatically created for internal production, but can also be used for specifying production batches for purchased goods. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### PurchaseLotNumber

Identification of the purchase lost with which the products from this store lot are received. E.g. the document number of the Receiving order.

Type: **string (30) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

### ReceiptDate

The date of the first receipt of products in this lot.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Status

Status of the warehouse lot. Minus statuses describe blocked conditions.
-3 blocked for document (sales or service order)
-2 blocked for party
-1 blocked for inspection
0 free to use

Type: **[Status](Logistics.Inventory.Lots.md#status)**  
Category: **System**  
Allowed values for the `Status`(Logistics.Inventory.Lots.md#status) data attribute  
Allowed Values (Logistics.Inventory.LotsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| FreeToUse | FreeToUse value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'FreeToUse' |
| BlockedForDocument | BlockedForDocument value. Stored as -3. <br /> Database Value: -3 <br /> Model Value: -3 <br /> Domain API Value: 'BlockedForDocument' |
| BlockedForParty | BlockedForParty value. Stored as -2. <br /> Database Value: -2 <br /> Model Value: -2 <br /> Domain API Value: 'BlockedForParty' |
| BlockedForInspection | BlockedForInspection value. Stored as -1. <br /> Database Value: -1 <br /> Model Value: -1 <br /> Domain API Value: 'BlockedForInspection' |

Supported Filters: **Equals, EqualsIn**  
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


## Reference Details

### BlockedForDocument

If non-null, contains the document for which the lot is blocked

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### BlockedForParty

Non-NULL when the warehouse lot is blocked specifically for some party

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CertificateDocument

Document, containing the certificate for this lot.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseMeasuringTransaction

When the lot was created in an excise controlled environment, specifies the measuring transaction which was used to create the lot.

Type: **[MeasuringTransactions](Regulatory.Excise.MeasuringTransactions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product to which the lot is bound

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReceiptStoreTransaction

The store receipt transaction, which created the lot. NULL if the lot is manually created

Type: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.Lots erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.Lots erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_Lots

Domain API Entity Type: 
Logistics_Inventory_Lot

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_Lots?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_Lots?$top=10>

