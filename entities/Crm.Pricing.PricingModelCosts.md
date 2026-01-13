---
uid: Crm.Pricing.PricingModelCosts
---
# Crm.Pricing.PricingModelCosts Entity

**Namespace:** [Crm.Pricing](Crm.Pricing.md)  

List of costs, associated with a pricing model. Entity: Crm_Pricing_Model_Costs

## Default Visualization
Default Display Text Format:  
_{PricingModel.Name}_  
Default Search Members:  
_PricingModel.Name_  
Name Data Member:  
_PricingModel.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  
Aggregate Root:  
[Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountPercent](Crm.Pricing.PricingModelCosts.md#amountpercent) | decimal (6, 5) __nullable__ | Used when the cost is calculated as percent of the amount. null when the cost is calculated in a different way. 
| [AmountPerUnit](Crm.Pricing.PricingModelCosts.md#amountperunit) | [Amount (9, 2)](../data-types.md#amount) __nullable__ | Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement_Unit_Id. null when the cost is calculated in a different way. `Currency: PricingModel.Currency` 
| [DisplayText](Crm.Pricing.PricingModelCosts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pricing.PricingModelCosts.md#id) | guid |  
| [LineNo](Crm.Pricing.PricingModelCosts.md#lineno) | int32 | The consequtive number of the cost within the pricing model. `Required` 
| [ObjectVersion](Crm.Pricing.PricingModelCosts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostType](Crm.Pricing.PricingModelCosts.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The cost type, which is listed for the pricing model. `Required` `Filter(multi eq)` |
| [MeasurementUnit](Crm.Pricing.PricingModelCosts.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit for which the Amount_Per_Unit is defined. null when the cost is calculated in a different way. `Filter(multi eq)` |
| [PricingModel](Crm.Pricing.PricingModelCosts.md#pricingmodel) | [PricingModels](Crm.Pricing.PricingModels.md) | Pricing model, for which the cost is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### AmountPercent

Used when the cost is calculated as percent of the amount. null when the cost is calculated in a different way.

_Type_: **decimal (6, 5) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### AmountPerUnit

Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement_Unit_Id. null when the cost is calculated in a different way. `Currency: PricingModel.Currency`

_Type_: **[Amount (9, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
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

The consequtive number of the cost within the pricing model. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.PricingModel.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.PricingModel.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### CostType

The cost type, which is listed for the pricing model. `Required` `Filter(multi eq)`

_Type_: **[CostTypes](Finance.Cost.CostTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MeasurementUnit

The measurement unit for which the Amount_Per_Unit is defined. null when the cost is calculated in a different way. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PricingModel

Pricing model, for which the cost is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[PricingModels](Crm.Pricing.PricingModels.md)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.PricingModelCosts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.PricingModelCosts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_PricingModelCosts

Domain API Entity Type: 
Crm_Pricing_PricingModelCost

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_PricingModelCosts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PricingModelCosts?$top=10>

