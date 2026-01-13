---
uid: Applications.DataWarehouse.DataMeasures
---
# Applications.DataWarehouse.DataMeasures Entity

**Namespace:** [Applications.DataWarehouse](Applications.DataWarehouse.md)  

Contains the data measures of the General data warehouse. Entity: Dw_Data_Measures (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{Name}_  
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
* [Applications.DataWarehouse.DataMeasures](Applications.DataWarehouse.DataMeasures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Applications.DataWarehouse.DataMeasures.md#code) | string (16) | Unique measure code. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Applications.DataWarehouse.DataMeasures.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Applications.DataWarehouse.DataMeasures.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.DataWarehouse.DataMeasures.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [GreenZoneSpreadPercent](Applications.DataWarehouse.DataMeasures.md#greenzonespreadpercent) | decimal (3, 2) | The plus or minus percent, by which the goal can be missed, but still considered achieved. `Required` `Default(0.2)` `Filter(eq)` 
| [HorizontalTrend<br />SpreadPercent](Applications.DataWarehouse.DataMeasures.md#horizontaltrendspreadpercent) | decimal (3, 2) | The change in percents, which is considered neutral. Higher positive/negative changes are considered positive/negative trends. `Required` `Default(0.01)` `Filter(eq)` 
| [Id](Applications.DataWarehouse.DataMeasures.md#id) | guid |  
| [Name](Applications.DataWarehouse.DataMeasures.md#name) | string (254) | The name of the measure (multilanguage). `Required` `Filter(eq;like)` 
| [Notes](Applications.DataWarehouse.DataMeasures.md#notes) | string (max) __nullable__ | Notes for this DataMeasure. 
| [ObjectVersion](Applications.DataWarehouse.DataMeasures.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Period](Applications.DataWarehouse.DataMeasures.md#period) | [Period](Applications.DataWarehouse.DataMeasures.md#period) | The period for which the data is collected. D=Day, M=Month, Q=Quarter, Y=Year. `Required` `Default("Q")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataMeasureGroup](Applications.DataWarehouse.DataMeasures.md#datameasuregroup) | [DataMeasureGroups](Applications.DataWarehouse.DataMeasureGroups.md) | The group to which this measure belongs. `Required` `Filter(multi eq)` |


## Attribute Details

### Code

Unique measure code. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
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

### GreenZoneSpreadPercent

The plus or minus percent, by which the goal can be missed, but still considered achieved. `Required` `Default(0.2)` `Filter(eq)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **0.2**  
_Show in UI_: **ShownByDefault**  

### HorizontalTrendSpreadPercent

The change in percents, which is considered neutral. Higher positive/negative changes are considered positive/negative trends. `Required` `Default(0.01)` `Filter(eq)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **0.01**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

The name of the measure (multilanguage). `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this DataMeasure.

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

### Period

The period for which the data is collected. D=Day, M=Month, Q=Quarter, Y=Year. `Required` `Default("Q")` `Filter(eq)`

_Type_: **[Period](Applications.DataWarehouse.DataMeasures.md#period)**  
_Category_: **System**  
Allowed values for the `Period`(Applications.DataWarehouse.DataMeasures.md#period) data attribute  
_Allowed Values (Applications.DataWarehouse.DataMeasuresRepository.Period Enum Members)_  

| Value | Description |
| ---- | --- |
| Day | Day value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Day' |
| Month | Month value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Month' |
| Quarter | Quarter value. Stored as 'Q'. <br /> _Database Value:_ 'Q' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Quarter' |
| Year | Year value. Stored as 'Y'. <br /> _Database Value:_ 'Y' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Year' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Quarter**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataMeasureGroup

The group to which this measure belongs. `Required` `Filter(multi eq)`

_Type_: **[DataMeasureGroups](Applications.DataWarehouse.DataMeasureGroups.md)**  
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

[!list limit=1000 erp.entity=Applications.DataWarehouse.DataMeasures erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.DataWarehouse.DataMeasures erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_DataWarehouse_DataMeasures

Domain API Entity Type: 
Applications_DataWarehouse_DataMeasure

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_DataWarehouse_DataMeasures?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_DataWarehouse_DataMeasures?$top=10>

