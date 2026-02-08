---
uid: Systems.Bpm.UserBusinessRules
---
# Systems.Bpm.UserBusinessRules


Represents user-defined business rule.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.UserBusinessRules  
Base Table: Sys_User_Business_Rules  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  
  * [Systems.Bpm.UserBusinessRuleActions](Systems.Bpm.UserBusinessRuleActions.md)  
  * [Systems.Bpm.UserBusinessRuleConditions](Systems.Bpm.UserBusinessRuleConditions.md)  
  * [Systems.Bpm.UserBusinessRuleEvents](Systems.Bpm.UserBusinessRuleEvents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Bpm.UserBusinessRules.md#code) | string (16) | The unique code of the UserBusinessRule. `Required` `Filter(eq;like)` `ORD` 
| [Icon](Systems.Bpm.UserBusinessRules.md#icon) | byte[] __nullable__ | Visual icon of the rule. Valid formats are: .JPG, .PNG, .SVG, .ICO 
| [IsActive](Systems.Bpm.UserBusinessRules.md#isactive) | boolean | Specifies whether the rule is activated.`Required` `Default(false)` `Filter(eq)` 
| [Layer](Systems.Bpm.UserBusinessRules.md#layer) | [Layer](Systems.Bpm.UserBusinessRules.md#layer) | Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both).`Required` `Default(&quot;BKE&quot;)` `Filter(multi eq)` 
| [Name](Systems.Bpm.UserBusinessRules.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this UserBusinessRule. `Required` `Filter(like)` 
| [Notes](Systems.Bpm.UserBusinessRules.md#notes) | string (max) __nullable__ | Notes for this UserBusinessRule. 
| [RepositoryName](Systems.Bpm.UserBusinessRules.md#repositoryname) | string (128) | The name of the repository, for which this business rule is defined.`Required` `Filter(eq;like)` 
| [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage) | [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage) | The programming language used to define the rule actions.`Required` `Default(&quot;Integrated&quot;)` 
| [ScriptText](Systems.Bpm.UserBusinessRules.md#scripttext) | string (max) __nullable__ | The program code used to define the rule actions. 
| [UserStartable](Systems.Bpm.UserBusinessRules.md#userstartable) | boolean __nullable__ | Specifies, that the rule can be manually started by the user.`Default(false)` `Filter(eq)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.UserBusinessRules.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.UserBusinessRules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Bpm.UserBusinessRules.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Bpm.UserBusinessRules.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Bpm.UserBusinessRules.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Bpm.UserBusinessRules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Actions | [UserBusinessRuleActions](Systems.Bpm.UserBusinessRuleActions.md) | List of `UserBusinessRuleAction`(Systems.Bpm.UserBusinessRuleActions.md) child objects, based on the `Systems.Bpm.UserBusinessRuleAction.UserBusinessRule`(Systems.Bpm.UserBusinessRuleActions.md#userbusinessrule) back reference 
| Conditions | [UserBusinessRuleConditions](Systems.Bpm.UserBusinessRuleConditions.md) | List of `UserBusinessRule<br />Condition`(Systems.Bpm.UserBusinessRuleConditions.md) child objects, based on the `Systems.Bpm.UserBusinessRuleCondition.UserBusinessRule`(Systems.Bpm.UserBusinessRuleConditions.md#userbusinessrule) back reference 
| Events | [UserBusinessRuleEvents](Systems.Bpm.UserBusinessRuleEvents.md) | List of `UserBusinessRuleEvent`(Systems.Bpm.UserBusinessRuleEvents.md) child objects, based on the `Systems.Bpm.UserBusinessRuleEvent.UserBusinessRule`(Systems.Bpm.UserBusinessRuleEvents.md#userbusinessrule) back reference 


## Attribute Details

### Code

The unique code of the UserBusinessRule. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Icon

Visual icon of the rule. Valid formats are: .JPG, .PNG, .SVG, .ICO

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the rule is activated.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Layer

Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both).`Required` `Default(&quot;BKE&quot;)` `Filter(multi eq)`

Type: **[Layer](Systems.Bpm.UserBusinessRules.md#layer)**  
Category: **System**  
Allowed values for the `Layer`(Systems.Bpm.UserBusinessRules.md#layer) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRulesRepository.Layer Enum Members)  

| Value | Description |
| ---- | --- |
| FrontEnd | The rule is registered for front-end applications.. Stored as 'FTE'. <br /> Database Value: 'FTE' <br /> Model Value: 0 <br /> Domain API Value: 'FrontEnd' |
| BackEnd | The rule is registered for server execution.. Stored as 'BKE'. <br /> Database Value: 'BKE' <br /> Model Value: 1 <br /> Domain API Value: 'BackEnd' |
| Common | The rule is registered both for server and client.. Stored as 'COM'. <br /> Database Value: 'COM' <br /> Model Value: 2 <br /> Domain API Value: 'Common' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **BackEnd**  
Show in UI: **ShownByDefault**  

### Name

The name of this UserBusinessRule. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this UserBusinessRule.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RepositoryName

The name of the repository, for which this business rule is defined.`Required` `Filter(eq;like)`

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### ScriptLanguage

The programming language used to define the rule actions.`Required` `Default(&quot;Integrated&quot;)`

Type: **[ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage)**  
Category: **System**  
Allowed values for the `ScriptLanguage`(Systems.Bpm.UserBusinessRules.md#scriptlanguage) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRulesRepository.ScriptLanguage Enum Members)  

| Value | Description |
| ---- | --- |
| Integrated | Integrated value. Stored as 'Integrated'. <br /> Database Value: 'Integrated' <br /> Model Value: 0 <br /> Domain API Value: 'Integrated' |
| CSharp | CSharp value. Stored as 'CSharp'. <br /> Database Value: 'CSharp' <br /> Model Value: 1 <br /> Domain API Value: 'CSharp' |
| JavaScript | JavaScript value. Stored as 'JavaScript'. <br /> Database Value: 'JavaScript' <br /> Model Value: 2 <br /> Domain API Value: 'JavaScript' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Integrated**  
Show in UI: **ShownByDefault**  

### ScriptText

The program code used to define the rule actions.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### UserStartable

Specifies, that the rule can be manually started by the user.`Default(false)` `Filter(eq)`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
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

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_UserBusinessRules

Domain API Entity Type: 
Systems_Bpm_UserBusinessRule

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRules?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRules?$top=10>

