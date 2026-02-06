---
uid: General.Products.ProductDimensions
---
# General.Products.ProductDimensions


Contains convertion ratios between the supported measument categories for each product. Does not contain a record for the default category of the products, for which the convertion ratio is defined as equal to 1.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductDimensions  
Base Table: Gen_Product_Dimensions  
API access:  ReadWrite  

## Visualization
Display Format: {Product.Name:T}  
Search Members: Product.Name  
Name Member: Product.Name  
Category:  Definitions  
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
| [ConvertToBaseDivisor](General.Products.ProductDimensions.md#converttobasedivisor) | decimal (9, 3) | This was intended to be the divisor, but due to a historical bug actually contains the multiplier of the convertion ratio from the non-base measurement category to the base measurement category. This should be automatically calculated by the system.[Required] 
| [ConvertToBaseMultiplier](General.Products.ProductDimensions.md#converttobasemultiplier) | decimal (9, 3) | This was intended to be the multiplier, but due to a historical bug actually contains the divisor of the convertion ratio from the non-base measurement category to the base measurement category. This should be automatically calculated by the system.[Required] 
| [DestQuantity](General.Products.ProductDimensions.md#destquantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity in some of the base units, that equals Source_Quantity[Unit: DestQuantityUnit] [Required] [Default(1)] 
| [SourceQuantity](General.Products.ProductDimensions.md#sourcequantity) | [Quantity (9, 3)](../data-types.md#quantity) | The quantity in the non-base unit[Unit: SourceQuantityUnit] [Required] [Default(1)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DestQuantityUnit](General.Products.ProductDimensions.md#destquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Dest_Quantity. Should be one of the units of the base measurement category of the product |
| [MeasurementCategory](General.Products.ProductDimensions.md#measurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) | The measurement category of Source Quantity Unit. For each product, only one conversion ratio can be specified for a measurement category. |
| [Product](General.Products.ProductDimensions.md#product) | [Products](General.Products.Products.md) | The product for which we specify conversion ratios |
| [SourceQuantityUnit](General.Products.ProductDimensions.md#sourcequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The non-base measurement unit for which we specify convertion ratio |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductDimensions.md#id) | guid |  
| [ObjectVersion](General.Products.ProductDimensions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductDimensions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConvertToBaseDivisor

This was intended to be the divisor, but due to a historical bug actually contains the multiplier of the convertion ratio from the non-base measurement category to the base measurement category. This should be automatically calculated by the system.[Required]

Type: **decimal (9, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

Back-End Default Expression:  
`( ( obj.DestQuantity.Value * obj.DestQuantityUnit.Multiplier) * obj.SourceQuantityUnit.Divisor)`

### ConvertToBaseMultiplier

This was intended to be the multiplier, but due to a historical bug actually contains the divisor of the convertion ratio from the non-base measurement category to the base measurement category. This should be automatically calculated by the system.[Required]

Type: **decimal (9, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

Back-End Default Expression:  
`( ( obj.SourceQuantity.Value * obj.SourceQuantityUnit.Multiplier) * obj.DestQuantityUnit.Divisor)`

### DestQuantity

Quantity in some of the base units, that equals Source_Quantity[Unit: DestQuantityUnit] [Required] [Default(1)]

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### SourceQuantity

The quantity in the non-base unit[Unit: SourceQuantityUnit] [Required] [Default(1)]

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
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

### DestQuantityUnit

The measurement unit of Dest_Quantity. Should be one of the units of the base measurement category of the product

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MeasurementCategory

The measurement category of Source Quantity Unit. For each product, only one conversion ratio can be specified for a measurement category.

Type: **[MeasurementCategories](General.Products.MeasurementCategories.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SourceQuantityUnit.MeasurementCategory`

Front-End Recalc Expressions:  
`obj.SourceQuantityUnit.MeasurementCategory`
### Product

The product for which we specify conversion ratios

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SourceQuantityUnit

The non-base measurement unit for which we specify convertion ratio

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
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

[!list limit=1000 erp.entity=General.Products.ProductDimensions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductDimensions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductDimensions

Domain API Entity Type: 
General_Products_ProductDimension

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductDimensions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductDimensions?$top=10>

