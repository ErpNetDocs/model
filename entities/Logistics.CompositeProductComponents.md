---
uid: Logistics.CompositeProductComponents
---
# Logistics.CompositeProductComponents Entity

**Namespace:** [Logistics](Logistics.md)  

Separate components of a product which are packaged and stored individually. Used when a single product is stored in multiple packages. Entity: Log_Composite_Product_Components (Introduced in version 23.1.0.15)
## Renamed
**New name:** [General.Products.CompositeProductComponents](General.Products.CompositeProductComponents.md)  



## Default Visualization
Default Display Text Format:  
_{ComponentNo}: {ComponentProduct}_  
Default Search Members:  
_CompositeProduct.Name_  
Name Data Member:  
_CompositeProduct.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ComponentNo](Logistics.CompositeProductComponents.md#componentno) | int32 | Consecutive number of the component within this composite product. `Required` `Filter(multi eq)` 
| [DisplayText](Logistics.CompositeProductComponents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](Logistics.CompositeProductComponents.md#fromdate) | date __nullable__ | Starting date (inclusive) of the validity of the component. Null means that the component does not have an activation date. `Filter(eq;ge;le)` 
| [Id](Logistics.CompositeProductComponents.md#id) | guid |  
| [IsActive](Logistics.CompositeProductComponents.md#isactive) | boolean | Indicates whether the component is currently active for this composite product. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Logistics.CompositeProductComponents.md#notes) | string (max) __nullable__ | Notes for this composite product component. 
| [ObjectVersion](Logistics.CompositeProductComponents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.CompositeProductComponents.md#quantity) | decimal (12, 3) | The number of packages of this component that are needed to compose the product. `Required` `Default(1)` `Filter(multi eq;ge;le)` 
| [ToDate](Logistics.CompositeProductComponents.md#todate) | date __nullable__ | Ending date (inclusive) of the validity of the component. Null means that the component does not have a deactivation date. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ComponentProduct](Logistics.CompositeProductComponents.md#componentproduct) | [Products](General.Products.Products.md) | The product which is a component of the composite product. `Required` `Filter(multi eq)` |
| [CompositeProduct](Logistics.CompositeProductComponents.md#compositeproduct) | [Products](General.Products.Products.md) | The product of which the current component is a part. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ComponentNo

Consecutive number of the component within this composite product. `Required` `Filter(multi eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.CompositeProduct.CompositeProductComponents.Select( c => c.ComponentNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.CompositeProduct.CompositeProductComponents.Select( c => c.ComponentNo).DefaultIfEmpty( 0).Max( ) + 1)`
### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

Starting date (inclusive) of the validity of the component. Null means that the component does not have an activation date. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the component is currently active for this composite product. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this composite product component.

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

The number of packages of this component that are needed to compose the product. `Required` `Default(1)` `Filter(multi eq;ge;le)`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### ToDate

Ending date (inclusive) of the validity of the component. Null means that the component does not have a deactivation date. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ComponentProduct

The product which is a component of the composite product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CompositeProduct

The product of which the current component is a part. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Logistics.CompositeProductComponents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.CompositeProductComponents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_CompositeProductComponents?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_CompositeProductComponents?$top=10>

