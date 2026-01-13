---
uid: General.Resources.ResourceCostRates
---
# General.Resources.ResourceCostRates Entity

**Namespace:** [General.Resources](General.Resources.md)  

Contains cost rates for different periods for resources. Each record is valid until the next From Date. Entity: Gen_Resource_Cost_Rates

## Default Visualization
Default Display Text Format:  
_{Resource.Name:T}_  
Default Search Members:  
_Resource.Name_  
Name Data Member:  
_Resource.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Resources.Resources](General.Resources.Resources.md)  
Aggregate Root:  
[General.Resources.ResourceGroups](General.Resources.ResourceGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](General.Resources.ResourceCostRates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](General.Resources.ResourceCostRates.md#fromdate) | date | Starting date of validity of the cost rate. The rate is valid until the next cost rate record with later date is defined. `Required` `Filter(eq;ge;le)` 
| [Id](General.Resources.ResourceCostRates.md#id) | guid |  
| [Notes](General.Resources.ResourceCostRates.md#notes) | string (max) __nullable__ | Notes for this ResourceCostRate. 
| [ObjectVersion](General.Resources.ResourceCostRates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OvertimeRatePerHour](General.Resources.ResourceCostRates.md#overtimerateperhour) | [Amount (12, 4)](../data-types.md#amount) __nullable__ | The overtime cost of the resource per hour in the resources costing currency. The overtime rate specifies the cost of the resource, when it is used outside the normal working schedule. null means that there is no special overtime rate and the standard rate should be applied. `Currency: Resource.CostingCurrency` `Filter(eq;like)` 
| [PerUseCost](General.Resources.ResourceCostRates.md#perusecost) | [Amount (12, 2)](../data-types.md#amount) | One-time cost for each usage of the resource in the resources costing currency. `Currency: Resource.CostingCurrency` `Required` `Default(0)` `Filter(eq;like)` 
| [StandardRatePerHour](General.Resources.ResourceCostRates.md#standardrateperhour) | [Amount (12, 4)](../data-types.md#amount) | The standard cost per hour of the resource in the resources costing currency. The standard cost is applied for resource usage during the normal working hours. `Currency: Resource.CostingCurrency` `Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](General.Resources.ResourceCostRates.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the cost is defined. `Required` `Filter(multi eq)` |
| [Resource](General.Resources.ResourceCostRates.md#resource) | [Resources](General.Resources.Resources.md) | The resource for which the cost rate is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

Starting date of validity of the cost rate. The rate is valid until the next cost rate record with later date is defined. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this ResourceCostRate.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OvertimeRatePerHour

The overtime cost of the resource per hour in the resources costing currency. The overtime rate specifies the cost of the resource, when it is used outside the normal working schedule. null means that there is no special overtime rate and the standard rate should be applied. `Currency: Resource.CostingCurrency` `Filter(eq;like)`

_Type_: **[Amount (12, 4)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PerUseCost

One-time cost for each usage of the resource in the resources costing currency. `Currency: Resource.CostingCurrency` `Required` `Default(0)` `Filter(eq;like)`

_Type_: **[Amount (12, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### StandardRatePerHour

The standard cost per hour of the resource in the resources costing currency. The standard cost is applied for resource usage during the normal working hours. `Currency: Resource.CostingCurrency` `Required` `Filter(eq;like)`

_Type_: **[Amount (12, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company for which the cost is defined. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Resource

The resource for which the cost rate is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Resources](General.Resources.Resources.md)**  
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

[!list limit=1000 erp.entity=General.Resources.ResourceCostRates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Resources.ResourceCostRates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Resources_ResourceCostRates

Domain API Entity Type: 
General_Resources_ResourceCostRate

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Resources_ResourceCostRates?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Resources_ResourceCostRates?$top=10>

