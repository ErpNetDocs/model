---
uid: Finance.Assets.DepreciationMethods
---
# Finance.Assets.DepreciationMethods


Depreciation methods. Contains both system-defined and user-defined methods.

## General
Namespace: [Finance.Assets](Finance.Assets.md)  
Repository: Finance.Assets.DepreciationMethods  
Base Table: Ast_Depreciation_Methods  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Assets.DepreciationMethods](Finance.Assets.DepreciationMethods.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table[Required] [Default(&quot;STL&quot;)] 
| [Factor](Finance.Assets.DepreciationMethods.md#factor) | decimal (5, 3) | Factor used in factor depreciation function. Factor < 1 means declining depreciation; >1 - increasing. The depreciation is multiplied for each period by the factor[Required] [Default(1)] 
| [IsSystem](Finance.Assets.DepreciationMethods.md#issystem) | boolean | Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user.[Required] [Default(false)] [Filter(eq)] [ReadOnly] 
| [MonthsInAPeriod](Finance.Assets.DepreciationMethods.md#monthsinaperiod) | int32 | Number of equal valued months calculated with single application of the function[Required] [Default(12)] 
| [Name](Finance.Assets.DepreciationMethods.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multilanguage string[Required] [Filter(like)] 
| [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | Determines when the depreciation starts and when it ends[Required] 
| [StartFromNextMonth](Finance.Assets.DepreciationMethods.md#startfromnextmonth) | boolean | When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month.[Required] [Default(true)] [ReadOnly] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.DepreciationMethods.md#id) | guid |  
| [ObjectVersion](Finance.Assets.DepreciationMethods.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Assets.DepreciationMethods.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Assets.DepreciationMethods.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Assets.DepreciationMethods.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Assets.DepreciationMethods.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DepreciationFunction

Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table[Required] [Default(&quot;STL&quot;)]

Type: **[DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction)**  
Category: **System**  
Allowed values for the `DepreciationFunction`(Finance.Assets.DepreciationMethods.md#depreciationfunction) data attribute  
Allowed Values (Finance.Assets.DepreciationMethodsRepository.DepreciationFunction Enum Members)  

| Value | Description |
| ---- | --- |
| DepreciationChangeByFactor | DepreciationChangeByFactor value. Stored as 'FAC'. <br /> Database Value: 'FAC' <br /> Model Value: 0 <br /> Domain API Value: 'DepreciationChangeByFactor' |
| StraightLine | StraightLine value. Stored as 'STL'. <br /> Database Value: 'STL' <br /> Model Value: 1 <br /> Domain API Value: 'StraightLine' |
| SumOfYearsDigits | SumOfYearsDigits value. Stored as 'SYD'. <br /> Database Value: 'SYD' <br /> Model Value: 2 <br /> Domain API Value: 'SumOfYearsDigits' |
| UserDefinedWithTable | UserDefinedWithTable value. Stored as 'TAB'. <br /> Database Value: 'TAB' <br /> Model Value: 3 <br /> Domain API Value: 'UserDefinedWithTable' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **StraightLine**  
Show in UI: **ShownByDefault**  

### Factor

Factor used in factor depreciation function. Factor < 1 means declining depreciation; >1 - increasing. The depreciation is multiplied for each period by the factor[Required] [Default(1)]

Type: **decimal (5, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### IsSystem

Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user.[Required] [Default(false)] [Filter(eq)] [ReadOnly]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### MonthsInAPeriod

Number of equal valued months calculated with single application of the function[Required] [Default(12)]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **12**  
Show in UI: **ShownByDefault**  

### Name

Multilanguage string[Required] [Filter(like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PeriodDeterminationMethod

Determines when the depreciation starts and when it ends[Required]

Type: **[PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod)**  
Category: **System**  
Allowed values for the `PeriodDeterminationMethod`(Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) data attribute  
Allowed Values (Finance.Assets.DepreciationMethodsRepository.PeriodDeterminationMethod Enum Members)  

| Value | Description |
| ---- | --- |
| NextMonth | NextMonth value. Stored as 'NM'. <br /> Database Value: 'NM' <br /> Model Value: 0 <br /> Domain API Value: 'NextMonth' |
| CurrentMonth | CurrentMonth value. Stored as 'CM'. <br /> Database Value: 'CM' <br /> Model Value: 1 <br /> Domain API Value: 'CurrentMonth' |
| ByDays | ByDays value. Stored as 'BD'. <br /> Database Value: 'BD' <br /> Model Value: 2 <br /> Domain API Value: 'ByDays' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StartFromNextMonth

When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month.[Required] [Default(true)] [ReadOnly]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **CannotBeShown**  

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

