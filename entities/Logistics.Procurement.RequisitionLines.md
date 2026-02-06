---
uid: Logistics.Procurement.RequisitionLines
---
# Logistics.Procurement.RequisitionLines


Detail lines of Requistions.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.RequisitionLines  
Base Table: Scm_Requisition_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {Requisition.DocumentNo} {Requisition.DocumentType.TypeName:T}  
Search Members: Requisition.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.Requisitions](Logistics.Procurement.Requisitions.md)  
Aggregate Root:  
[Logistics.Procurement.Requisitions](Logistics.Procurement.Requisitions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Procurement.RequisitionLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineNo](Logistics.Procurement.RequisitionLines.md#lineno) | int32 | Line number, unique within the Requisition. Usually is increasing number like 10, 20, 30, ... when initially entering the Requisition (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Logistics.Procurement.RequisitionLines.md#notes) | string (254) __nullable__ | Notes for this RequisitionLine. 
| [ProductDescription](Logistics.Procurement.RequisitionLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The description of the required product. When Product is set, this is copied initially from the product name. When Product is null, this contains the manually entered description of the desired product. 
| [Quantity](Logistics.Procurement.RequisitionLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The required quantity of the product.[Unit: QuantityUnit] [Required] [Default(0)] [Filter(ge;le)] 
| [QuantityBase](Logistics.Procurement.RequisitionLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [ReadOnly] 
| [RequiredDeliveryDate](Logistics.Procurement.RequisitionLines.md#requireddeliverydate) | datetime | The desired delivery date. Initially set to the required delivery date in the requisition header or if it is empty - to the document date plus the products lead time.[Required] [Filter(ge;le)] 
| [StandardQuantityBase](Logistics.Procurement.RequisitionLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Procurement.RequisitionLines.md#document) | [Requisitions](Logistics.Procurement.Requisitions.md) | The owner document. The <see cref="Requisition"/> to which this RequisitionLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Procurement.RequisitionLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | When not null, indicates a specific lot should be purchased. |
| [Product](Logistics.Procurement.RequisitionLines.md#product) | [Products](General.Products.Products.md) (nullable) | The required product. When null, the product is unknown to the requisitor and only a description is supplied to the purchase department. |
| [QuantityUnit](Logistics.Procurement.RequisitionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [Requisition](Logistics.Procurement.RequisitionLines.md#requisition) | [Requisitions](Logistics.Procurement.Requisitions.md) | The <see cref="Requisition"/> to which this RequisitionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [SuggestedSupplier](Logistics.Procurement.RequisitionLines.md#suggestedsupplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | When the requisitor knows the supplier or has a supplier preference it is denoted in this field. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.RequisitionLines.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.RequisitionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Procurement.RequisitionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineNo

Line number, unique within the Requisition. Usually is increasing number like 10, 20, 30, ... when initially entering the Requisition (in order to allow insertions with adjustment documents). `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Requisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Requisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this RequisitionLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### ProductDescription

The description of the required product. When Product is set, this is copied initially from the product name. When Product is null, this contains the manually entered description of the desired product.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

The required quantity of the product.[Unit: QuantityUnit] [Required] [Default(0)] [Filter(ge;le)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement category of the product.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [ReadOnly]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### RequiredDeliveryDate

The desired delivery date. Initially set to the required delivery date in the requisition header or if it is empty - to the document date plus the products lead time.[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
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

### Document

The owner document. The <see cref="Requisition"/> to which this RequisitionLine belongs. `Required` `Filter(multi eq)`

Type: **[Requisitions](Logistics.Procurement.Requisitions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

When not null, indicates a specific lot should be purchased.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The required product. When null, the product is unknown to the requisitor and only a description is supplied to the purchase department.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Requisition

The <see cref="Requisition"/> to which this RequisitionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Requisitions](Logistics.Procurement.Requisitions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SuggestedSupplier

When the requisitor knows the supplier or has a supplier preference it is denoted in this field.

Type: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Logistics.Procurement.RequisitionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.RequisitionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_RequisitionLines

Domain API Entity Type: 
Logistics_Procurement_RequisitionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_RequisitionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_RequisitionLines?$top=10>

