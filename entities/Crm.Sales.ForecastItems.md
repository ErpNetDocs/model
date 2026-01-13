---
uid: Crm.Sales.ForecastItems
---
# Crm.Sales.ForecastItems Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Forecast items form demand in MRP calculations. Entity: Crm_Forecast_Items

## Renames

Old name: **Crm.Marketing.ForecastItems**  
New name: **Crm.Sales.ForecastItems**  
Version: **25.1.1.48**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{Id}: {QuantityValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Sales.ForecastItems](Crm.Sales.ForecastItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](Crm.Sales.ForecastItems.md#date) | datetime | The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period. `Required` `Filter(ge;le)` 
| [DisplayText](Crm.Sales.ForecastItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.Sales.ForecastItems.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Sales.ForecastItems.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Sales.ForecastItems.md#id) | guid |  
| [IsActive](Crm.Sales.ForecastItems.md#isactive) | boolean | Indicates whether the current Forecast item is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18` 
| [ObjectVersion](Crm.Sales.ForecastItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Crm.Sales.ForecastItems.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The forecasted sales quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Country](Crm.Sales.ForecastItems.md#country) | [Countries](General.Geography.Countries.md) (nullable) | The country for which the forecast is made. When null, the forecast is country neutral. `Filter(multi eq)` |
| [Customer](Crm.Sales.ForecastItems.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | The customer for which the forecast is made. When null, the forecast is not for any specfic customer. `Filter(multi eq)` |
| [Dealer](Crm.Sales.ForecastItems.md#dealer) | [Dealers](Crm.Sales.Dealers.md) (nullable) | The dealer for which the forecast is made. When null, the forecast is not for any specfic dealer. `Filter(multi eq)` |
| [Product](Crm.Sales.ForecastItems.md#product) | [Products](General.Products.Products.md) | The product for which the forecast is made. `Required` `Filter(multi eq)` |
| [SalesPerson](Crm.Sales.ForecastItems.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable) | The sales person for which the forecast is made. When null, the forecast is not for any specfic sales person. `Filter(multi eq)` |
| [Store](Crm.Sales.ForecastItems.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store which is expected to sell the products. `Required` `Filter(multi eq)` |


## Attribute Details

### Date

The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### IsActive

Indicates whether the current Forecast item is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The forecasted sales quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Country

The country for which the forecast is made. When null, the forecast is country neutral. `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Customer

The customer for which the forecast is made. When null, the forecast is not for any specfic customer. `Filter(multi eq)`

_Type_: **[Customers](Crm.Sales.Customers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Dealer

The dealer for which the forecast is made. When null, the forecast is not for any specfic dealer. `Filter(multi eq)`

_Type_: **[Dealers](Crm.Sales.Dealers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product for which the forecast is made. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesPerson

The sales person for which the forecast is made. When null, the forecast is not for any specfic sales person. `Filter(multi eq)`

_Type_: **[SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store which is expected to sell the products. `Required` `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Crm.Sales.ForecastItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.ForecastItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_ForecastItems

Domain API Entity Type: 
Crm_Sales_ForecastItem

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_ForecastItems?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_ForecastItems?$top=10>

