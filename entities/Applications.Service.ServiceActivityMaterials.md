---
uid: Applications.Service.ServiceActivityMaterials
---
# Applications.Service.ServiceActivityMaterials


Contains the materials, which were actually used during the service activity (repair).

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceActivityMaterials  
Base Table: Srv_Service_Activity_Materials  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {ServiceActivity.DocumentNo} {Product}  
Search Members: ServiceActivity.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  
Aggregate Root:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CoveredByGuarantee](Applications.Service.ServiceActivityMaterials.md#coveredbyguarantee) | boolean | True when the used material is covered by the guarantee.`Required` `Default(false)` 
| [LineNo](Applications.Service.ServiceActivityMaterials.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc.`Required` 
| [Quantity](Applications.Service.ServiceActivityMaterials.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity of the product, that was used`Unit: QuantityUnit` `Required` 
| [QuantityBase](Applications.Service.ServiceActivityMaterials.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [StandardQuantityBase](Applications.Service.ServiceActivityMaterials.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.Service.ServiceActivityMaterials.md#document) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` |
| [LineStore](Applications.Service.ServiceActivityMaterials.md#linestore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which the product was taken. If empty - use the store from the service activity |
| [Lot](Applications.Service.ServiceActivityMaterials.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product used as material. NULL means that the lot is unknown or will be specified at a later stage (in a store order. etc.) |
| [Product](Applications.Service.ServiceActivityMaterials.md#product) | [Products](General.Products.Products.md) | The product, which was used as material. |
| [QuantityUnit](Applications.Service.ServiceActivityMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. Initially is set to the default unit for the product |
| [SerialNumber](Applications.Service.ServiceActivityMaterials.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the product used as material. NULL means that the number is unknown or will be specified at a later stage (in a store order, etc.) |
| [ServiceActivity](Applications.Service.ServiceActivityMaterials.md#serviceactivity) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` `Owner` |
| [ServiceObject](Applications.Service.ServiceActivityMaterials.md#serviceobject) | [ServiceObjects](Applications.Service.ServiceObjects.md) (nullable) | The service object for which the material from this line is used. If service object is unknown or there isn't service object then this field should be blank. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceActivityMaterials.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceActivityMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Service.ServiceActivityMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ServiceActivity<br />AgreedMaterials | [ServiceActivityAgreedMaterials](Applications.Service.ServiceActivityAgreedMaterials.md) | List of `ServiceActivity<br />AgreedMaterial`(Applications.Service.ServiceActivity<br />AgreedMaterials.md) child objects, based on the `Applications.Service.ServiceActivity<br />AgreedMaterial.ServiceActivityMaterial`(Applications.Service.ServiceActivity<br />AgreedMaterials.md#serviceactivitymaterial) back reference 


## Attribute Details

### CoveredByGuarantee

True when the used material is covered by the guarantee.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ServiceActivity.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ServiceActivity.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Quantity

Quantity of the product, that was used`Unit: QuantityUnit` `Required`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement category of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

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

The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)`

Type: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineStore

The store from which the product was taken. If empty - use the store from the service activity

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ServiceActivity.Store`

Front-End Recalc Expressions:  
`obj.ServiceActivity.Store`
### Lot

The lot of the product used as material. NULL means that the lot is unknown or will be specified at a later stage (in a store order. etc.)

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product, which was used as material.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. Initially is set to the default unit for the product

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SerialNumber

The serial number of the product used as material. NULL means that the number is unknown or will be specified at a later stage (in a store order, etc.)

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceActivity

The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ServiceObject

The service object for which the material from this line is used. If service object is unknown or there isn't service object then this field should be blank.

Type: **[ServiceObjects](Applications.Service.ServiceObjects.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ServiceActivity.DefaultServiceObject`

Front-End Recalc Expressions:  
`obj.ServiceActivity.DefaultServiceObject`

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

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceActivityMaterials

Domain API Entity Type: 
Applications_Service_ServiceActivityMaterial

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceActivityMaterials?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceActivityMaterials?$top=10>

