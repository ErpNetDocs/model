---
uid: Systems.Bpm.UserBusinessRuleConditions
---
# Systems.Bpm.UserBusinessRuleConditions


Represents one condition for the execution of a business rule.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.UserBusinessRuleConditions  
Base Table: Sys_User_Business_Rule_Conditions  
API access:  ReadWrite  

## Visualization
Display Format: {AttributeName}  
Search Members: AttributeName  
Name Member: AttributeName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  
Aggregate Root:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AttributeName](Systems.Bpm.UserBusinessRuleConditions.md#attributename) | string (64) | The attribute, which will be tested. 
| [ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) | [ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) | How to compare the attribute and the value of the condition - e.g. Attribute-Comparison-Value. 
| [ConditionNo](Systems.Bpm.UserBusinessRuleConditions.md#conditionno) | int32 | Unique consecutive number of the condition within the business rule. 
| [Notes](Systems.Bpm.UserBusinessRuleConditions.md#notes) | string (max) __nullable__ | Notes for this UserBusinessRuleCondition. `Introduced in version 20.1` 
| [Value](Systems.Bpm.UserBusinessRuleConditions.md#value) | string (254) __nullable__ | The value against which the data attribute will be tested. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleConditions.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The business rule, for which the condition is defined. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.UserBusinessRuleConditions.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.UserBusinessRuleConditions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Bpm.UserBusinessRuleConditions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AttributeName

The attribute, which will be tested.

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ComparisonType

How to compare the attribute and the value of the condition - e.g. Attribute-Comparison-Value.

Type: **[ComparisonType](Systems.Bpm.UserBusinessRuleConditions.md#comparisontype)**  
Category: **System**  
Allowed values for the `ComparisonType`(Systems.Bpm.UserBusinessRuleConditions.md#comparisontype) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRuleConditionsRepository.ComparisonType Enum Members)  

| Value | Description |
| ---- | --- |
| Equals | Equals. Stored as 'Equals'. <br /> Database Value: 'Equals' <br /> Model Value: 0 <br /> Domain API Value: 'Equals' |
| Greater_Than | Greater Than Or Equal. Stored as 'Greater_Than'. <br /> Database Value: 'Greater_Than' <br /> Model Value: 1 <br /> Domain API Value: 'Greater_Than' |
| Less_Than | Less Than Or Equal. Stored as 'Less_Than'. <br /> Database Value: 'Less_Than' <br /> Model Value: 2 <br /> Domain API Value: 'Less_Than' |
| Like | Compare by mask. Use * (asterisk) as wildcard char.. Stored as 'Like'. <br /> Database Value: 'Like' <br /> Model Value: 3 <br /> Domain API Value: 'Like' |
| IsNull | Field is null.. Stored as 'IsNull'. <br /> Database Value: 'IsNull' <br /> Model Value: 4 <br /> Domain API Value: 'IsNull' |
| Not_Equals | Not Equals. Stored as 'Not_Equals'. <br /> Database Value: 'Not_Equals' <br /> Model Value: 5 <br /> Domain API Value: 'Not_Equals' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Equals**  
Show in UI: **ShownByDefault**  

### ConditionNo

Unique consecutive number of the condition within the business rule.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.UserBusinessRule.Conditions.Select( c => c.ConditionNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.UserBusinessRule.Conditions.Select( c => c.ConditionNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this UserBusinessRuleCondition. `Introduced in version 20.1`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Value

The value against which the data attribute will be tested.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### UserBusinessRule

The business rule, for which the condition is defined.

Type: **[UserBusinessRules](Systems.Bpm.UserBusinessRules.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

