---
uid: Applications.Rental.LeaseContractLineConsumables
---
# Applications.Rental.LeaseContractLineConsumables


Contains the consumables, which are sold accompanying asset rentals.

## General
Namespace: [Applications.Rental](Applications.Rental.md)  
Repository: Applications.Rental.LeaseContractLineConsumables  
Base Table: Rent_Lease_Contract_Line_Consumables  
API access:  ReadWrite  

## Visualization
Display Format: {LeaseLine.LeaseContract.EntityName}  
Search Members: LeaseLine.LeaseContract.EntityName  
Name Member: LeaseLine.LeaseContract.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.LeaseContractLines](Applications.Rental.LeaseContractLines.md)  
Aggregate Root:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumableQuantity](Applications.Rental.LeaseContractLineConsumables.md#consumablequantity) | [Quantity (12, 3)](../data-types.md#quantity) | Specifies what quantity of the current consumable is given.[Unit: ConsumableQuantityUnit] [Required] [Default(0)] 
| [LineNo](Applications.Rental.LeaseContractLineConsumables.md#lineno) | int32 | Consecutive number of the consumable within the lease contract line.[Required] [Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumableQuantityUnit](Applications.Rental.LeaseContractLineConsumables.md#consumablequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Consumable Quantity. |
| [LeaseLine](Applications.Rental.LeaseContractLineConsumables.md#leaseline) | [LeaseContractLines](Applications.Rental.LeaseContractLines.md) | Lease line with which the current consumable is given. |
| [Product](Applications.Rental.LeaseContractLineConsumables.md#product) | [Products](General.Products.Products.md) | The consumable to be sold accompanying the asset. |
| [Store](Applications.Rental.LeaseContractLineConsumables.md#store) | [Stores](Logistics.Inventory.Stores.md) | Store from which the consumable is issued. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Rental.LeaseContractLineConsumables.md#id) | guid |  
| [ObjectVersion](Applications.Rental.LeaseContractLineConsumables.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Rental.LeaseContractLineConsumables.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConsumableQuantity

Specifies what quantity of the current consumable is given.[Unit: ConsumableQuantityUnit] [Required] [Default(0)]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive number of the consumable within the lease contract line.[Required] [Filter(eq;ge;le)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.LeaseLine.Consumables.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.LeaseLine.Consumables.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
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

### ConsumableQuantityUnit

The measurement unit of Consumable Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LeaseLine

Lease line with which the current consumable is given.

Type: **[LeaseContractLines](Applications.Rental.LeaseContractLines.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Product

The consumable to be sold accompanying the asset.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

Store from which the consumable is issued.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
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

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLineConsumables erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLineConsumables erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Rental_LeaseContractLineConsumables

Domain API Entity Type: 
Applications_Rental_LeaseContractLineConsumable

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Rental_LeaseContractLineConsumables?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Rental_LeaseContractLineConsumables?$top=10>

