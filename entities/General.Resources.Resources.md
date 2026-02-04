---
uid: General.Resources.Resources
---
# General.Resources.Resources


Enterprise resources, categorized by groups.

## General
Namespace: [General.Resources](General.Resources.md)  
Repository: General.Resources.Resources  
Base Table: Gen_Resources  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Resources.ResourceGroups](General.Resources.ResourceGroups.md)  
Aggregate Root:  
[General.Resources.ResourceGroups](General.Resources.ResourceGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Name](General.Resources.Resources.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Resource name. Unique within the resource group. `Required` `Filter(eq;like)` 
| [Notes](General.Resources.Resources.md#notes) | string (max) __nullable__ | Notes for this Resource. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostingCurrency](General.Resources.Resources.md#costingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency in which resource costs are specified. Required only if resource costs will be specified. `Filter(multi eq)` |
| [ResourceGroup](General.Resources.Resources.md#resourcegroup) | [ResourceGroups](General.Resources.ResourceGroups.md) | The <see cref="ResourceGroup"/> to which this Resource belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Resources.Resources.md#id) | guid |  
| [ObjectVersion](General.Resources.Resources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Resources.Resources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Availability | [ResourceAvailability](General.Resources.ResourceAvailability.md) | List of `ResourceAvailability`(General.Resources.ResourceAvailability.md) child objects, based on the `General.Resources.ResourceAvailability.Resource`(General.Resources.ResourceAvailability.md#resource) back reference 
| CostRates | [ResourceCostRates](General.Resources.ResourceCostRates.md) | List of `ResourceCostRate`(General.Resources.ResourceCostRates.md) child objects, based on the `General.Resources.ResourceCostRate.Resource`(General.Resources.ResourceCostRates.md#resource) back reference 
| Instances | [ResourceInstances](General.Resources.ResourceInstances.md) | List of `ResourceInstance`(General.Resources.ResourceInstances.md) child objects, based on the `General.Resources.ResourceInstance.Resource`(General.Resources.ResourceInstances.md#resource) back reference 


## Attribute Details

### Name

Resource name. Unique within the resource group. `Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Resource.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### CostingCurrency

The currency in which resource costs are specified. Required only if resource costs will be specified. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResourceGroup

The <see cref="ResourceGroup"/> to which this Resource belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ResourceGroups](General.Resources.ResourceGroups.md)**  
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

[!list limit=1000 erp.entity=General.Resources.Resources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Resources.Resources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Resources_Resources

Domain API Entity Type: 
General_Resources_Resource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Resources_Resources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Resources_Resources?$top=10>

