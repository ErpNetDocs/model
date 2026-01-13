---
uid: Systems.Bpm.UserBusinessRuleConditions
---
# Systems.Bpm.UserBusinessRuleConditions Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represents one condition for the execution of a business rule. Entity: Sys_User_Business_Rule_Conditions

## Default Visualization
Default Display Text Format:  
_{AttributeName}_  
Default Search Members:  
_AttributeName_  
Name Data Member:  
_AttributeName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  
Aggregate Root:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AttributeName](Systems.Bpm.UserBusinessRuleConditions.md#attributename) | string (64) | The attribute, which will be tested. `Required` 
| [ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) | [ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) | How to compare the attribute and the value of the condition - e.g. Attribute-Comparison-Value. `Required` `Default("Equals")` 
| [ConditionNo](Systems.Bpm.UserBusinessRuleConditions.md#conditionno) | int32 | Unique consecutive number of the condition within the business rule. `Required` 
| [DisplayText](Systems.Bpm.UserBusinessRuleConditions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Bpm.UserBusinessRuleConditions.md#id) | guid |  
| [Notes](Systems.Bpm.UserBusinessRuleConditions.md#notes) | string (max) __nullable__ | Notes for this UserBusinessRuleCondition. `Introduced in version 20.1` 
| [ObjectVersion](Systems.Bpm.UserBusinessRuleConditions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Value](Systems.Bpm.UserBusinessRuleConditions.md#value) | string (254) __nullable__ | The value against which the data attribute will be tested. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleConditions.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The business rule, for which the condition is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### AttributeName

The attribute, which will be tested. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ComparisonType

How to compare the attribute and the value of the condition - e.g. Attribute-Comparison-Value. `Required` `Default("Equals")`

_Type_: **[ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype)**  
_Category_: **System**  
Allowed values for the `ComparisonType`(Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRuleConditionsRepository.ComparisonType Enum Members)_  

| Value | Description |
| ---- | --- |
| Equals | Equals. Stored as 'Equals'. <br /> _Database Value:_ 'Equals' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Equals' |
| Greater_Than | Greater Than Or Equal. Stored as 'Greater_Than'. <br /> _Database Value:_ 'Greater_Than' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Greater_Than' |
| Less_Than | Less Than Or Equal. Stored as 'Less_Than'. <br /> _Database Value:_ 'Less_Than' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Less_Than' |
| Like | Compare by mask. Use * (asterisk) as wildcard char.. Stored as 'Like'. <br /> _Database Value:_ 'Like' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Like' |
| IsNull | Field is null.. Stored as 'IsNull'. <br /> _Database Value:_ 'IsNull' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'IsNull' |
| Not_Equals | Not Equals. Stored as 'Not_Equals'. <br /> _Database Value:_ 'Not_Equals' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Not_Equals' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Equals**  
_Show in UI_: **ShownByDefault**  

### ConditionNo

Unique consecutive number of the condition within the business rule. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.UserBusinessRule.Conditions.Select( c => c.ConditionNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.UserBusinessRule.Conditions.Select( c => c.ConditionNo).DefaultIfEmpty( 0).Max( ) + 10)`
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

### Notes

Notes for this UserBusinessRuleCondition. `Introduced in version 20.1`

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

### Value

The value against which the data attribute will be tested.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### UserBusinessRule

The business rule, for which the condition is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[UserBusinessRules](Systems.Bpm.UserBusinessRules.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleConditions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleConditions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_UserBusinessRuleConditions

Domain API Entity Type: 
Systems_Bpm_UserBusinessRuleCondition

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRuleConditions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRuleConditions?$top=10>

