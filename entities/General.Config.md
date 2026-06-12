---
uid: General.Config
---
# General.Config Entity

**Namespace:** [General](General.md)  

Hierarchical repository of configuration options. Entity: Gen_Config

## Default Visualization
Default Display Text Format:  
_{Id}: {KeyPath}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Config](General.Config.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](General.Config.md#description) | string (254) __nullable__ | The description of this Config. 
| [DisplayText](General.Config.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Config.md#id) | guid |  
| [IsActive](General.Config.md#isactive) | boolean | Indicates whether this config entry is active. Inactive config entries are not taken into account. `Required` `Default(true)` `Filter(eq)` `Introduced in version 19.1` 
| [KeyPath](General.Config.md#keypath) | string (128) | Full path of the configuration option. `Required` `Filter(eq)` `ORD` 
| [KeyValue](General.Config.md#keyvalue) | string (max) __nullable__ | The value of the configuration option. 
| [ObjectVersion](General.Config.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [UserLogin](General.Config.md#userlogin) | string (64) __nullable__ | If not null, the configuration option is specific to the user. `Filter(eq)` 
| [UserMachine](General.Config.md#usermachine) | string (64) __nullable__ | If not null, the configuration option is specific to the machine. `Filter(eq)` 


## Attribute Details

### Description

The description of this Config.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsActive

Indicates whether this config entry is active. Inactive config entries are not taken into account. `Required` `Default(true)` `Filter(eq)` `Introduced in version 19.1`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### KeyPath

Full path of the configuration option. `Required` `Filter(eq)` `ORD`

_Type_: **string (128)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  

### KeyValue

The value of the configuration option.

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

### UserLogin

If not null, the configuration option is specific to the user. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### UserMachine

If not null, the configuration option is specific to the machine. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  


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

[!list limit=1000 erp.entity=General.Config erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Config erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Config?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Config?$top=10>

