---
uid: General.CurrencyDirectoryLines
---
# General.CurrencyDirectoryLines Entity

**Namespace:** [General](General.md)  

Contains exchange rate for a currency against the main currency of currency directory. Entity: Gen_Currency_Directory_Lines
## Renamed
**New name:** [General.Currencies.CurrencyDirectoryLines](General.Currencies.CurrencyDirectoryLines.md)  



## Default Visualization
Default Display Text Format:  
_{CurrencyDirectory.Name}_  
Default Search Members:  
_CurrencyDirectory.Name_  
Name Data Member:  
_CurrencyDirectory.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.CurrencyDirectories](General.CurrencyDirectories.md)  
Aggregate Root:  
[General.CurrencyDirectories](General.CurrencyDirectories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](General.CurrencyDirectoryLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.CurrencyDirectoryLines.md#id) | guid |  
| [ObjectVersion](General.CurrencyDirectoryLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RateDivisor](General.CurrencyDirectoryLines.md#ratedivisor) | decimal (18, 6) | The divisor for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)` 
| [RateMultiplier](General.CurrencyDirectoryLines.md#ratemultiplier) | decimal (18, 6) | The multiplier for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrencyDirectory](General.CurrencyDirectoryLines.md#currencydirectory) | [CurrencyDirectories](General.CurrencyDirectories.md) | The <see cref="CurrencyDirectory"/> to which this CurrencyDirectoryLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [FromCurrency](General.CurrencyDirectoryLines.md#fromcurrency) | [Currencies](General.Currencies.md) | The currency for which the exchange rate is recorded. `Required` `Filter(multi eq)` |


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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RateDivisor

The divisor for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### RateMultiplier

The multiplier for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CurrencyDirectory

The <see cref="CurrencyDirectory"/> to which this CurrencyDirectoryLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[CurrencyDirectories](General.CurrencyDirectories.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### FromCurrency

The currency for which the exchange rate is recorded. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.md)**  
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

[!list limit=1000 erp.entity=General.CurrencyDirectoryLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.CurrencyDirectoryLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_CurrencyDirectoryLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_CurrencyDirectoryLines?$top=10>

