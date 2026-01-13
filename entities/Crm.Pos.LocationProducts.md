---
uid: Crm.Pos.LocationProducts
---
# Crm.Pos.LocationProducts Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

The listed products for sale for each POS location. Entity: Pos_Location_Products (Introduced in version 26.2.0.74)

## Default Visualization
Default Display Text Format:  
_{Location.PosLocationCode}_  
Default Search Members:  
_Location.PosLocationCode_  
Name Data Member:  
_Location.PosLocationCode_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  
Aggregate Root:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Crm.Pos.LocationProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pos.LocationProducts.md#id) | guid |  
| [MaxQuantity](Crm.Pos.LocationProducts.md#maxquantity) | decimal (10, 3) __nullable__ | Maximum target on-hand quantity for this product in this POS location. Used to calculate replenishment need (MaxQuantity - CurrentOnHand). 
| [MinQuantity](Crm.Pos.LocationProducts.md#minquantity) | decimal (10, 3) __nullable__ | Minimum desired on-hand quantity for this product in this POS location. Used for basic replenishment and stock alerts. 
| [ObjectVersion](Crm.Pos.LocationProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Placement](Crm.Pos.LocationProducts.md#placement) | string (254) __nullable__ | Free-text description of default placement. 
| [Status](Crm.Pos.LocationProducts.md#status) | [Status](Crm.Pos.LocationProducts.md#status) | Listing state. `Required` `Filter(multi eq)` 
| [ValidFrom](Crm.Pos.LocationProducts.md#validfrom) | date __nullable__ | Begining of validity. `Filter(eq;ge;le)` 
| [ValidTo](Crm.Pos.LocationProducts.md#validto) | date __nullable__ | End of validity. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Location](Crm.Pos.LocationProducts.md#location) | [Locations](Crm.Pos.Locations.md) | The location for which the product is listed. `Required` `Filter(multi eq)` `Owner` |
| [Product](Crm.Pos.LocationProducts.md#product) | [Products](General.Products.Products.md) | The listed product. `Required` `Filter(multi eq)` |


## Attribute Details

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
_Show in UI_: **ShownByDefault**  

### MaxQuantity

Maximum target on-hand quantity for this product in this POS location. Used to calculate replenishment need (MaxQuantity - CurrentOnHand).

_Type_: **decimal (10, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MinQuantity

Minimum desired on-hand quantity for this product in this POS location. Used for basic replenishment and stock alerts.

_Type_: **decimal (10, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Placement

Free-text description of default placement.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Status

Listing state. `Required` `Filter(multi eq)`

_Type_: **[Status](Crm.Pos.LocationProducts.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Crm.Pos.LocationProducts.md#status) data attribute  
_Allowed Values (Crm.Pos.LocationProductsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| Active | Active; product can be sold in this location.. Stored as 'ACT'. <br /> _Database Value:_ 'ACT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Active' |
| Inactive | Inactive; product temporarily unavailable or not to be offered.. Stored as 'INA'. <br /> _Database Value:_ 'INA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Inactive' |
| Blocked | Blocked; product must not be sold due to issues or restrictions.. Stored as 'BLK'. <br /> _Database Value:_ 'BLK' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Blocked' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidFrom

Begining of validity. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidTo

End of validity. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Location

The location for which the product is listed. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Locations](Crm.Pos.Locations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Product

The listed product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
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

