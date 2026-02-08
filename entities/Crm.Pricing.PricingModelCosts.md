---
uid: Crm.Pricing.PricingModelCosts
---
# Crm.Pricing.PricingModelCosts


List of costs, associated with a pricing model

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.PricingModelCosts  
Base Table: Crm_Pricing_Model_Costs  
API access:  ReadWrite  

## Visualization
Display Format: {PricingModel.Name}  
Search Members: PricingModel.Name  
Name Member: PricingModel.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  
Aggregate Root:  
[Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountPercent](Crm.Pricing.PricingModelCosts.md#amountpercent) | decimal (6, 5) __nullable__ | Used when the cost is calculated as percent of the amount. NULL when the cost is calculated in a different way 
| [AmountPerUnit](Crm.Pricing.PricingModelCosts.md#amountperunit) | [Amount (9, 2)](../data-types.md#amount) __nullable__ | Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement Unit. NULL when the cost is calculated in a different way`Currency: PricingModel.Currency` 
| [LineNo](Crm.Pricing.PricingModelCosts.md#lineno) | int32 | The consequtive number of the cost within the pricing model`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostType](Crm.Pricing.PricingModelCosts.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The cost type, which is listed for the pricing model |
| [MeasurementUnit](Crm.Pricing.PricingModelCosts.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit for which the Amount_Per_Unit is defined. NULL when the cost is calculated in a different way |
| [PricingModel](Crm.Pricing.PricingModelCosts.md#pricingmodel) | [PricingModels](Crm.Pricing.PricingModels.md) | Pricing model, for which the cost is defined |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PricingModelCosts.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.PricingModelCosts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pricing.PricingModelCosts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AmountPercent

Used when the cost is calculated as percent of the amount. NULL when the cost is calculated in a different way

Type: **decimal (6, 5) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AmountPerUnit

Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement Unit. NULL when the cost is calculated in a different way`Currency: PricingModel.Currency`

Type: **[Amount (9, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

The consequtive number of the cost within the pricing model`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PricingModel.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.PricingModel.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
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

### CostType

The cost type, which is listed for the pricing model

Type: **[CostTypes](Finance.Cost.CostTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MeasurementUnit

The measurement unit for which the Amount_Per_Unit is defined. NULL when the cost is calculated in a different way

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PricingModel

Pricing model, for which the cost is defined

Type: **[PricingModels](Crm.Pricing.PricingModels.md)**  
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

