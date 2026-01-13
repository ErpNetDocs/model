---
uid: Applications.Service.ServiceAgreementMaterials
---
# Applications.Service.ServiceAgreementMaterials Entity

**Namespace:** [Applications.Service](Applications.Service.md)  

Contains the free materials, included in the service agreement. Entity: Srv_Service_Agreement_Materials

## Default Visualization
Default Display Text Format:  
_{LineNo}. {ServiceAgreement.DocumentNo} {ServiceAgreement.DocumentType.TypeName:T}_  
Default Search Members:  
_ServiceAgreement.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  
Aggregate Root:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Applications.Service.ServiceAgreementMaterials.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Applications.Service.ServiceAgreementMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndDate](Applications.Service.ServiceAgreementMaterials.md#enddate) | datetime __nullable__ | End date to which the agreedment for the material is valid. For the agreement period, the material could be used free of charge in service activities. `Filter(ge;le)` 
| [Id](Applications.Service.ServiceAgreementMaterials.md#id) | guid |  
| [LineNo](Applications.Service.ServiceAgreementMaterials.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` 
| [ObjectVersion](Applications.Service.ServiceAgreementMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Applications.Service.ServiceAgreementMaterials.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity of the agreed material. `Unit: QuantityUnit` `Required` 
| [QuantityBase](Applications.Service.ServiceAgreementMaterials.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [StandardQuantityBase](Applications.Service.ServiceAgreementMaterials.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [StartDate](Applications.Service.ServiceAgreementMaterials.md#startdate) | datetime __nullable__ | Start date from which the agreedment for the material is valid. For the agreement period, the material could be used free of charge in service activities. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.Service.ServiceAgreementMaterials.md#document) | [ServiceAgreements](Applications.Service.ServiceAgreements.md) | The owner document. The <see cref="ServiceAgreement"/> to which this ServiceAgreementMaterial belongs. `Required` `Filter(multi eq)` |
| [Product](Applications.Service.ServiceAgreementMaterials.md#product) | [Products](General.Products.Products.md) | Paid or agreed in advance material that won't be invoiced after service activities. `Required` `Filter(multi eq)` |
| [QuantityUnit](Applications.Service.ServiceAgreementMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [ServiceAgreement](Applications.Service.ServiceAgreementMaterials.md#serviceagreement) | [ServiceAgreements](Applications.Service.ServiceAgreements.md) | The <see cref="ServiceAgreement"/> to which this ServiceAgreementMaterial belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

_Type_: **[Quantity](../data-types.md#quantity)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EndDate

End date to which the agreedment for the material is valid. For the agreement period, the material could be used free of charge in service activities. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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
`( obj.ServiceAgreement.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ServiceAgreement.Materials.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

Quantity of the agreed material. `Unit: QuantityUnit` `Required`

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
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StartDate

Start date from which the agreedment for the material is valid. For the agreement period, the material could be used free of charge in service activities. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="ServiceAgreement"/> to which this ServiceAgreementMaterial belongs. `Required` `Filter(multi eq)`

_Type_: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

Paid or agreed in advance material that won't be invoiced after service activities. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit)`
### ServiceAgreement

The <see cref="ServiceAgreement"/> to which this ServiceAgreementMaterial belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
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

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceAgreementMaterials

Domain API Entity Type: 
Applications_Service_ServiceAgreementMaterial

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceAgreementMaterials?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceAgreementMaterials?$top=10>

