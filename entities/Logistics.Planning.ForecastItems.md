---
uid: Logistics.Planning.ForecastItems
---
# Logistics.Planning.ForecastItems


Represents forecasted demand quantities for products, used as input for planning and supply calculations. Each item defines the expected demand for a specific product, location, and time period (planning bucket). Demand forecast items may originate from statistical forecasting, manual input, or external sources, and serve as a primary driver for MRP, replenishment, and production planning processes.

## General
Namespace: [Logistics.Planning](Logistics.Planning.md)  
Repository: Logistics.Planning.ForecastItems  
Base Table: Crm_Forecast_Items  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {QuantityValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Planning.ForecastItems](Logistics.Planning.ForecastItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](Logistics.Planning.ForecastItems.md#date) | datetime | The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period`Required` `Filter(ge;le)` |
| [ForecastedOnUtc](Logistics.Planning.ForecastItems.md#forecastedonutc) | datetime __nullable__ | Indicates the date and time when the demand forecast was generated or last recalculated. For manually created or adjusted records, this represents the date and time of the latest update.`Default(NowUtc)` `Filter(ge;le)` `Introduced in version 26.2.2.5` |
| [ForecastSettingsJson](Logistics.Planning.ForecastItems.md#forecastsettingsjson) | string (max) __nullable__ | Stores the configuration parameters used to generate the forecast in JSON format. This may include algorithm settings, input filters, time horizons, or other options applied during the forecasting process.`Filter(like)` `Introduced in version 26.2.2.5` |
| [IsActive](Logistics.Planning.ForecastItems.md#isactive) | boolean | Indicates whether the current Forecast item is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18` |
| [Notes](Logistics.Planning.ForecastItems.md#notes) | string (max) __nullable__ | Additional information for this forecast item.`Filter(like)` `Introduced in version 26.2.2.5` |
| [PlanningSource](Logistics.Planning.ForecastItems.md#planningsource) | [PlanningSource](Logistics.Planning.ForecastItems.md#planningsource) | Specifies how the demand forecast item was created—whether it was generated automatically by the forecasting system or entered/adjusted manually by a user.`Required` `Default(&quot;M&quot;)` `Filter(eq)` `Introduced in version 26.2.2.5` |
| [Quantity](Logistics.Planning.ForecastItems.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The forecasted sales quantity in the base measurement category of the product`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Country](Logistics.Planning.ForecastItems.md#country) | [Countries](General.Geography.Countries.md) (nullable) | The country for which the forecast is made. When NULL, the forecast is country neutral. |
| [Customer](Logistics.Planning.ForecastItems.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | The customer for which the forecast is made. When NULL, the forecast is not for any specfic customer. |
| [Dealer](Logistics.Planning.ForecastItems.md#dealer) | [Dealers](Crm.Sales.Dealers.md) (nullable) | The dealer for which the forecast is made. When NULL, the forecast is not for any specfic dealer. |
| [Product](Logistics.Planning.ForecastItems.md#product) | [Products](General.Products.Products.md) | The product for which the forecast is made. |
| [SalesPerson](Logistics.Planning.ForecastItems.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable) | The sales person for which the forecast is made. When NULL, the forecast is not for any specfic sales person. |
| [Store](Logistics.Planning.ForecastItems.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store which is expected to sell the products. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Planning.ForecastItems.md#id) | guid |  |
| [ObjectVersion](Logistics.Planning.ForecastItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Logistics.Planning.ForecastItems.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Logistics.Planning.ForecastItems.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Logistics.Planning.ForecastItems.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [DisplayText](Logistics.Planning.ForecastItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Date

The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ForecastedOnUtc

Indicates the date and time when the demand forecast was generated or last recalculated. For manually created or adjusted records, this represents the date and time of the latest update.`Default(NowUtc)` `Filter(ge;le)` `Introduced in version 26.2.2.5`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### ForecastSettingsJson

Stores the configuration parameters used to generate the forecast in JSON format. This may include algorithm settings, input filters, time horizons, or other options applied during the forecasting process.`Filter(like)` `Introduced in version 26.2.2.5`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Forecast item is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Additional information for this forecast item.`Filter(like)` `Introduced in version 26.2.2.5`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PlanningSource

Specifies how the demand forecast item was created—whether it was generated automatically by the forecasting system or entered/adjusted manually by a user.`Required` `Default(&quot;M&quot;)` `Filter(eq)` `Introduced in version 26.2.2.5`

Type: **[PlanningSource](Logistics.Planning.ForecastItems.md#planningsource)**  
Category: **System**  
Allowed values for the `PlanningSource`(Logistics.Planning.ForecastItems.md#planningsource) data attribute  
Allowed Values (Logistics.Planning.ForecastItemsRepository.PlanningSource Enum Members)  

| Value | Description |
| ---- | --- |
| Automated | Generated automatically by a forecasting algorithm or external system.. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Automated' |
| Manual | Entered or adjusted manually by a user.. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Manual' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Manual**  
Show in UI: **ShownByDefault**  

### Quantity

The forecasted sales quantity in the base measurement category of the product`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### Country

The country for which the forecast is made. When NULL, the forecast is country neutral.

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Customer

The customer for which the forecast is made. When NULL, the forecast is not for any specfic customer.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Dealer

The dealer for which the forecast is made. When NULL, the forecast is not for any specfic dealer.

Type: **[Dealers](Crm.Sales.Dealers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product for which the forecast is made.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesPerson

The sales person for which the forecast is made. When NULL, the forecast is not for any specfic sales person.

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The store which is expected to sell the products.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Logistics.Planning.ForecastItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Planning.ForecastItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Planning_ForecastItems

Domain API Entity Type: 
Logistics_Planning_ForecastItem

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Planning_ForecastItems?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Planning_ForecastItems?$top=10>

