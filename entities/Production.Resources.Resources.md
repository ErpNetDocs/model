---
uid: Production.Resources.Resources
---
# Production.Resources.Resources


Resource types available to production

## General
Namespace: [Production.Resources](Production.Resources.md)  
Repository: Production.Resources.Resources  
Base Table: Prd_Resources  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
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
[Production.Resources.ResourceGroups](Production.Resources.ResourceGroups.md)  
Aggregate Root:  
[Production.Resources.ResourceGroups](Production.Resources.ResourceGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Production.Resources.Resources.md#active) | boolean | Indicates whether the current resource is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26` 
| [Name](Production.Resources.Resources.md#name) | string (64) | Name of the resource. `Required` `Filter(like)` 
| [Notes](Production.Resources.Resources.md#notes) | string (254) __nullable__ | User notes for the resource. 
| [SetupDurationHours](Production.Resources.Resources.md#setupdurationhours) | decimal (6, 2) | The usual duration of setup when changing production. `Required` `Default(0)` 
| [SetupScrapQuantity](Production.Resources.Resources.md#setupscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The usual quantity of fixed scrap occurring when changing production. . `Unit: SetupScrapUnit` `Required` `Default(0)` 
| [StandardCostPerHour](Production.Resources.Resources.md#standardcostperhour) | [Amount (18, 6)](../data-types.md#amount) __nullable__ | Standard cost per hour for this resource. It participates in the calculation of standard cost for production recipes in which the current resource is used. `Currency: ResourceCurrency` 
| [StandardPricePerHour](Production.Resources.Resources.md#standardpriceperhour) | [Amount (18, 6)](../data-types.md#amount) __nullable__ | Standard price per hour for this resource. It participates in the calculation of standard price for production recipes in which the current resource is used. `Currency: ResourceCurrency` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PrimaryUnit](Production.Resources.Resources.md#primaryunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Primary measurement unit for quantities of the resource. `Required` `Filter(multi eq)` |
| [ResourceCurrency](Production.Resources.Resources.md#resourcecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Currency for this resource. This currency applies for the standard price and cost per hour. `Filter(multi eq)` |
| [ResourceGroup](Production.Resources.Resources.md#resourcegroup) | [ResourceGroups](Production.Resources.ResourceGroups.md) | The Id of the containing resource group. `Required` `Filter(multi eq)` `Owner` |
| [SetupScrapUnit](Production.Resources.Resources.md#setupscrapunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement units of Setup_Scrap_Quantity. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.Resources.md#id) | guid |  
| [ObjectVersion](Production.Resources.Resources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Resources.Resources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Functions | [ResourceFunctions](Production.Resources.ResourceFunctions.md) | List of `ResourceFunction`(Production.Resources.ResourceFunctions.md) child objects, based on the `Production.Resources.ResourceFunction.Resource`(Production.Resources.ResourceFunctions.md#resource) back reference 


## Attribute Details

### Active

Indicates whether the current resource is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the resource. `Required` `Filter(like)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

User notes for the resource.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SetupDurationHours

The usual duration of setup when changing production. `Required` `Default(0)`

Type: **decimal (6, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### SetupScrapQuantity

The usual quantity of fixed scrap occurring when changing production. . `Unit: SetupScrapUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StandardCostPerHour

Standard cost per hour for this resource. It participates in the calculation of standard cost for production recipes in which the current resource is used. `Currency: ResourceCurrency`

Type: **[Amount (18, 6)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardPricePerHour

Standard price per hour for this resource. It participates in the calculation of standard price for production recipes in which the current resource is used. `Currency: ResourceCurrency`

Type: **[Amount (18, 6)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### PrimaryUnit

Primary measurement unit for quantities of the resource. `Required` `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResourceCurrency

Currency for this resource. This currency applies for the standard price and cost per hour. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResourceGroup

The Id of the containing resource group. `Required` `Filter(multi eq)` `Owner`

Type: **[ResourceGroups](Production.Resources.ResourceGroups.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SetupScrapUnit

The measurement units of Setup_Scrap_Quantity. `Required` `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
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

[!list limit=1000 erp.entity=Production.Resources.Resources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Resources.Resources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Resources_Resources

Domain API Entity Type: 
Production_Resources_Resource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Resources_Resources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Resources_Resources?$top=10>

