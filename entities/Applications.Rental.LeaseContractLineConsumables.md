---
uid: Applications.Rental.LeaseContractLineConsumables
---
# Applications.Rental.LeaseContractLineConsumables Entity

**Namespace:** [Applications.Rental](Applications.Rental.md)  

Contains the consumables, which are sold accompanying asset rentals. Entity: Rent_Lease_Contract_Line_Consumables

## Default Visualization
Default Display Text Format:  
_{LeaseLine.LeaseContract.EntityName}_  
Default Search Members:  
_LeaseLine.LeaseContract.EntityName_  
Name Data Member:  
_LeaseLine.LeaseContract.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.LeaseContractLines](Applications.Rental.LeaseContractLines.md)  
Aggregate Root:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumableQuantity](Applications.Rental.LeaseContractLineConsumables.md#consumablequantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity sold of the consumable. `Unit: ConsumableQuantityUnit` `Required` `Default(0)` 
| [DisplayText](Applications.Rental.LeaseContractLineConsumables.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Rental.LeaseContractLineConsumables.md#id) | guid |  
| [LineNo](Applications.Rental.LeaseContractLineConsumables.md#lineno) | int32 | Consecutive number of the consumable within the lease contract line. `Required` `Filter(eq;ge;le)` 
| [ObjectVersion](Applications.Rental.LeaseContractLineConsumables.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumableQuantityUnit](Applications.Rental.LeaseContractLineConsumables.md#consumablequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Consumable Quantity. `Required` `Filter(multi eq)` |
| [LeaseLine](Applications.Rental.LeaseContractLineConsumables.md#leaseline) | [LeaseContractLines](Applications.Rental.LeaseContractLines.md) | Lease line with which the current consumable is given. `Required` `Filter(multi eq)` `Owner` |
| [Product](Applications.Rental.LeaseContractLineConsumables.md#product) | [Products](General.Products.Products.md) | The consumable to be sold accompanying the asset. `Required` `Filter(multi eq)` |
| [Store](Applications.Rental.LeaseContractLineConsumables.md#store) | [Stores](Logistics.Inventory.Stores.md) | Store from which the consumable is issued. `Required` `Filter(multi eq)` |


## Attribute Details

### ConsumableQuantity

The quantity sold of the consumable. `Unit: ConsumableQuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive number of the consumable within the lease contract line. `Required` `Filter(eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.LeaseLine.Consumables.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.LeaseLine.Consumables.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### ConsumableQuantityUnit

The measurement unit of Consumable Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LeaseLine

Lease line with which the current consumable is given. `Required` `Filter(multi eq)` `Owner`

_Type_: **[LeaseContractLines](Applications.Rental.LeaseContractLines.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Product

The consumable to be sold accompanying the asset. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

Store from which the consumable is issued. `Required` `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
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

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLineConsumables erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLineConsumables erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Rental_LeaseContractLineConsumables?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Rental_LeaseContractLineConsumables?$top=10>

