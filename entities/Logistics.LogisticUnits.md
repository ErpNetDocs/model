---
uid: Logistics.LogisticUnits
---
# Logistics.LogisticUnits Entity

**Namespace:** [Logistics](Logistics.md)  

Composition of products established for transport and/or storage which needs to be managed through the supply chain. Entity: Log_Logistic_Units (Introduced in version 21.1.0.77)
## Renamed
**New name:** [Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  



## Default Visualization
Default Display Text Format:  
_{SerialCode}_  
Default Search Members:  
_SerialCode_  
Code Data Member:  
_SerialCode_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
Object category attribute:  _LogisticUnitTypeId_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.LogisticUnits](Logistics.LogisticUnits.md)  
  * [Logistics.LogisticUnitContents](Logistics.LogisticUnitContents.md)  
  * [Logistics.LogisticUnitSpecifications](Logistics.LogisticUnitSpecifications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Logistics.LogisticUnits.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpectedWeight](Logistics.LogisticUnits.md#expectedweight) | decimal (12, 3) __nullable__ | Expected weight in KG. Used for planning purposes. null means unknown. `Filter(eq;ge;le)` 
| [Id](Logistics.LogisticUnits.md#id) | guid |  
| [IsActive](Logistics.LogisticUnits.md#isactive) | boolean | Indicates whether the logistic unit is currently active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 23.1.2.11` 
| [MeasuredWeight](Logistics.LogisticUnits.md#measuredweight) | decimal (12, 3) __nullable__ | Actual measured weight of the unit in KG. null means unknown. `Filter(eq;ge;le)` 
| [Notes](Logistics.LogisticUnits.md#notes) | string (max) __nullable__ | Notes for this LogisticUnit. `Filter(like)` 
| [ObjectVersion](Logistics.LogisticUnits.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SerialCode](Logistics.LogisticUnits.md#serialcode) | string (32) | Unique serial code of the logistic unit. If GS1 coding is used, this is the SSCC. `Required` `Filter(multi eq;like)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.LogisticUnits.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable) | General type of the cargo of the logistic unit. null means unknown or N/A. `Filter(multi eq)` |
| [LogisticUnitType](Logistics.LogisticUnits.md#logisticunittype) | [LogisticUnitTypes](Logistics.LogisticUnitTypes.md) (nullable) | The type of the logistic unit. null means the type is currently unknown. `Filter(multi eq)` |
| [RepresentedAsProduct](Logistics.LogisticUnits.md#representedasproduct) | [Products](General.Products.Products.md) (nullable) | When the logistic unit is also a tradeable item, specifies the product used to trade the unit. The product should uniquely identify only one logistic unit. Note that this is different from a logistic unit containing a single item. null means that the unit is not a tradeable item. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Contents | [LogisticUnitContents](Logistics.LogisticUnitContents.md) | List of `LogisticUnitContent`(Logistics.LogisticUnitContents.md) child objects, based on the `Logistics.LogisticUnitContent.LogisticUnit`(Logistics.LogisticUnitContents.md#logisticunit) back reference 
| Specifications | [LogisticUnitSpecifications](Logistics.LogisticUnitSpecifications.md) | List of `LogisticUnitSpecification<br />`(Logistics.LogisticUnitSpecifications.md) child objects, based on the `Logistics.LogisticUnitSpecification.LogisticUnit`(Logistics.LogisticUnitSpecifications.md#logisticunit) back reference 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpectedWeight

Expected weight in KG. Used for planning purposes. null means unknown. `Filter(eq;ge;le)`

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the logistic unit is currently active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 23.1.2.11`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### MeasuredWeight

Actual measured weight of the unit in KG. null means unknown. `Filter(eq;ge;le)`

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this LogisticUnit. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### SerialCode

Unique serial code of the logistic unit. If GS1 coding is used, this is the SSCC. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CargoType

General type of the cargo of the logistic unit. null means unknown or N/A. `Filter(multi eq)`

_Type_: **[CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LogisticUnitType

The type of the logistic unit. null means the type is currently unknown. `Filter(multi eq)`

_Type_: **[LogisticUnitTypes](Logistics.LogisticUnitTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RepresentedAsProduct

When the logistic unit is also a tradeable item, specifies the product used to trade the unit. The product should uniquely identify only one logistic unit. Note that this is different from a logistic unit containing a single item. null means that the unit is not a tradeable item. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### UpdateGS1ApplicationCodes

Based on the internal data in the logistic unit and its contents, creates or updates the GS1 application codes.              The data is than stored in the logistic unit specifications.              The method does not commit the object transaction.  
_Return Type_: **void**  
_Declaring Type_: **[LogisticUnits](Logistics.LogisticUnits.md)**  
_Domain API Request_: **POST**  

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


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Logistics.LogisticUnits erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.LogisticUnits erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_LogisticUnits?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_LogisticUnits?$top=10>

