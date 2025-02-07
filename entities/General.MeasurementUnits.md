---
uid: General.MeasurementUnits
---
# General.MeasurementUnits Entity

**Namespace:** [General](General.md)  

Contains all measurement units, grouped in categories. Each category has one base unit (with ratio 1/1) and unlimited number of derived units with fixed ratio to the base unit. Entity: Gen_Measurement_Units
## Renamed
**New name:** [General.Products.MeasurementUnits](General.Products.MeasurementUnits.md)  



## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.MeasurementCategories](General.MeasurementCategories.md)  
Aggregate Root:  
[General.MeasurementCategories](General.MeasurementCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.MeasurementUnits.md#code) | string (16) __nullable__ | When not null, contains unique measurement unit code. `Filter(eq;like)` `ORD` 
| [Description](General.MeasurementUnits.md#description) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | Full multi-language description of the measurement unit. 
| [DisplayText](General.MeasurementUnits.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Divisor](General.MeasurementUnits.md#divisor) | decimal (9, 3) | Divisor of the relative value of the measurement unit against other units (divisor when converting to base). `Required` `Default(1)` 
| [Id](General.MeasurementUnits.md#id) | guid |  
| [IsDefaultUnit](General.MeasurementUnits.md#isdefaultunit) | boolean | True if this measurement unit is the default measurement unit within the category. There can be only one default measurement unit within a category. `Required` `Default(false)` `Filter(eq)` 
| [Multiplier](General.MeasurementUnits.md#multiplier) | decimal (9, 3) | Multiplier of the relative value of the measurement unit against other units (multiplier when converting to base). `Required` `Default(1)` 
| [Name](General.MeasurementUnits.md#name) | [MultilanguageString (64)](../data-types.md#multilanguagestring) | Name of the measurement unit. `Required` `Filter(eq;like)` 
| [ObjectVersion](General.MeasurementUnits.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SystemUnit](General.MeasurementUnits.md#systemunit) | [SystemUnit](General.MeasurementUnits.md#systemunit) __nullable__ | Not null only when this is one of the system measurement units. N=NetKG; G=GrossKG; V=VolumeL; H=HeightM; W=WidthM, L=LengthM, P=Piece, T=TimeH. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MeasurementCategory](General.MeasurementUnits.md#measurementcategory) | [MeasurementCategories](General.MeasurementCategories.md) | Base measurement category Id. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Code

When not null, contains unique measurement unit code. `Filter(eq;like)` `ORD`

_Type_: **string (16) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### Description

Full multi-language description of the measurement unit.

_Type_: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Divisor

Divisor of the relative value of the measurement unit against other units (divisor when converting to base). `Required` `Default(1)`

_Type_: **decimal (9, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsDefaultUnit

True if this measurement unit is the default measurement unit within the category. There can be only one default measurement unit within a category. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Multiplier

Multiplier of the relative value of the measurement unit against other units (multiplier when converting to base). `Required` `Default(1)`

_Type_: **decimal (9, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### Name

Name of the measurement unit. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SystemUnit

Not null only when this is one of the system measurement units. N=NetKG; G=GrossKG; V=VolumeL; H=HeightM; W=WidthM, L=LengthM, P=Piece, T=TimeH. `Filter(eq;like)`

_Type_: **[SystemUnit](General.MeasurementUnits.md#systemunit) __nullable__**  
_Category_: **System**  
Allowed values for the `SystemUnit`(General.MeasurementUnits.md#systemunit) data attribute  
_Allowed Values (General.MeasurementUnitsRepository.SystemUnit Enum Members)_  

| Value | Description |
| ---- | --- |
| GrossKilograms | GrossKilograms value. Stored as 'G'. <br /> _Database Value:_ 'G' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'GrossKilograms' |
| HeightMeters | HeightMeters value. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'HeightMeters' |
| LengthMeters | LengthMeters value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'LengthMeters' |
| NetKilograms | NetKilograms value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'NetKilograms' |
| Pieces | Pieces value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Pieces' |
| VolumeLiters | VolumeLiters value. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'VolumeLiters' |
| WidthMeters | WidthMeters value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'WidthMeters' |
| TimeHours | TimeHours value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'TimeHours' |

_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### MeasurementCategory

Base measurement category Id. `Required` `Filter(multi eq)` `Owner`

_Type_: **[MeasurementCategories](General.MeasurementCategories.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


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


### CreateNotification

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=General.MeasurementUnits erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.MeasurementUnits erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_MeasurementUnits?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_MeasurementUnits?$top=10>

