---
uid: Systems.Bpm.UserBusinessRules
---
# Systems.Bpm.UserBusinessRules Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represents user-defined business rule. Entity: Sys_User_Business_Rules

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Track Changes  
Min level:  _3 - Track object and attribute changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Systems.Bpm.UserBusinessRules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Icon](Systems.Bpm.UserBusinessRules.md#icon) | byte[] __nullable__ | Visual icon of the rule in .PNG format. 
| [Id](Systems.Bpm.UserBusinessRules.md#id) | guid |  
| [IsActive](Systems.Bpm.UserBusinessRules.md#isactive) | boolean | Specifies whether the rule is activated. `Required` `Default(false)` `Filter(eq)` 
| [Layer](Systems.Bpm.UserBusinessRules.md#layer) | [Layer](Systems.Bpm.UserBusinessRules.md#layer) | Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both). `Required` `Default("BKE")` `Filter(multi eq)` 
| [Name](Systems.Bpm.UserBusinessRules.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this UserBusinessRule. `Required` `Filter(like)` 
| [Notes](Systems.Bpm.UserBusinessRules.md#notes) | string (max) __nullable__ | Notes for this UserBusinessRule. 
| [ObjectVersion](Systems.Bpm.UserBusinessRules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RepositoryName](Systems.Bpm.UserBusinessRules.md#repositoryname) | string (128) | The name of the repository, for which this business rule is defined. `Required` `Filter(eq;like)` 
| [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage) | [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage) | The programming language used to define the rule actions. `Required` `Default("Integrated")` 
| [ScriptText](Systems.Bpm.UserBusinessRules.md#scripttext) | string (max) __nullable__ | The program code used to define the rule actions. 
| [UserStartable](Systems.Bpm.UserBusinessRules.md#userstartable) | boolean __nullable__ | Specifies, that the rule can be manually started by the user. `Default(false)` `Filter(eq)` 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Actions | [UserBusinessRuleActions](Systems.Bpm.UserBusinessRuleActions.md) | List of `UserBusinessRuleAction`(Systems.Bpm.UserBusinessRuleActions.md) child objects, based on the `Systems.Bpm.UserBusinessRuleAction.UserBusinessRule`(Systems.Bpm.UserBusinessRuleActions.md#userbusinessrule) back reference 
| Conditions | [UserBusinessRuleConditions](Systems.Bpm.UserBusinessRuleConditions.md) | List of `UserBusinessRule<br />Condition`(Systems.Bpm.UserBusinessRuleConditions.md) child objects, based on the `Systems.Bpm.UserBusinessRuleCondition.UserBusinessRule`(Systems.Bpm.UserBusinessRuleConditions.md#userbusinessrule) back reference 
| Events | [UserBusinessRuleEvents](Systems.Bpm.UserBusinessRuleEvents.md) | List of `UserBusinessRuleEvent`(Systems.Bpm.UserBusinessRuleEvents.md) child objects, based on the `Systems.Bpm.UserBusinessRuleEvent.UserBusinessRule`(Systems.Bpm.UserBusinessRuleEvents.md#userbusinessrule) back reference 


## Attribute Details

### Code

The unique code of the UserBusinessRule. `Required` `Filter(eq;like)` `ORD`

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

### Icon

Visual icon of the rule in .PNG format.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Specifies whether the rule is activated. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Layer

Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both). `Required` `Default("BKE")` `Filter(multi eq)`

_Type_: **[Layer](Systems.Bpm.UserBusinessRules.md#layer)**  
_Category_: **System**  
Allowed values for the `Layer`(Systems.Bpm.UserBusinessRules.md#layer) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRulesRepository.Layer Enum Members)_  

| Value | Description |
| ---- | --- |
| FrontEnd | The rule is registered for front-end applications.. Stored as 'FTE'. <br /> _Database Value:_ 'FTE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'FrontEnd' |
| BackEnd | The rule is registered for server execution.. Stored as 'BKE'. <br /> _Database Value:_ 'BKE' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BackEnd' |
| Common | The rule is registered both for server and client.. Stored as 'COM'. <br /> _Database Value:_ 'COM' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Common' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **BackEnd**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this UserBusinessRule. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this UserBusinessRule.

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

### RepositoryName

The name of the repository, for which this business rule is defined. `Required` `Filter(eq;like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### ScriptLanguage

The programming language used to define the rule actions. `Required` `Default("Integrated")`

_Type_: **[ScriptLanguage](Systems.Bpm.UserBusinessRules.md#scriptlanguage)**  
_Category_: **System**  
Allowed values for the `ScriptLanguage`(Systems.Bpm.UserBusinessRules.md#scriptlanguage) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRulesRepository.ScriptLanguage Enum Members)_  

| Value | Description |
| ---- | --- |
| Integrated | Integrated value. Stored as 'Integrated'. <br /> _Database Value:_ 'Integrated' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Integrated' |
| CSharp | CSharp value. Stored as 'CSharp'. <br /> _Database Value:_ 'CSharp' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CSharp' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Integrated**  
_Show in UI_: **ShownByDefault**  

### ScriptText

The program code used to define the rule actions.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### UserStartable

Specifies, that the rule can be manually started by the user. `Default(false)` `Filter(eq)`

_Type_: **boolean __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
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


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRules?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRules?$top=10>

