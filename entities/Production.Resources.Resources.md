---
uid: Production.Resources.Resources
---
# Production.Resources.Resources Entity

**Namespace:** [Production.Resources](Production.Resources.md)  

Resource types available to production. Entity: Prd_Resources

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Production.Resources.Resources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.Resources.Resources.md#id) | guid |  
| [Name](Production.Resources.Resources.md#name) | string (64) | Name of the resource. `Required` `Filter(like)` 
| [Notes](Production.Resources.Resources.md#notes) | string (254) __nullable__ | User notes for the resource. 
| [ObjectVersion](Production.Resources.Resources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Functions | [ResourceFunctions](Production.Resources.ResourceFunctions.md) | List of `ResourceFunction`(Production.Resources.ResourceFunctions.md) child objects, based on the `Production.Resources.ResourceFunction.Resource`(Production.Resources.ResourceFunctions.md#resource) back reference 


## Attribute Details

### Active

Indicates whether the current resource is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
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
_Show in UI_: **HiddenByDefault**  

### Name

Name of the resource. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

User notes for the resource.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SetupDurationHours

The usual duration of setup when changing production. `Required` `Default(0)`

_Type_: **decimal (6, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### SetupScrapQuantity

The usual quantity of fixed scrap occurring when changing production. . `Unit: SetupScrapUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### StandardCostPerHour

Standard cost per hour for this resource. It participates in the calculation of standard cost for production recipes in which the current resource is used. `Currency: ResourceCurrency`

_Type_: **[Amount (18, 6)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardPricePerHour

Standard price per hour for this resource. It participates in the calculation of standard price for production recipes in which the current resource is used. `Currency: ResourceCurrency`

_Type_: **[Amount (18, 6)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### PrimaryUnit

Primary measurement unit for quantities of the resource. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ResourceCurrency

Currency for this resource. This currency applies for the standard price and cost per hour. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ResourceGroup

The Id of the containing resource group. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ResourceGroups](Production.Resources.ResourceGroups.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SetupScrapUnit

The measurement units of Setup_Scrap_Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
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

