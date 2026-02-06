---
uid: General.Products.ProductTypePurchaseInvoiceLineProperties
---
# General.Products.ProductTypePurchaseInvoiceLineProperties


When specified for a product type, contains the suggested user-defined properties, which can be specified when creating new purchase invoice lines with products of this type.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductTypePurchaseInvoiceLineProperties  
Base Table: Gen_Product_Type_Purchase_Invoice_Line_Properties  
API access:  ReadWrite  

## Visualization
Display Format: {ProductType.Name:T}  
Search Members: ProductType.Name  
Name Member: ProductType.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.ProductTypes](General.Products.ProductTypes.md)  
Aggregate Root:  
[General.Products.ProductTypes](General.Products.ProductTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [PropertyNo](General.Products.ProductTypePurchaseInvoiceLineProperties.md#propertyno) | int32 | The consecutive number (position) of the property within the current product type.[Required] 
| [Required](General.Products.ProductTypePurchaseInvoiceLineProperties.md#required) | boolean | True when the property is required, when creating new purchase invoice lines. False when this only suggests the usage of the property.[Required] [Default(false)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProductType](General.Products.ProductTypePurchaseInvoiceLineProperties.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The <see cref="ProductType"/> to which this ProductTypePurchase<br />InvoiceLineProperty belongs. `Required` `Filter(multi eq)` `Owner` |
| [Property](General.Products.ProductTypePurchaseInvoiceLineProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The user-defined property. It should be with Entity Type = 'Purchase Invoice Line'. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductTypePurchaseInvoiceLineProperties.md#id) | guid |  
| [ObjectVersion](General.Products.ProductTypePurchaseInvoiceLineProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductTypePurchaseInvoiceLineProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### PropertyNo

The consecutive number (position) of the property within the current product type.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ProductType.PurchaseInvoiceLineProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.ProductType.PurchaseInvoiceLineProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Required

True when the property is required, when creating new purchase invoice lines. False when this only suggests the usage of the property.[Required] [Default(false)]

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

### ProductType

The <see cref="ProductType"/> to which this ProductTypePurchaseInvoiceLineProperty belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ProductTypes](General.Products.ProductTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Property

The user-defined property. It should be with Entity Type = 'Purchase Invoice Line'.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=General.Products.ProductTypePurchaseInvoiceLineProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductTypePurchaseInvoiceLineProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductTypePurchaseInvoiceLineProperties

Domain API Entity Type: 
General_Products_ProductTypePurchaseInvoiceLineProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductTypePurchaseInvoiceLineProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductTypePurchaseInvoiceLineProperties?$top=10>

