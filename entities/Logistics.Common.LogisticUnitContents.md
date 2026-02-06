---
uid: Logistics.Common.LogisticUnitContents
---
# Logistics.Common.LogisticUnitContents


Theoretical or actual content of a logistic unit.

## General
Namespace: [Logistics.Common](Logistics.Common.md)  
Repository: Logistics.Common.LogisticUnitContents  
Base Table: Log_Logistic_Unit_Contents  
Introduced In Version: 21.1.0.77  
API access:  ReadWrite  

## Renames

Old name: Logistics.LogisticUnitContents  
New name: Logistics.Common.LogisticUnitContents  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {LogisticUnit.SerialCode}  
Search Members: LotNumber; LogisticUnit.SerialCode  
Code Member: LotNumber  
Name Member: LogisticUnit.SerialCode  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  
Aggregate Root:  
[Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseQuantity](Logistics.Common.LogisticUnitContents.md#basequantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, expressed in the base measurement category of the product. 
| [ExpirationDate](Logistics.Common.LogisticUnitContents.md#expirationdate) | date __nullable__ | Expiration date of the goods. NULL means unknown or N/A. 
| [GrossWeight](Logistics.Common.LogisticUnitContents.md#grossweight) | decimal (12, 3) __nullable__ | Gross weight in kilograms (kg). NULL means unknown. 
| [LineNo](Logistics.Common.LogisticUnitContents.md#lineno) | int32 | Consecutive position within the logistic unit. 
| [LotNumber](Logistics.Common.LogisticUnitContents.md#lotnumber) | string (32) __nullable__ | The production lot number. NULL means unknown. 
| [Notes](Logistics.Common.LogisticUnitContents.md#notes) | string (max) __nullable__ | Notes for this LogisticUnitContent. 
| [Quantity](Logistics.Common.LogisticUnitContents.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity of the product in the logistic unit. Expressed in the specified measurement unit. 
| [StandardQuantity](Logistics.Common.LogisticUnitContents.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, expessed in the standard measurement unit of the product. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LogisticUnit](Logistics.Common.LogisticUnitContents.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) | The containing logistic unit. |
| [Lot](Logistics.Common.LogisticUnitContents.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product. Null means unknown or that the product does not use lots. |
| [Product](Logistics.Common.LogisticUnitContents.md#product) | [Products](General.Products.Products.md) | The product, which is contained in the logistic unit. |
| [ProductVariant](Logistics.Common.LogisticUnitContents.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant of the product. Null means unknown or that the product does not have variants. |
| [QuantityUnit](Logistics.Common.LogisticUnitContents.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity. |
| [SerialNumber](Logistics.Common.LogisticUnitContents.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the product. Null means unknown or that product is not serialized. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Common.LogisticUnitContents.md#id) | guid |  
| [ObjectVersion](Logistics.Common.LogisticUnitContents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Common.LogisticUnitContents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BaseQuantity

The quantity, expressed in the base measurement category of the product.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.BaseQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ExpirationDate

Expiration date of the goods. NULL means unknown or N/A.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### GrossWeight

Gross weight in kilograms (kg). NULL means unknown.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive position within the logistic unit.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.LogisticUnit.Contents.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.LogisticUnit.Contents.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### LotNumber

The production lot number. NULL means unknown.

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this LogisticUnitContent.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Quantity

Quantity of the product in the logistic unit. Expressed in the specified measurement unit.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardQuantity

The quantity, expessed in the standard measurement unit of the product.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.BaseQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
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

### LogisticUnit

The containing logistic unit.

Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Lot

The lot of the product. Null means unknown or that the product does not use lots.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, which is contained in the logistic unit.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The product variant of the product. Null means unknown or that the product does not have variants.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of the quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SerialNumber

The serial number of the product. Null means unknown or that product is not serialized.

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

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnitContents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnitContents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Common_LogisticUnitContents

Domain API Entity Type: 
Logistics_Common_LogisticUnitContent

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Common_LogisticUnitContents?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Common_LogisticUnitContents?$top=10>

