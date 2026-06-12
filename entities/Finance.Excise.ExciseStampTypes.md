---
uid: Finance.Excise.ExciseStampTypes
---
# Finance.Excise.ExciseStampTypes Entity

**Namespace:** [Finance.Excise](Finance.Excise.md)  

The different types of tax stamps (aka Excise Labels) which are applied to the excise products. Tax stamps denote paid or due excise. The types of tax stamps are differentiated by product, capacity, alcoholic strength and other criteria. Entity: Exc_Excise_Stamp_Types (Introduced in version 22.1.5.83)

## Default Visualization
Default Display Text Format:  
_{Code}: {Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Excise.ExciseStampTypes](Finance.Excise.ExciseStampTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AlcoholicStrength](Finance.Excise.ExciseStampTypes.md#alcoholicstrength) | decimal (5, 2) __nullable__ | Percentage of pure alcohol used in excise duty reporting. `Default(0)` 
| [Capacity](Finance.Excise.ExciseStampTypes.md#capacity) | decimal (6, 4) __nullable__ | Package capacity - number of cigarettes or volume of alcohol in liters. `Default(0)` 
| [Category](Finance.Excise.ExciseStampTypes.md#category) | [Category](Finance.Excise.ExciseStampTypes.md#category) | Specifies the excise product category of the excise stamp - alcohol, tobacco, and others. `Required` 
| [Code](Finance.Excise.ExciseStampTypes.md#code) | string (32) | The unique code of the ExciseStampType. `Required` `Filter(multi eq;like)` `ORD` 
| [DisplayText](Finance.Excise.ExciseStampTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExciseAmountPerStamp](Finance.Excise.ExciseStampTypes.md#exciseamountperstamp) | decimal (5, 2) __nullable__ | The excise duty, which is charged with one excise label. `Default(0)` 
| [Id](Finance.Excise.ExciseStampTypes.md#id) | guid |  
| [IsActive](Finance.Excise.ExciseStampTypes.md#isactive) | boolean | Indicates whether this excise stamp type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)` 
| [Name](Finance.Excise.ExciseStampTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this ExciseStampType. `Required` `Filter(like)` 
| [Notes](Finance.Excise.ExciseStampTypes.md#notes) | string (max) __nullable__ | Notes for this ExciseStampType. 
| [ObjectVersion](Finance.Excise.ExciseStampTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CommodityCode](Finance.Excise.ExciseStampTypes.md#commoditycode) | [CommodityCodes](Finance.Intrastat.CommodityCodes.md) | Harmonized commodity code of the products, as defined by EU and/or the applicable authority. `Required` `Filter(multi eq)` |
| [ExciseProduct](Finance.Excise.ExciseStampTypes.md#exciseproduct) | [ExciseProducts](Finance.Excise.ExciseProducts.md) | The excise product, defined by the taxation and customs authorities. `Required` `Filter(multi eq)` |
| [MeasurementUnit](Finance.Excise.ExciseStampTypes.md#measurementunit) | [MeasurementUnits](General.MeasurementUnits.md) (nullable) | The unit of measure in which the product is reported. `Filter(multi eq)` |


## Attribute Details

### AlcoholicStrength

Percentage of pure alcohol used in excise duty reporting. `Default(0)`

_Type_: **decimal (5, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Capacity

Package capacity - number of cigarettes or volume of alcohol in liters. `Default(0)`

_Type_: **decimal (6, 4) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Category

Specifies the excise product category of the excise stamp - alcohol, tobacco, and others. `Required`

_Type_: **[Category](Finance.Excise.ExciseStampTypes.md#category)**  
_Category_: **System**  
Allowed values for the `Category`(Finance.Excise.ExciseStampTypes.md#category) data attribute  
_Allowed Values (Finance.Excise.ExciseStampTypesRepository.Category Enum Members)_  

| Value | Description |
| ---- | --- |
| ExciseStampFor<br />TobaccoProducts | Excise Stamp for Tobacco Products. Stored as 'TT'. <br /> _Database Value:_ 'TT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ExciseStampFor<br />TobaccoProducts' |
| ExciseStampFor<br />AlcoholProducts | Excise Stamp for Alcohol Products . Stored as 'AA'. <br /> _Database Value:_ 'AA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ExciseStampFor<br />AlcoholProducts' |
| DutyFree | Duty Free. Stored as 'DF'. <br /> _Database Value:_ 'DF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'DutyFree' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Code

The unique code of the ExciseStampType. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ExciseAmountPerStamp

The excise duty, which is charged with one excise label. `Default(0)`

_Type_: **decimal (5, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsActive

Indicates whether this excise stamp type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### Name

The name of this ExciseStampType. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### Notes

Notes for this ExciseStampType.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### CommodityCode

Harmonized commodity code of the products, as defined by EU and/or the applicable authority. `Required` `Filter(multi eq)`

_Type_: **[CommodityCodes](Finance.Intrastat.CommodityCodes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### ExciseProduct

The excise product, defined by the taxation and customs authorities. `Required` `Filter(multi eq)`

_Type_: **[ExciseProducts](Finance.Excise.ExciseProducts.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### MeasurementUnit

The unit of measure in which the product is reported. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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



## Business Rules

[!list limit=1000 erp.entity=Finance.Excise.ExciseStampTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Excise.ExciseStampTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Excise_ExciseStampTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Excise_ExciseStampTypes?$top=10>

