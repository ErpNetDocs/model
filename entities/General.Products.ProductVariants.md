---
uid: General.Products.ProductVariants
---
# General.Products.ProductVariants


Contains definitions of different variants of a product. The variants are differentiated by color, size and style.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductVariants  
Base Table: Gen_Product_Variants  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BarCode](General.Products.ProductVariants.md#barcode) | string (16) __nullable__ | When specified, it contains a bar code which uniquely identifies the product variant. `Filter(eq;like)` `ORD` 
| [Code](General.Products.ProductVariants.md#code) | string (16) | The code of the variant. The code is unique within the Product. It is the concatenation of the codes of the color, size and style. `Required` `Filter(eq;like)` `ReadOnly` 
| [Name](General.Products.ProductVariants.md#name) | [MultilanguageString (512)](../data-types.md#multilanguagestring) __nullable__ | Product variant name. It is the concatenation of the names of the color, size and style. `ReadOnly` 
| [ShortCode](General.Products.ProductVariants.md#shortcode) | string (32) __nullable__ | Short code of the variant, that is unique within the Product. Usually used as a data element in data encoded barcodes (e.g., GS1-128 barcodes). `Filter(eq;like)` `Introduced in version 23.1.1.19` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](General.Products.ProductVariants.md#product) | [Products](General.Products.Products.md) | The product for which this variant is defined. `Required` `Filter(multi eq)` `Owner` |
| [VariantColor](General.Products.ProductVariants.md#variantcolor) | [VariantColors](General.Products.VariantColors.md) (nullable) | The color of the variant. null means that the variant does not have a specific color. `Filter(multi eq)` |
| [VariantSize](General.Products.ProductVariants.md#variantsize) | [VariantSizes](General.Products.VariantSizes.md) (nullable) | The size of the variant. null means that the variant does not have a specific size. `Filter(multi eq)` |
| [VariantStyle](General.Products.ProductVariants.md#variantstyle) | [VariantStyles](General.Products.VariantStyles.md) (nullable) | The style of the variant. null means that the variant does not have a specific style. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductVariants.md#id) | guid |  
| [ObjectVersion](General.Products.ProductVariants.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductVariants.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BarCode

When specified, it contains a bar code which uniquely identifies the product variant. `Filter(eq;like)` `ORD`

Type: **string (16) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Code

The code of the variant. The code is unique within the Product. It is the concatenation of the codes of the color, size and style. `Required` `Filter(eq;like)` `ReadOnly`

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Name

Product variant name. It is the concatenation of the names of the color, size and style. `ReadOnly`

Type: **[MultilanguageString (512)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`Join( " ", new [] {obj.VariantColor.Name, obj.VariantSize.Name, obj.VariantStyle.Name})`

Front-End Recalc Expressions:  
`Join( " ", new [] {obj.VariantColor.Name, obj.VariantSize.Name, obj.VariantStyle.Name})`
### ShortCode

Short code of the variant, that is unique within the Product. Usually used as a data element in data encoded barcodes (e.g., GS1-128 barcodes). `Filter(eq;like)` `Introduced in version 23.1.1.19`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **32**  
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

### Product

The product for which this variant is defined. `Required` `Filter(multi eq)` `Owner`

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### VariantColor

The color of the variant. null means that the variant does not have a specific color. `Filter(multi eq)`

Type: **[VariantColors](General.Products.VariantColors.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VariantSize

The size of the variant. null means that the variant does not have a specific size. `Filter(multi eq)`

Type: **[VariantSizes](General.Products.VariantSizes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VariantStyle

The style of the variant. null means that the variant does not have a specific style. `Filter(multi eq)`

Type: **[VariantStyles](General.Products.VariantStyles.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Products.ProductVariants erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductVariants erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductVariants

Domain API Entity Type: 
General_Products_ProductVariant

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductVariants?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductVariants?$top=10>

