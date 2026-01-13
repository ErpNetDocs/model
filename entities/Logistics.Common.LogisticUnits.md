---
uid: Logistics.Common.LogisticUnits
---
# Logistics.Common.LogisticUnits Entity

**Namespace:** [Logistics.Common](Logistics.Common.md)  

Composition of products established for transport and/or storage which needs to be managed through the supply chain. Entity: Log_Logistic_Units (Introduced in version 21.1.0.77)

## Renames

Old name: **Logistics.LogisticUnits**  
New name: **Logistics.Common.LogisticUnits**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{SerialCode}_  
Default Search Members:  
_SerialCode_  
Code Data Member:  
_SerialCode_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _LogisticUnitTypeId_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Common.LogisticUnits](Logistics.Common.LogisticUnits.md)  
  * [Logistics.Common.LogisticUnitContents](Logistics.Common.LogisticUnitContents.md)  
  * [Logistics.Common.LogisticUnitSpecifications](Logistics.Common.LogisticUnitSpecifications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Logistics.Common.LogisticUnits.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpectedWeight](Logistics.Common.LogisticUnits.md#expectedweight) | decimal (12, 3) __nullable__ | Expected weight in KG. Used for planning purposes. null means unknown. `Filter(eq;ge;le)` 
| [ExternalId](Logistics.Common.LogisticUnits.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Common.LogisticUnits.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Logistics.Common.LogisticUnits.md#id) | guid |  
| [IsActive](Logistics.Common.LogisticUnits.md#isactive) | boolean | Indicates whether the logistic unit is currently active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 23.1.2.11` 
| [MeasuredWeight](Logistics.Common.LogisticUnits.md#measuredweight) | decimal (12, 3) __nullable__ | Actual measured weight of the unit in KG. null means unknown. `Filter(eq;ge;le)` 
| [Notes](Logistics.Common.LogisticUnits.md#notes) | string (max) __nullable__ | Notes for this LogisticUnit. `Filter(like)` 
| [ObjectVersion](Logistics.Common.LogisticUnits.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SerialCode](Logistics.Common.LogisticUnits.md#serialcode) | string (32) | Unique serial code of the logistic unit. If GS1 coding is used, this is the SSCC. `Required` `Filter(multi eq;like)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Common.LogisticUnits.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable) | General type of the cargo of the logistic unit. null means unknown or N/A. `Filter(multi eq)` |
| [LogisticUnitType](Logistics.Common.LogisticUnits.md#logisticunittype) | [LogisticUnitTypes](Logistics.Common.LogisticUnitTypes.md) (nullable) | The type of the logistic unit. null means the type is currently unknown. `Filter(multi eq)` |
| [RepresentedAsProduct](Logistics.Common.LogisticUnits.md#representedasproduct) | [Products](General.Products.Products.md) (nullable) | When the logistic unit is also a tradeable item, specifies the product used to trade the unit. The product should uniquely identify only one logistic unit. Note that this is different from a logistic unit containing a single item. null means that the unit is not a tradeable item. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Contents | [LogisticUnitContents](Logistics.Common.LogisticUnitContents.md) | List of `LogisticUnitContent`(Logistics.Common.LogisticUnitContents.md) child objects, based on the `Logistics.Common.LogisticUnitContent.LogisticUnit`(Logistics.Common.LogisticUnitContents.md#logisticunit) back reference 
| Specifications | [LogisticUnitSpecifications](Logistics.Common.LogisticUnitSpecifications.md) | List of `LogisticUnitSpecification<br />`(Logistics.Common.LogisticUnitSpecifications.md) child objects, based on the `Logistics.Common.LogisticUnitSpecification.LogisticUnit`(Logistics.Common.LogisticUnitSpecifications.md#logisticunit) back reference 


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

_Type_: **[LogisticUnitTypes](Logistics.Common.LogisticUnitTypes.md) (nullable)**  
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
_Declaring Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md)**  
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

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnits erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Common.LogisticUnits erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Common_LogisticUnits

Domain API Entity Type: 
Logistics_Common_LogisticUnit

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Common_LogisticUnits?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Common_LogisticUnits?$top=10>

