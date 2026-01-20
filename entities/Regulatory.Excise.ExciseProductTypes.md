---
uid: Regulatory.Excise.ExciseProductTypes
---
# Regulatory.Excise.ExciseProductTypes Entity

**Namespace:** [Regulatory.Excise](Regulatory.Excise.md)  

The different types of excise products. Excise product types are differentiated by product, capacity, alcoholic strength and other criteria. Entity: Exc_Excise_Product_Types (Introduced in version 22.1.6.44)

## Default Visualization
Default Display Text Format:  
_{Code}: {Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseProductTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [AlcoholicStrength](Regulatory.Excise.ExciseProductTypes.md#alcoholicstrength) | decimal (5, 2) | Percentage of pure alcohol used in excise duty reporting. `Required` `Default(0)` 
| [Capacity](Regulatory.Excise.ExciseProductTypes.md#capacity) | decimal (6, 4) __nullable__ | Package capacity - number of cigarettes or volume of alcohol in liters. `Default(0)` 
| [Category](Regulatory.Excise.ExciseProductTypes.md#category) | [Category](Regulatory.Excise.ExciseProductTypes.md#category) | Specifies the excise product category of the excise stamp - alcohol, tobacco, and others. `Required` 
| [Code](Regulatory.Excise.ExciseProductTypes.md#code) | string (32) | The unique code of the ExciseProductType. `Required` `Filter(multi eq;like)` `ORD` 
| [DisplayText](Regulatory.Excise.ExciseProductTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExciseAmountPerStamp](Regulatory.Excise.ExciseProductTypes.md#exciseamountperstamp) | decimal (10, 6) | The excise duty, which is charged with one excise label. `Required` `Default(0)` 
| [ExternalId](Regulatory.Excise.ExciseProductTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseProductTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Regulatory.Excise.ExciseProductTypes.md#id) | guid |  
| [IsActive](Regulatory.Excise.ExciseProductTypes.md#isactive) | boolean | Indicates whether this excise poduct type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)` 
| [Name](Regulatory.Excise.ExciseProductTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this ExciseProductType. `Required` `Filter(like)` 
| [Notes](Regulatory.Excise.ExciseProductTypes.md#notes) | string (max) __nullable__ | Notes for this ExciseProductType. 
| [ObjectVersion](Regulatory.Excise.ExciseProductTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CommodityCode](Regulatory.Excise.ExciseProductTypes.md#commoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) | Code from The Combined Nomenclature used within the European Union countries. `Required` `Filter(multi eq)` |
| [ExciseProduct](Regulatory.Excise.ExciseProductTypes.md#exciseproduct) | [ExciseProducts](Regulatory.Excise.ExciseProducts.md) | Excise product according to the EU nomenclature for products subject to excise duty. `Required` `Filter(multi eq)` |
| [MeasurementUnit](Regulatory.Excise.ExciseProductTypes.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The unit of measure in which the product is reported. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### AlcoholicStrength

Percentage of pure alcohol used in excise duty reporting. `Required` `Default(0)`

_Type_: **decimal (5, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Capacity

Package capacity - number of cigarettes or volume of alcohol in liters. `Default(0)`

_Type_: **decimal (6, 4) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Category

Specifies the excise product category of the excise stamp - alcohol, tobacco, and others. `Required`

_Type_: **[Category](Regulatory.Excise.ExciseProductTypes.md#category)**  
_Category_: **System**  
Allowed values for the `Category`(Regulatory.Excise.ExciseProductTypes.md#category) data attribute  
_Allowed Values (Regulatory.Excise.ExciseProductTypesRepository.Category Enum Members)_  

| Value | Description |
| ---- | --- |
| ExciseStampFor<br />TobaccoProducts | ExciseStampFor<br />TobaccoProducts value. Stored as 'TT'. <br /> _Database Value:_ 'TT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ExciseStampFor<br />TobaccoProducts' |
| ExciseStampFor<br />AlcoholProducts | ExciseStampFor<br />AlcoholProducts value. Stored as 'AA'. <br /> _Database Value:_ 'AA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ExciseStampFor<br />AlcoholProducts' |
| DutyFree | DutyFree value. Stored as 'DF'. <br /> _Database Value:_ 'DF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'DutyFree' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Code

The unique code of the ExciseProductType. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.GetNextDefaultCode( )`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExciseAmountPerStamp

The excise duty, which is charged with one excise label. `Required` `Default(0)`

_Type_: **decimal (10, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
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

Indicates whether this excise poduct type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this ExciseProductType. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this ExciseProductType.

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


## Reference Details

### CommodityCode

Code from The Combined Nomenclature used within the European Union countries. `Required` `Filter(multi eq)`

_Type_: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExciseProduct

Excise product according to the EU nomenclature for products subject to excise duty. `Required` `Filter(multi eq)`

_Type_: **[ExciseProducts](Regulatory.Excise.ExciseProducts.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MeasurementUnit

The unit of measure in which the product is reported. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseProductTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseProductTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseProductTypes

Domain API Entity Type: 
Regulatory_Excise_ExciseProductType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseProductTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseProductTypes?$top=10>

