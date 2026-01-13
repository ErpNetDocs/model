---
uid: Finance.Assets.DepreciationMethods
---
# Finance.Assets.DepreciationMethods Entity

**Namespace:** [Finance.Assets](Finance.Assets.md)  

Depreciation methods. Contains both system-defined and user-defined methods. Entity: Ast_Depreciation_Methods

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
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
* [Finance.Assets.DepreciationMethods](Finance.Assets.DepreciationMethods.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table. `Required` `Default("STL")` 
| [DisplayText](Finance.Assets.DepreciationMethods.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Finance.Assets.DepreciationMethods.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Assets.DepreciationMethods.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Factor](Finance.Assets.DepreciationMethods.md#factor) | decimal (5, 3) | Factor used in factor depreciation function. Factor &lt; 1 means declining depreciation; &gt;1 - increasing. The depreciation is multiplied for each period by the factor. `Required` `Default(1)` 
| [Id](Finance.Assets.DepreciationMethods.md#id) | guid |  
| [IsSystem](Finance.Assets.DepreciationMethods.md#issystem) | boolean | Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [MonthsInAPeriod](Finance.Assets.DepreciationMethods.md#monthsinaperiod) | int32 | Number of equal valued months calculated with single application of the function. `Required` `Default(12)` 
| [Name](Finance.Assets.DepreciationMethods.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multilanguage string. `Required` `Filter(like)` 
| [ObjectVersion](Finance.Assets.DepreciationMethods.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | Determines when the depreciation starts and when it ends. NM=Next_Month, CM=Current_Month, BD=By_Days. `Required` 
| [StartFromNextMonth](Finance.Assets.DepreciationMethods.md#startfromnextmonth) | boolean | When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month. `Required` `Default(true)` `ReadOnly` 


## Attribute Details

### DepreciationFunction

Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table. `Required` `Default("STL")`

_Type_: **[DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction)**  
_Category_: **System**  
Allowed values for the `DepreciationFunction`(Finance.Assets.DepreciationMethods.md#depreciationfunction) data attribute  
_Allowed Values (Finance.Assets.DepreciationMethodsRepository.DepreciationFunction Enum Members)_  

| Value | Description |
| ---- | --- |
| DepreciationChangeByFactor | DepreciationChangeByFactor value. Stored as 'FAC'. <br /> _Database Value:_ 'FAC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DepreciationChangeByFactor' |
| StraightLine | StraightLine value. Stored as 'STL'. <br /> _Database Value:_ 'STL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'StraightLine' |
| SumOfYearsDigits | SumOfYearsDigits value. Stored as 'SYD'. <br /> _Database Value:_ 'SYD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'SumOfYearsDigits' |
| UserDefinedWithTable | UserDefinedWithTable value. Stored as 'TAB'. <br /> _Database Value:_ 'TAB' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'UserDefinedWithTable' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **StraightLine**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### Factor

Factor used in factor depreciation function. Factor &lt; 1 means declining depreciation; &gt;1 - increasing. The depreciation is multiplied for each period by the factor. `Required` `Default(1)`

_Type_: **decimal (5, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsSystem

Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### MonthsInAPeriod

Number of equal valued months calculated with single application of the function. `Required` `Default(12)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **12**  
_Show in UI_: **ShownByDefault**  

### Name

Multilanguage string. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PeriodDeterminationMethod

Determines when the depreciation starts and when it ends. NM=Next_Month, CM=Current_Month, BD=By_Days. `Required`

_Type_: **[PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod)**  
_Category_: **System**  
Allowed values for the `PeriodDeterminationMethod`(Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) data attribute  
_Allowed Values (Finance.Assets.DepreciationMethodsRepository.PeriodDeterminationMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| NextMonth | NextMonth value. Stored as 'NM'. <br /> _Database Value:_ 'NM' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NextMonth' |
| CurrentMonth | CurrentMonth value. Stored as 'CM'. <br /> _Database Value:_ 'CM' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CurrentMonth' |
| ByDays | ByDays value. Stored as 'BD'. <br /> _Database Value:_ 'BD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ByDays' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StartFromNextMonth

When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month. `Required` `Default(true)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **CannotBeShown**  


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

[!list limit=1000 erp.entity=Finance.Assets.DepreciationMethods erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.DepreciationMethods erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_DepreciationMethods

Domain API Entity Type: 
Finance_Assets_DepreciationMethod

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_DepreciationMethods?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_DepreciationMethods?$top=10>

