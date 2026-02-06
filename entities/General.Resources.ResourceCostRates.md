---
uid: General.Resources.ResourceCostRates
---
# General.Resources.ResourceCostRates


Contains cost rates for different periods for resources. Each record is valid until the next From Date.

## General
Namespace: [General.Resources](General.Resources.md)  
Repository: General.Resources.ResourceCostRates  
Base Table: Gen_Resource_Cost_Rates  
API access:  ReadWrite  

## Visualization
Display Format: {Resource.Name:T}  
Search Members: Resource.Name  
Name Member: Resource.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Resources.Resources](General.Resources.Resources.md)  
Aggregate Root:  
[General.Resources.ResourceGroups](General.Resources.ResourceGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](General.Resources.ResourceCostRates.md#fromdate) | date | Starting date of validity of the cost rate. The rate is valid until the next cost rate record with later date is defined.[Required] [Filter(eq;ge;le)] 
| [Notes](General.Resources.ResourceCostRates.md#notes) | string (max) __nullable__ | Notes for this ResourceCostRate. 
| [OvertimeRatePerHour](General.Resources.ResourceCostRates.md#overtimerateperhour) | [Amount (12, 4)](../data-types.md#amount) __nullable__ | The overtime cost of the resource per hour in the resources costing currency. The overtime rate specifies the cost of the resource, when it is used outside the normal working schedule. NULL means that there is no special overtime rate and the standard rate should be applied.[Currency: Resource.CostingCurrency] [Filter(eq;like)] 
| [PerUseCost](General.Resources.ResourceCostRates.md#perusecost) | [Amount (12, 2)](../data-types.md#amount) | One-time cost for each usage of the resource in the resources costing currency.[Currency: Resource.CostingCurrency] [Required] [Default(0)] [Filter(eq;like)] 
| [StandardRatePerHour](General.Resources.ResourceCostRates.md#standardrateperhour) | [Amount (12, 4)](../data-types.md#amount) | The standard cost per hour of the resource in the resources costing currency. The standard cost is applied for resource usage during the normal working hours.[Currency: Resource.CostingCurrency] [Required] [Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](General.Resources.ResourceCostRates.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the cost is defined. |
| [Resource](General.Resources.ResourceCostRates.md#resource) | [Resources](General.Resources.Resources.md) | The resource for which the cost rate is defined. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Resources.ResourceCostRates.md#id) | guid |  
| [ObjectVersion](General.Resources.ResourceCostRates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Resources.ResourceCostRates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FromDate

Starting date of validity of the cost rate. The rate is valid until the next cost rate record with later date is defined.[Required] [Filter(eq;ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ResourceCostRate.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### OvertimeRatePerHour

The overtime cost of the resource per hour in the resources costing currency. The overtime rate specifies the cost of the resource, when it is used outside the normal working schedule. NULL means that there is no special overtime rate and the standard rate should be applied.[Currency: Resource.CostingCurrency] [Filter(eq;like)]

Type: **[Amount (12, 4)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PerUseCost

One-time cost for each usage of the resource in the resources costing currency.[Currency: Resource.CostingCurrency] [Required] [Default(0)] [Filter(eq;like)]

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StandardRatePerHour

The standard cost per hour of the resource in the resources costing currency. The standard cost is applied for resource usage during the normal working hours.[Currency: Resource.CostingCurrency] [Required] [Filter(eq;like)]

Type: **[Amount (12, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

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

### EnterpriseCompany

The enterprise company for which the cost is defined.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Resource

The resource for which the cost rate is defined.

Type: **[Resources](General.Resources.Resources.md)**  
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

