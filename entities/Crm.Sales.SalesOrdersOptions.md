---
uid: Crm.Sales.SalesOrdersOptions
---
# Crm.Sales.SalesOrdersOptions


Options for sales orders of specific user defined document type

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.SalesOrdersOptions  
Base Table: Crm_Sales_Orders_Options  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentType.EntityName}  
Search Members: DocumentType.EntityName  
Name Member: DocumentType.EntityName  
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
| [AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections) | [AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections) | Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default) 
| [AvailableQuantityOnly](Crm.Sales.SalesOrdersOptions.md#availablequantityonly) | boolean | When 1 indicates that the sales order can be released only if there is sufficient available quantity (by ATP) 
| [MinimumAmount](Crm.Sales.SalesOrdersOptions.md#minimumamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | When not NULL, specifies minimal total amount of the sales order, which is required for order releasing. 
| [ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance) | [ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance) | Terms on which the shipment of the products in the sales order is allowed. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DealDocumentType](Crm.Sales.SalesOrdersOptions.md#dealdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | If filled then new deals from the specified type are created automatically by the sales orders that aren't assigned to existing deals. |
| [DocumentType](Crm.Sales.SalesOrdersOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type for which the sales order option applies. |
| [MinimumAmountCurrency](Crm.Sales.SalesOrdersOptions.md#minimumamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of Minimal Amount |
| [VATDeviationDocument<br />AmountType](Crm.Sales.SalesOrdersOptions.md#vatdeviationdocumentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.SalesOrdersOptions.md#id) | guid |  
| [ObjectVersion](Crm.Sales.SalesOrdersOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.SalesOrdersOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AllowedDirections

Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default)

Type: **[AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections)**  
Category: **System**  
Allowed values for the `AllowedDirections`(Crm.Sales.SalesOrdersOptions.md#alloweddirections) data attribute  
Allowed Values (Crm.Sales.SalesOrdersOptionsRepository.AllowedDirections Enum Members)  

| Value | Description |
| ---- | --- |
| NormalSale | NormalSale value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'NormalSale' |
| SalesReturn | SalesReturn value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'SalesReturn' |
| NoLimit | NoLimit value. Stored as '*'. <br /> Database Value: '*' <br /> Model Value: 2 <br /> Domain API Value: 'NoLimit' |
| AllowAnyButNotBoth | AllowAnyButNotBoth value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 3 <br /> Domain API Value: 'AllowAnyButNotBoth' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **AllowAnyButNotBoth**  
Show in UI: **ShownByDefault**  

### AvailableQuantityOnly

When 1 indicates that the sales order can be released only if there is sufficient available quantity (by ATP)

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### MinimumAmount

When not NULL, specifies minimal total amount of the sales order, which is required for order releasing.

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ShipmentAllowance

Terms on which the shipment of the products in the sales order is allowed.

Type: **[ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance)**  
Category: **System**  
Allowed values for the `ShipmentAllowance`(Crm.Sales.SalesOrdersOptions.md#shipmentallowance) data attribute  
Allowed Values (Crm.Sales.SalesOrdersOptionsRepository.ShipmentAllowance Enum Members)  

| Value | Description |
| ---- | --- |
| AlwaysAllow | AlwaysAllow value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'AlwaysAllow' |
| WaitForAnyPayment | WaitForAnyPayment value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'WaitForAnyPayment' |
| WaitForFullPayment | WaitForFullPayment value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 2 <br /> Domain API Value: 'WaitForFullPayment' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **AlwaysAllow**  
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

### DealDocumentType

If filled then new deals from the specified type are created automatically by the sales orders that aren't assigned to existing deals.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

The document type for which the sales order option applies.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### MinimumAmountCurrency

The currency of Minimal Amount

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VATDeviationDocumentAmountType

Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT.

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Sales.SalesOrdersOptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.SalesOrdersOptions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_SalesOrdersOptions

Domain API Entity Type: 
Crm_Sales_SalesOrdersOption

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_SalesOrdersOptions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_SalesOrdersOptions?$top=10>

