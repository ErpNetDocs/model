---
uid: Crm.Sales.CustomerProducts
---
# Crm.Sales.CustomerProducts


Customer Products represent the products that are contractually agreed and listed for a specific customer. This data type defines the set of products associated with a customer, including products that are contractually negotiated, approved for sale, or explicitly listed as available to that customer. Customer Products are used to support customer-specific assortments, sales restrictions, pricing agreements, and order validation, ensuring that only applicable products are offered and sold to the customer.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.CustomerProducts  
Base Table: Crm_Customer_Products  
Introduced In Version: 22.1.6.42  
API access:  ReadWrite  

## Renames

Old name: Crm.CustomerProducts  
New name: Crm.Sales.CustomerProducts  
Version: 25.1.2.28  
Case: 38176  



## Visualization
Display Format: {Customer.Party.PartyName:T}  
Search Members: Customer.Party.PartyName  
Name Member: Customer.Party.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  
Aggregate Root:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](Crm.Sales.CustomerProducts.md#fromdate) | date __nullable__ | The initial date of the listing. null when the initial date is unknown. `Filter(eq;ge;le)` 
| [InStoreLocation](Crm.Sales.CustomerProducts.md#instorelocation) | string (32) __nullable__ | Location in store, like row, stand, etc. 
| [InStoreMaxQuantity](Crm.Sales.CustomerProducts.md#instoremaxquantity) | [Quantity (10, 3)](../data-types.md#quantity) __nullable__ | Maximum quantity maintained by the customer. Measurement unit is Product.MeasurementUnit. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)` 
| [InStoreMinQuantity](Crm.Sales.CustomerProducts.md#instoreminquantity) | [Quantity (10, 3)](../data-types.md#quantity) __nullable__ | Minimum quantity maintained by the customer. Measurement unit is Product.MeasurementUnit. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)` 
| [IsActive](Crm.Sales.CustomerProducts.md#isactive) | boolean | Indicates whether this customer product definition is active. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Crm.Sales.CustomerProducts.md#notes) | string (254) __nullable__ | Notes for the listing. 
| [OrderMultiple](Crm.Sales.CustomerProducts.md#ordermultiple) | [Quantity (10, 3)](../data-types.md#quantity) __nullable__ | Determines the step when the system offers a quantity to order. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)` 
| [ToDate](Crm.Sales.CustomerProducts.md#todate) | date __nullable__ | The final date of the listing. null when the final date is unknown. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyDivision](Crm.Sales.CustomerProducts.md#companydivision) | [CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable) | When the customer is a company, denotes the division for which the product is listed. null when the customer is not a company or when the listing is not division specific. `Filter(multi eq)` |
| [CompanyLocation](Crm.Sales.CustomerProducts.md#companylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When the customer is a company, denotes the location for which the product is listed. null when the customer is not a company or when the listing is not location specific. `Filter(multi eq)` |
| [Customer](Crm.Sales.CustomerProducts.md#customer) | [Customers](Crm.Sales.Customers.md) | Customer, for which the product is listed. `Required` `Filter(multi eq)` `Owner` |
| [InStoreQuantityUnit](Crm.Sales.CustomerProducts.md#instorequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Location in store, like row, stand, etc. `Filter(multi eq)` |
| [Product](Crm.Sales.CustomerProducts.md#product) | [Products](General.Products.Products.md) | The product, which is listed for the customer. `Required` `Filter(multi eq)` `FilterableReference` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.CustomerProducts.md#id) | guid |  
| [ObjectVersion](Crm.Sales.CustomerProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.CustomerProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FromDate

The initial date of the listing. null when the initial date is unknown. `Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InStoreLocation

Location in store, like row, stand, etc.

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### InStoreMaxQuantity

Maximum quantity maintained by the customer. Measurement unit is Product.MeasurementUnit. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)`

Type: **[Quantity (10, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InStoreMinQuantity

Minimum quantity maintained by the customer. Measurement unit is Product.MeasurementUnit. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)`

Type: **[Quantity (10, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether this customer product definition is active. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the listing.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### OrderMultiple

Determines the step when the system offers a quantity to order. `Unit: InStoreQuantityUnit` `Filter(eq;ge;le)`

Type: **[Quantity (10, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

The final date of the listing. null when the final date is unknown. `Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### CompanyDivision

When the customer is a company, denotes the division for which the product is listed. null when the customer is not a company or when the listing is not division specific. `Filter(multi eq)`

Type: **[CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CompanyLocation

When the customer is a company, denotes the location for which the product is listed. null when the customer is not a company or when the listing is not location specific. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Customer

Customer, for which the product is listed. `Required` `Filter(multi eq)` `Owner`

Type: **[Customers](Crm.Sales.Customers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### InStoreQuantityUnit

Location in store, like row, stand, etc. `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### Product

The product, which is listed for the customer. `Required` `Filter(multi eq)` `FilterableReference`

Type: **[Products](General.Products.Products.md)**  
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

[!list limit=1000 erp.entity=Crm.Sales.CustomerProducts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.CustomerProducts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_CustomerProducts

Domain API Entity Type: 
Crm_Sales_CustomerProduct

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_CustomerProducts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_CustomerProducts?$top=10>

