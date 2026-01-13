---
uid: General.Currencies.CurrencyDirectoryLines
---
# General.Currencies.CurrencyDirectoryLines Entity

**Namespace:** [General.Currencies](General.Currencies.md)  

Contains exchange rate for a currency against the main currency of currency directory. Entity: Gen_Currency_Directory_Lines

## Renames

Old name: **General.CurrencyDirectoryLines**  
New name: **General.Currencies.CurrencyDirectoryLines**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{CurrencyDirectory.Name}_  
Default Search Members:  
_CurrencyDirectory.Name_  
Name Data Member:  
_CurrencyDirectory.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Currencies.CurrencyDirectories](General.Currencies.CurrencyDirectories.md)  
Aggregate Root:  
[General.Currencies.CurrencyDirectories](General.Currencies.CurrencyDirectories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](General.Currencies.CurrencyDirectoryLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Currencies.CurrencyDirectoryLines.md#id) | guid |  
| [ObjectVersion](General.Currencies.CurrencyDirectoryLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RateDivisor](General.Currencies.CurrencyDirectoryLines.md#ratedivisor) | decimal (18, 6) | The divisor for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)` 
| [RateMultiplier](General.Currencies.CurrencyDirectoryLines.md#ratemultiplier) | decimal (18, 6) | The multiplier for conversion from From_Currency to Directory.To_Currency. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrencyDirectory](General.Currencies.CurrencyDirectoryLines.md#currencydirectory) | [CurrencyDirectories](General.Currencies.CurrencyDirectories.md) | The <see cref="CurrencyDirectory"/> to which this CurrencyDirectoryLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [FromCurrency](General.Currencies.CurrencyDirectoryLines.md#fromcurrency) | [Currencies](General.Currencies.Currencies.md) | The currency for which the exchange rate is recorded. `Required` `Filter(multi eq)` |


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

_Type_: **[CurrencyDirectories](General.Currencies.CurrencyDirectories.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### FromCurrency

The currency for which the exchange rate is recorded. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
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

[!list limit=1000 erp.entity=General.Currencies.CurrencyDirectoryLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Currencies.CurrencyDirectoryLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Currencies_CurrencyDirectoryLines

Domain API Entity Type: 
General_Currencies_CurrencyDirectoryLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Currencies_CurrencyDirectoryLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Currencies_CurrencyDirectoryLines?$top=10>

