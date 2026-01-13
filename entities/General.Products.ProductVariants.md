---
uid: General.Products.ProductVariants
---
# General.Products.ProductVariants Entity

**Namespace:** [General.Products](General.Products.md)  

Contains definitions of different variants of a product. The variants are differentiated by color, size and style. Entity: Gen_Product_Variants

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](General.Products.ProductVariants.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Products.ProductVariants.md#id) | guid |  
| [Name](General.Products.ProductVariants.md#name) | [MultilanguageString (512)](../data-types.md#multilanguagestring) __nullable__ | Product variant name. It is the concatenation of the names of the color, size and style. `ReadOnly` 
| [ObjectVersion](General.Products.ProductVariants.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ShortCode](General.Products.ProductVariants.md#shortcode) | string (32) __nullable__ | Short code of the variant, that is unique within the Product. Usually used as a data element in data encoded barcodes (e.g., GS1-128 barcodes). `Filter(eq;like)` `Introduced in version 23.1.1.19` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](General.Products.ProductVariants.md#product) | [Products](General.Products.Products.md) | The product for which this variant is defined. `Required` `Filter(multi eq)` `Owner` |
| [VariantColor](General.Products.ProductVariants.md#variantcolor) | [VariantColors](General.Products.VariantColors.md) (nullable) | The color of the variant. null means that the variant does not have a specific color. `Filter(multi eq)` |
| [VariantSize](General.Products.ProductVariants.md#variantsize) | [VariantSizes](General.Products.VariantSizes.md) (nullable) | The size of the variant. null means that the variant does not have a specific size. `Filter(multi eq)` |
| [VariantStyle](General.Products.ProductVariants.md#variantstyle) | [VariantStyles](General.Products.VariantStyles.md) (nullable) | The style of the variant. null means that the variant does not have a specific style. `Filter(multi eq)` |


## Attribute Details

### BarCode

When specified, it contains a bar code which uniquely identifies the product variant. `Filter(eq;like)` `ORD`

_Type_: **string (16) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### Code

The code of the variant. The code is unique within the Product. It is the concatenation of the codes of the color, size and style. `Required` `Filter(eq;like)` `ReadOnly`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
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

### Name

Product variant name. It is the concatenation of the names of the color, size and style. `ReadOnly`

_Type_: **[MultilanguageString (512)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`Join( " ", new [] {obj.VariantColor.Name, obj.VariantSize.Name, obj.VariantStyle.Name})`

_Front-End Recalc Expressions:_  
`Join( " ", new [] {obj.VariantColor.Name, obj.VariantSize.Name, obj.VariantStyle.Name})`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ShortCode

Short code of the variant, that is unique within the Product. Usually used as a data element in data encoded barcodes (e.g., GS1-128 barcodes). `Filter(eq;like)` `Introduced in version 23.1.1.19`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Product

The product for which this variant is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### VariantColor

The color of the variant. null means that the variant does not have a specific color. `Filter(multi eq)`

_Type_: **[VariantColors](General.Products.VariantColors.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VariantSize

The size of the variant. null means that the variant does not have a specific size. `Filter(multi eq)`

_Type_: **[VariantSizes](General.Products.VariantSizes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VariantStyle

The style of the variant. null means that the variant does not have a specific style. `Filter(multi eq)`

_Type_: **[VariantStyles](General.Products.VariantStyles.md) (nullable)**  
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

