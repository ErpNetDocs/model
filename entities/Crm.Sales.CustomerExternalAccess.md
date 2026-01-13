---
uid: Crm.Sales.CustomerExternalAccess
---
# Crm.Sales.CustomerExternalAccess Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Defines the users permissions to specific customer data. Entity: Crm_Customer_External_Access (Introduced in version 25.1.2.51)

## Default Visualization
Default Display Text Format:  
_{Customer} - {ShipToCustomer} - {User}_  
Default Search Members:  
_Customer.Party.PartyName_  
Name Data Member:  
_Customer.Party.PartyName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  
Aggregate Root:  
[Crm.Sales.Customers](Crm.Sales.Customers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DaysBackAccess](Crm.Sales.CustomerExternalAccess.md#daysbackaccess) | int32 __nullable__ | The maximum number of past days the user is allowed to view. If null, the access is unlimited. `Default(30)` `Filter(eq;ge;le)` 
| [DisplayText](Crm.Sales.CustomerExternalAccess.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Sales.CustomerExternalAccess.md#id) | guid |  
| [Notes](Crm.Sales.CustomerExternalAccess.md#notes) | string (max) __nullable__ | Notes for this External Access. 
| [ObjectVersion](Crm.Sales.CustomerExternalAccess.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Role](Crm.Sales.CustomerExternalAccess.md#role) | [Role](Crm.Sales.CustomerExternalAccess.md#role) | The role of the user, defines the granted access. `Required` `Default("L30")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Customer](Crm.Sales.CustomerExternalAccess.md#customer) | [Customers](Crm.Sales.Customers.md) | The customer whose data is being accessed. `Required` `Filter(multi eq)` `Owner` |
| [User](Crm.Sales.CustomerExternalAccess.md#user) | [Users](Systems.Security.Users.md) | The user to whom the access is granted. `Required` `Filter(multi eq)` |


## Attribute Details

### DaysBackAccess

The maximum number of past days the user is allowed to view. If null, the access is unlimited. `Default(30)` `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **30**  
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
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this External Access.

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

### Role

The role of the user, defines the granted access. `Required` `Default("L30")` `Filter(eq)`

_Type_: **[Role](Crm.Sales.CustomerExternalAccess.md#role)**  
_Category_: **System**  
Allowed values for the `Role`(Crm.Sales.CustomerExternalAccess.md#role) data attribute  
_Allowed Values (Crm.Sales.CustomerExternalAccessRepository.Role Enum Members)_  

| Value | Description |
| ---- | --- |
| Basic | Basic. Stored as 'L10'. <br /> _Database Value:_ 'L10' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Basic' |
| Orders | Orders. Stored as 'L20'. <br /> _Database Value:_ 'L20' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Orders' |
| OrdersWithPrices | Orders with Prices. Stored as 'L30'. <br /> _Database Value:_ 'L30' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'OrdersWithPrices' |
| Billing | Billing. Stored as 'L40'. <br /> _Database Value:_ 'L40' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Billing' |
| Admin | Admin. Stored as 'L80'. <br /> _Database Value:_ 'L80' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Admin' |
| Owner | Owner. Stored as 'L90'. <br /> _Database Value:_ 'L90' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Owner' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **OrdersWithPrices**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Customer

The customer whose data is being accessed. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Customers](Crm.Sales.Customers.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### User

The user to whom the access is granted. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Crm.Sales.CustomerExternalAccess erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.CustomerExternalAccess erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_CustomerExternalAccess

Domain API Entity Type: 
Crm_Sales_CustomerExternalAcces

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_CustomerExternalAccess?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_CustomerExternalAccess?$top=10>

