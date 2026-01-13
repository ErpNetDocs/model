---
uid: Applications.Service.ServiceActivityMaterials
---
# Applications.Service.ServiceActivityMaterials Entity

**Namespace:** [Applications.Service](Applications.Service.md)  

Contains the materials, which were actually used during the service activity (repair). Entity: Srv_Service_Activity_Materials

## Default Visualization
Default Display Text Format:  
_{LineNo}. {ServiceActivity.DocumentNo} {Product}_  
Default Search Members:  
_ServiceActivity.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  
Aggregate Root:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CoveredByGuarantee](Applications.Service.ServiceActivityMaterials.md#coveredbyguarantee) | boolean | True when the used material is covered by the guarantee. `Required` `Default(false)` 
| [DisplayText](Applications.Service.ServiceActivityMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Service.ServiceActivityMaterials.md#id) | guid |  
| [LineNo](Applications.Service.ServiceActivityMaterials.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` 
| [ObjectVersion](Applications.Service.ServiceActivityMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Applications.Service.ServiceActivityMaterials.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity of the product, that was used. `Unit: QuantityUnit` `Required` 
| [QuantityBase](Applications.Service.ServiceActivityMaterials.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [StandardQuantityBase](Applications.Service.ServiceActivityMaterials.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.Service.ServiceActivityMaterials.md#document) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` |
| [LineStore](Applications.Service.ServiceActivityMaterials.md#linestore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which the product was taken. null = use the store from the header. `Filter(multi eq)` |
| [Lot](Applications.Service.ServiceActivityMaterials.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product used as material. null means that the lot is unknown or will be specified at a later stage (in a store order. etc.). `Filter(multi eq)` `Introduced in version 25.1.1.39` |
| [Product](Applications.Service.ServiceActivityMaterials.md#product) | [Products](General.Products.Products.md) | The product, which was used as material. `Required` `Filter(multi eq)` |
| [QuantityUnit](Applications.Service.ServiceActivityMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. Initially is set to the default unit for the product. `Required` `Filter(multi eq)` |
| [SerialNumber](Applications.Service.ServiceActivityMaterials.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the product used as material. null means that the number is unknown or will be specified at a later stage (in a store order, etc.). `Filter(multi eq)` `Introduced in version 25.1.1.26` |
| [ServiceActivity](Applications.Service.ServiceActivityMaterials.md#serviceactivity) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` `Owner` |
| [ServiceObject](Applications.Service.ServiceActivityMaterials.md#serviceobject) | [ServiceObjects](Applications.Service.ServiceObjects.md) (nullable) | The service object for which the material is used. null means unkown object or N/A. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ServiceActivity<br />AgreedMaterials | [ServiceActivityAgreedMaterials](Applications.Service.ServiceActivityAgreedMaterials.md) | List of `ServiceActivity<br />AgreedMaterial`(Applications.Service.ServiceActivity<br />AgreedMaterials.md) child objects, based on the `Applications.Service.ServiceActivity<br />AgreedMaterial.ServiceActivityMaterial`(Applications.Service.ServiceActivity<br />AgreedMaterials.md#serviceactivitymaterial) back reference 


## Attribute Details

### CoveredByGuarantee

True when the used material is covered by the guarantee. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
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

### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ServiceActivity.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ServiceActivity.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

Quantity of the product, that was used. `Unit: QuantityUnit` `Required`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

## Reference Details

### Document

The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)`

_Type_: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LineStore

The store from which the product was taken. null = use the store from the header. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ServiceActivity.Store`

_Front-End Recalc Expressions:_  
`obj.ServiceActivity.Store`
### Lot

The lot of the product used as material. null means that the lot is unknown or will be specified at a later stage (in a store order. etc.). `Filter(multi eq)` `Introduced in version 25.1.1.39`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The product, which was used as material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. Initially is set to the default unit for the product. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### SerialNumber

The serial number of the product used as material. null means that the number is unknown or will be specified at a later stage (in a store order, etc.). `Filter(multi eq)` `Introduced in version 25.1.1.26`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ServiceActivity

The <see cref="ServiceActivity"/> to which this ServiceActivityMaterial belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ServiceObject

The service object for which the material is used. null means unkown object or N/A. `Filter(multi eq)`

_Type_: **[ServiceObjects](Applications.Service.ServiceObjects.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ServiceActivity.DefaultServiceObject`

_Front-End Recalc Expressions:_  
`obj.ServiceActivity.DefaultServiceObject`

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

