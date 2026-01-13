---
uid: Production.ShopFloor.OutputOrderDistributedMaterialConsumptions
---
# Production.ShopFloor.OutputOrderDistributedMaterialConsumptions Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

Contains the quantity of materials distributed over the output order lines. Entity: Prd_Output_Order_Distributed_Material_Consumptions

## Default Visualization
Default Display Text Format:  
_{OutputOrderLine.OutputOrder.EntityName}_  
Default Search Members:  
_OutputOrderLine.OutputOrder.EntityName_  
Name Data Member:  
_OutputOrderLine.OutputOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.OutputOrderLines](Production.ShopFloor.OutputOrderLines.md)  
Aggregate Root:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedCost](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#consumedcost) | [Amount (14, 2)](../data-types.md#amount) | Cost of the actually issued Consumed_Quantity. `Currency: ConsumptionOrderLine.GetIssueCurrency()` `Required` `Default(0)` `ReadOnly` 
| [ConsumedQuantity](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#consumedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Part of the quantity in the consumption order line which was used for the product in the output order line. `Unit: ConsumptionOrderLine.ConsumedQuantityUnit` `Required` `Default(0)` `ReadOnly` 
| [DisplayText](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumptionOrderLine](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#consumptionorderline) | [ConsumptionOrderLines](Production.ShopFloor.ConsumptionOrderLines.md) | Consumption order line which requested the Consumed_Quantity. `Required` `Filter(multi eq)` `ReadOnly` |
| [OutputOrderLine](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md#outputorderline) | [OutputOrderLines](Production.ShopFloor.OutputOrderLines.md) | The output order line for which the distribution is recorded. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |


## Attribute Details

### ConsumedCost

Cost of the actually issued Consumed_Quantity. `Currency: ConsumptionOrderLine.GetIssueCurrency()` `Required` `Default(0)` `ReadOnly`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ConsumedQuantity

Part of the quantity in the consumption order line which was used for the product in the output order line. `Unit: ConsumptionOrderLine.ConsumedQuantityUnit` `Required` `Default(0)` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### ConsumptionOrderLine

Consumption order line which requested the Consumed_Quantity. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[ConsumptionOrderLines](Production.ShopFloor.ConsumptionOrderLines.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OutputOrderLine

The output order line for which the distribution is recorded. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[OutputOrderLines](Production.ShopFloor.OutputOrderLines.md)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderDistributedMaterialConsumptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderDistributedMaterialConsumptions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_OutputOrderDistributedMaterialConsumptions

Domain API Entity Type: 
Production_ShopFloor_OutputOrderDistributedMaterialConsumption

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_OutputOrderDistributedMaterialConsumptions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_OutputOrderDistributedMaterialConsumptions?$top=10>

