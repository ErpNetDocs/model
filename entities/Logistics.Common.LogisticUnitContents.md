---
uid: Logistics.Common.LogisticUnitContents
---
# Logistics.Common.LogisticUnitContents Entity

**Namespace:** [Logistics.Common](Logistics.Common.md)  

Theoretical or actual content of a logistic unit. Entity: Log_Logistic_Unit_Contents (Introduced in version 21.1.0.77)

## Renames

Old name: **Logistics.LogisticUnitContents**  
New name: **Logistics.Common.LogisticUnitContents**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{LogisticUnit.SerialCode}_  
Default Search Members:  
_LotNumber; LogisticUnit.SerialCode_  
Code Data Member:  
_LotNumber_  
Name Data Member:  
_LogisticUnit.SerialCode_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  
Aggregate Root:  
[Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseQuantity](Logistics.Common.LogisticUnitContents.md#basequantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, expressed in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` 
| [DisplayText](Logistics.Common.LogisticUnitContents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpirationDate](Logistics.Common.LogisticUnitContents.md#expirationdate) | date __nullable__ | Expiration date of the goods. null means unknown or N/A. `Filter(multi eq;ge;le)` 
| [GrossWeight](Logistics.Common.LogisticUnitContents.md#grossweight) | decimal (12, 3) __nullable__ | Gross weight in kilograms (kg). null means unknown. `Filter(eq;ge;le)` 
| [Id](Logistics.Common.LogisticUnitContents.md#id) | guid |  
| [LineNo](Logistics.Common.LogisticUnitContents.md#lineno) | int32 | Consecutive position within the logistic unit. `Required` `Filter(multi eq)` 
| [LotNumber](Logistics.Common.LogisticUnitContents.md#lotnumber) | string (32) __nullable__ | The production lot number. null means unknown. `Filter(multi eq;like)` 
| [Notes](Logistics.Common.LogisticUnitContents.md#notes) | string (max) __nullable__ | Notes for this LogisticUnitContent. 
| [ObjectVersion](Logistics.Common.LogisticUnitContents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Common.LogisticUnitContents.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity of the product in the logistic unit. Expressed in the specified measurement unit. `Unit: QuantityUnit` `Required` `Filter(multi eq;ge;le)` 
| [StandardQuantity](Logistics.Common.LogisticUnitContents.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, expessed in the standard measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LogisticUnit](Logistics.Common.LogisticUnitContents.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) | The containing logistic unit. `Required` `Filter(multi eq)` `Owner` |
| [Lot](Logistics.Common.LogisticUnitContents.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product. Null means unknown or that the product does not use lots. `Filter(multi eq)` `Introduced in version 23.1.2.0` |
| [Product](Logistics.Common.LogisticUnitContents.md#product) | [Products](General.Products.Products.md) | The product, which is contained in the logistic unit. `Required` `Filter(multi eq)` |
| [ProductVariant](Logistics.Common.LogisticUnitContents.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant of the product. Null means unknown or that the product does not have variants. `Filter(multi eq)` `Introduced in version 23.1.2.0` |
| [QuantityUnit](Logistics.Common.LogisticUnitContents.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity. `Required` `Filter(multi eq)` |
| [SerialNumber](Logistics.Common.LogisticUnitContents.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the product. Null means unknown or that product is not serialized. `Filter(multi eq)` `Introduced in version 23.1.2.0` |


## Attribute Details

### BaseQuantity

The quantity, expressed in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.BaseQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpirationDate

Expiration date of the goods. null means unknown or N/A. `Filter(multi eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### GrossWeight

Gross weight in kilograms (kg). null means unknown. `Filter(eq;ge;le)`

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive position within the logistic unit. `Required` `Filter(multi eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.LogisticUnit.Contents.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.LogisticUnit.Contents.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### LotNumber

The production lot number. null means unknown. `Filter(multi eq;like)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this LogisticUnitContent.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

Quantity of the product in the logistic unit. Expressed in the specified measurement unit. `Unit: QuantityUnit` `Required` `Filter(multi eq;ge;le)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardQuantity

The quantity, expessed in the standard measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.BaseQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

## Reference Details

### LogisticUnit

The containing logistic unit. `Required` `Filter(multi eq)` `Owner`

_Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Lot

The lot of the product. Null means unknown or that the product does not use lots. `Filter(multi eq)` `Introduced in version 23.1.2.0`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, which is contained in the logistic unit. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

The product variant of the product. Null means unknown or that the product does not have variants. `Filter(multi eq)` `Introduced in version 23.1.2.0`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of the quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### SerialNumber

The serial number of the product. Null means unknown or that product is not serialized. `Filter(multi eq)` `Introduced in version 23.1.2.0`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
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

