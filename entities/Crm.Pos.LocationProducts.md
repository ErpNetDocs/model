---
uid: Crm.Pos.LocationProducts
---
# Crm.Pos.LocationProducts


The listed products for sale for each POS location.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.LocationProducts  
Base Table: Pos_Location_Products  
Introduced In Version: 26.2.0.74  
API access:  ReadWrite  

## Visualization
Display Format: {Location.PosLocationCode}  
Search Members: Location.PosLocationCode  
Name Member: Location.PosLocationCode  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  
Aggregate Root:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [GrossPrice](Crm.Pos.LocationProducts.md#grossprice) | [Amount (18, 4)](../data-types.md#amount) __nullable__ | Gross sales price including applicable taxes, expressed in the currency defined by Product.ProductCurrency. `Currency: Product.ProductCurrency` `Introduced in version 26.2.1.26` 
| [MaxQuantity](Crm.Pos.LocationProducts.md#maxquantity) | decimal (10, 3) __nullable__ | Maximum target on-hand quantity for this product in this POS location. Used to calculate replenishment need (MaxQuantity - CurrentOnHand). 
| [MinQuantity](Crm.Pos.LocationProducts.md#minquantity) | decimal (10, 3) __nullable__ | Minimum desired on-hand quantity for this product in this POS location. Used for basic replenishment and stock alerts. 
| [Placement](Crm.Pos.LocationProducts.md#placement) | string (254) __nullable__ | Free-text description of default placement. 
| [Status](Crm.Pos.LocationProducts.md#status) | [Status](Crm.Pos.LocationProducts.md#status) | Listing state. `Required` `Filter(multi eq)` 
| [ValidFrom](Crm.Pos.LocationProducts.md#validfrom) | date __nullable__ | Begining of validity. `Filter(eq;ge;le)` 
| [ValidTo](Crm.Pos.LocationProducts.md#validto) | date __nullable__ | End of validity. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Location](Crm.Pos.LocationProducts.md#location) | [Locations](Crm.Pos.Locations.md) | The location for which the product is listed. `Required` `Filter(multi eq)` `Owner` |
| [Product](Crm.Pos.LocationProducts.md#product) | [Products](General.Products.Products.md) | The listed product. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.LocationProducts.md#id) | guid |  
| [ObjectVersion](Crm.Pos.LocationProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pos.LocationProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### GrossPrice

Gross sales price including applicable taxes, expressed in the currency defined by Product.ProductCurrency. `Currency: Product.ProductCurrency` `Introduced in version 26.2.1.26`

Type: **[Amount (18, 4)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MaxQuantity

Maximum target on-hand quantity for this product in this POS location. Used to calculate replenishment need (MaxQuantity - CurrentOnHand).

Type: **decimal (10, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MinQuantity

Minimum desired on-hand quantity for this product in this POS location. Used for basic replenishment and stock alerts.

Type: **decimal (10, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Placement

Free-text description of default placement.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Status

Listing state. `Required` `Filter(multi eq)`

Type: **[Status](Crm.Pos.LocationProducts.md#status)**  
Category: **System**  
Allowed values for the `Status`(Crm.Pos.LocationProducts.md#status) data attribute  
Allowed Values (Crm.Pos.LocationProductsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| Active | Active; product can be sold in this location.. Stored as 'ACT'. <br /> Database Value: 'ACT' <br /> Model Value: 0 <br /> Domain API Value: 'Active' |
| Inactive | Inactive; product temporarily unavailable or not to be offered.. Stored as 'INA'. <br /> Database Value: 'INA' <br /> Model Value: 1 <br /> Domain API Value: 'Inactive' |
| Blocked | Blocked; product must not be sold due to issues or restrictions.. Stored as 'BLK'. <br /> Database Value: 'BLK' <br /> Model Value: 2 <br /> Domain API Value: 'Blocked' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidFrom

Begining of validity. `Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidTo

End of validity. `Filter(eq;ge;le)`

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
Show in UI: **ShownByDefault**  

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

### Location

The location for which the product is listed. `Required` `Filter(multi eq)` `Owner`

Type: **[Locations](Crm.Pos.Locations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Product

The listed product. `Required` `Filter(multi eq)`

Type: **[Products](General.Products.Products.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.LocationProducts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.LocationProducts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_LocationProducts

Domain API Entity Type: 
Crm_Pos_LocationProduct

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_LocationProducts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_LocationProducts?$top=10>

