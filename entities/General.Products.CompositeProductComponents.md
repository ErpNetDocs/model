---
uid: General.Products.CompositeProductComponents
---
# General.Products.CompositeProductComponents


Separate components of a product which are packaged and stored individually. Used when a single product is stored in multiple packages.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.CompositeProductComponents  
Base Table: Log_Composite_Product_Components  
Introduced In Version: 23.1.0.15  
API access:  ReadWrite  

## Renames

Old name: Logistics.CompositeProductComponents  
New name: General.Products.CompositeProductComponents  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {ComponentNo}: {ComponentProduct}  
Search Members: CompositeProduct.Name  
Name Member: CompositeProduct.Name  
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
| [ComponentNo](General.Products.CompositeProductComponents.md#componentno) | int32 | Consecutive number of the component within this composite product.[Required] [Filter(multi eq)] 
| [FromDate](General.Products.CompositeProductComponents.md#fromdate) | date __nullable__ | When set, specifies the activation date of the component for this product.[Filter(eq;ge;le)] 
| [IsActive](General.Products.CompositeProductComponents.md#isactive) | boolean | Indicates whether the component is currently active for this composite product.[Required] [Default(true)] [Filter(eq)] 
| [Notes](General.Products.CompositeProductComponents.md#notes) | string (max) __nullable__ | Notes for this composite product component. 
| [Quantity](General.Products.CompositeProductComponents.md#quantity) | decimal (12, 3) | The number of packages of this component that are needed to compose the product.[Required] [Default(1)] [Filter(multi eq;ge;le)] 
| [ToDate](General.Products.CompositeProductComponents.md#todate) | date __nullable__ | When set, specifies the de-activation date of the component for this product.[Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ComponentProduct](General.Products.CompositeProductComponents.md#componentproduct) | [Products](General.Products.Products.md) | The product which is a component of the composite product. |
| [CompositeProduct](General.Products.CompositeProductComponents.md#compositeproduct) | [Products](General.Products.Products.md) | The product of which the current component is a part. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.CompositeProductComponents.md#id) | guid |  
| [ObjectVersion](General.Products.CompositeProductComponents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.CompositeProductComponents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ComponentNo

Consecutive number of the component within this composite product.[Required] [Filter(multi eq)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.CompositeProduct.CompositeProductComponents.Select( c => c.ComponentNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.CompositeProduct.CompositeProductComponents.Select( c => c.ComponentNo).DefaultIfEmpty( 0).Max( ) + 1)`
### FromDate

When set, specifies the activation date of the component for this product.[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the component is currently active for this composite product.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this composite product component.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Quantity

The number of packages of this component that are needed to compose the product.[Required] [Default(1)] [Filter(multi eq;ge;le)]

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### ToDate

When set, specifies the de-activation date of the component for this product.[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
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

### ComponentProduct

The product which is a component of the composite product.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CompositeProduct

The product of which the current component is a part.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=General.Products.CompositeProductComponents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.CompositeProductComponents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_CompositeProductComponents

Domain API Entity Type: 
General_Products_CompositeProductComponent

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_CompositeProductComponents?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_CompositeProductComponents?$top=10>

