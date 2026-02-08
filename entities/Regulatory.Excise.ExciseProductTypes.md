---
uid: Regulatory.Excise.ExciseProductTypes
---
# Regulatory.Excise.ExciseProductTypes


The different types of excise products. Excise product types are differentiated by product, capacity, alcoholic strength and other criteria.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseProductTypes  
Base Table: Exc_Excise_Product_Types  
Introduced In Version: 22.1.6.44  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.ExciseProductTypes  
New name: Regulatory.Excise.ExciseProductTypes  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {Code}: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AlcoholicStrength](Regulatory.Excise.ExciseProductTypes.md#alcoholicstrength) | decimal (5, 2) | Percentage of pure alcohol used in excise duty reporting.`Required` `Default(0)` 
| [Capacity](Regulatory.Excise.ExciseProductTypes.md#capacity) | decimal (6, 4) __nullable__ | Package capacity - number of cigarettes or volume of alcohol in liters.`Default(0)` 
| [Category](Regulatory.Excise.ExciseProductTypes.md#category) | [Category](Regulatory.Excise.ExciseProductTypes.md#category) | Specifies the excise product category of the excise stamp - alcohol, tobacco, and others.`Required` 
| [Code](Regulatory.Excise.ExciseProductTypes.md#code) | string (32) | The unique code of the ExciseProductType. `Required` `Filter(multi eq;like)` `ORD` 
| [ExciseAmountPerStamp](Regulatory.Excise.ExciseProductTypes.md#exciseamountperstamp) | decimal (10, 6) | The excise duty, which is charged with one excise label.`Required` `Default(0)` 
| [IsActive](Regulatory.Excise.ExciseProductTypes.md#isactive) | boolean | Indicates whether this excise poduct type is active and usable for choosing in new documents.`Required` `Default(true)` `Filter(eq)` 
| [Name](Regulatory.Excise.ExciseProductTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this ExciseProductType. `Required` `Filter(like)` 
| [Notes](Regulatory.Excise.ExciseProductTypes.md#notes) | string (max) __nullable__ | Notes for this ExciseProductType. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CommodityCode](Regulatory.Excise.ExciseProductTypes.md#commoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) | Code from The Combined Nomenclature used within the European Union countries. |
| [ExciseProduct](Regulatory.Excise.ExciseProductTypes.md#exciseproduct) | [ExciseProducts](Regulatory.Excise.ExciseProducts.md) | Excise product according to the EU nomenclature for products subject to excise duty. |
| [MeasurementUnit](Regulatory.Excise.ExciseProductTypes.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The unit of measure in which the product is reported. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseProductTypes.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseProductTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.ExciseProductTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseProductTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseProductTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.ExciseProductTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AlcoholicStrength

Percentage of pure alcohol used in excise duty reporting.`Required` `Default(0)`

Type: **decimal (5, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Capacity

Package capacity - number of cigarettes or volume of alcohol in liters.`Default(0)`

Type: **decimal (6, 4) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Category

Specifies the excise product category of the excise stamp - alcohol, tobacco, and others.`Required`

Type: **[Category](Regulatory.Excise.ExciseProductTypes.md#category)**  
Category: **System**  
Allowed values for the `Category`(Regulatory.Excise.ExciseProductTypes.md#category) data attribute  
Allowed Values (Regulatory.Excise.ExciseProductTypesRepository.Category Enum Members)  

| Value | Description |
| ---- | --- |
| ExciseStampFor<br />TobaccoProducts | ExciseStampFor<br />TobaccoProducts value. Stored as 'TT'. <br /> Database Value: 'TT' <br /> Model Value: 0 <br /> Domain API Value: 'ExciseStampFor<br />TobaccoProducts' |
| ExciseStampFor<br />AlcoholProducts | ExciseStampFor<br />AlcoholProducts value. Stored as 'AA'. <br /> Database Value: 'AA' <br /> Model Value: 1 <br /> Domain API Value: 'ExciseStampFor<br />AlcoholProducts' |
| DutyFree | DutyFree value. Stored as 'DF'. <br /> Database Value: 'DF' <br /> Model Value: 2 <br /> Domain API Value: 'DutyFree' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Code

The unique code of the ExciseProductType. `Required` `Filter(multi eq;like)` `ORD`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.GetNextDefaultCode( )`

### ExciseAmountPerStamp

The excise duty, which is charged with one excise label.`Required` `Default(0)`

Type: **decimal (10, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether this excise poduct type is active and usable for choosing in new documents.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this ExciseProductType. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ExciseProductType.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### CommodityCode

Code from The Combined Nomenclature used within the European Union countries.

Type: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseProduct

Excise product according to the EU nomenclature for products subject to excise duty.

Type: **[ExciseProducts](Regulatory.Excise.ExciseProducts.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MeasurementUnit

The unit of measure in which the product is reported.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
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

