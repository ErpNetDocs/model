---
uid: Crm.Sales.SalesOrdersOptions
---
# Crm.Sales.SalesOrdersOptions Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Options for sales orders of specific user defined document type. Entity: Crm_Sales_Orders_Options

## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections) | [AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections) | Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default). `Required` `Default("A")` `Filter(multi eq)` 
| [AvailableQuantityOnly](Crm.Sales.SalesOrdersOptions.md#availablequantityonly) | boolean | When true indicates that the sales order can be released only if there is sufficient available quantity (by ATP). `Required` `Default(false)` `Filter(eq)` 
| [DisplayText](Crm.Sales.SalesOrdersOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Sales.SalesOrdersOptions.md#id) | guid |  
| [MinimumAmount](Crm.Sales.SalesOrdersOptions.md#minimumamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | When not null, specifies minimal total amount of the sales order, which is required for order releasing. `Currency: MinimumAmountCurrency` 
| [ObjectVersion](Crm.Sales.SalesOrdersOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance) | [ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance) | Terms on which the shipment of the products in the sales order is allowed. `Required` `Default("A")` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DealDocumentType](Crm.Sales.SalesOrdersOptions.md#dealdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | If filled then new opportunities (deals) from the specified type are created automatically by the sales orders that aren't assigned to existing opportunities. `Filter(multi eq)` |
| [DocumentType](Crm.Sales.SalesOrdersOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type for which the sales order option applies. `Required` `Filter(multi eq)` `Owner` |
| [MinimumAmountCurrency](Crm.Sales.SalesOrdersOptions.md#minimumamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of Minimal Amount. `Filter(multi eq)` |
| [VATDeviationDocument<br />AmountType](Crm.Sales.SalesOrdersOptions.md#vatdeviationdocumentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT. `Filter(multi eq)` |


## Attribute Details

### AllowedDirections

Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default). `Required` `Default("A")` `Filter(multi eq)`

_Type_: **[AllowedDirections](Crm.Sales.SalesOrdersOptions.md#alloweddirections)**  
_Category_: **System**  
Allowed values for the `AllowedDirections`(Crm.Sales.SalesOrdersOptions.md#alloweddirections) data attribute  
_Allowed Values (Crm.Sales.SalesOrdersOptionsRepository.AllowedDirections Enum Members)_  

| Value | Description |
| ---- | --- |
| NormalSale | NormalSale value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NormalSale' |
| SalesReturn | SalesReturn value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'SalesReturn' |
| NoLimit | NoLimit value. Stored as '*'. <br /> _Database Value:_ '*' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'NoLimit' |
| AllowAnyButNotBoth | AllowAnyButNotBoth value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'AllowAnyButNotBoth' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **AllowAnyButNotBoth**  
_Show in UI_: **ShownByDefault**  

### AvailableQuantityOnly

When true indicates that the sales order can be released only if there is sufficient available quantity (by ATP). `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### MinimumAmount

When not null, specifies minimal total amount of the sales order, which is required for order releasing. `Currency: MinimumAmountCurrency`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ShipmentAllowance

Terms on which the shipment of the products in the sales order is allowed. `Required` `Default("A")`

_Type_: **[ShipmentAllowance](Crm.Sales.SalesOrdersOptions.md#shipmentallowance)**  
_Category_: **System**  
Allowed values for the `ShipmentAllowance`(Crm.Sales.SalesOrdersOptions.md#shipmentallowance) data attribute  
_Allowed Values (Crm.Sales.SalesOrdersOptionsRepository.ShipmentAllowance Enum Members)_  

| Value | Description |
| ---- | --- |
| AlwaysAllow | AlwaysAllow value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AlwaysAllow' |
| WaitForAnyPayment | WaitForAnyPayment value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'WaitForAnyPayment' |
| WaitForFullPayment | WaitForFullPayment value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'WaitForFullPayment' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **AlwaysAllow**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DealDocumentType

If filled then new opportunities (deals) from the specified type are created automatically by the sales orders that aren't assigned to existing opportunities. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

The document type for which the sales order option applies. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### MinimumAmountCurrency

The currency of Minimal Amount. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VATDeviationDocumentAmountType

Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT. `Filter(multi eq)`

_Type_: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

