---
uid: Systems.Bpm.CalculatedAttributes
---
# Systems.Bpm.CalculatedAttributes


User-defined read-only calculated attribute.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.CalculatedAttributes  
Base Table: Sys_Calculated_Attributes  
API access:  ReadWrite  

## Visualization
Display Format: {Caption:T}   
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)  
  * [Systems.Bpm.CalculatedAttributeExpressions](Systems.Bpm.CalculatedAttributeExpressions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Caption](Systems.Bpm.CalculatedAttributes.md#caption) | [MultilanguageString (512)](../data-types.md#multilanguagestring) | The multi-language caption, used to display the attribute.`Required` 
| [Hint](Systems.Bpm.CalculatedAttributes.md#hint) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The hint, which is displayed alongside the attribute.`Filter(multi eq;like)` `Introduced in version 21.1.3.53` 
| [IsActive](Systems.Bpm.CalculatedAttributes.md#isactive) | boolean | True if the attribute is activated and added to the repository.`Required` `Default(false)` `Filter(eq)` 
| [Name](Systems.Bpm.CalculatedAttributes.md#name) | string (128) | The unique name of the attribute within the repository.`Required` `Filter(eq;like)` 
| [Notes](Systems.Bpm.CalculatedAttributes.md#notes) | string (max) __nullable__ | Notes for this CalculatedAttribute. 
| [RepositoryName](Systems.Bpm.CalculatedAttributes.md#repositoryname) | string (128) | The repository, for which the attribute is defined.`Required` `Filter(multi eq)` `ORD` 
| [ScriptLanguage](Systems.Bpm.CalculatedAttributes.md#scriptlanguage) | [ScriptLanguage](Systems.Bpm.CalculatedAttributes.md#scriptlanguage) | The programming language used to evaluate the attribute. `Required` `Default("Integrated")` `Introduced in version 26.2.1.16` 
| [ScriptText](Systems.Bpm.CalculatedAttributes.md#scripttext) | string (max) __nullable__ | The program code that defines how the attribute is evaluated. `Introduced in version 26.2.1.16` 
| [StartingExpressionNo](Systems.Bpm.CalculatedAttributes.md#startingexpressionno) | int32 | The expression, from which the calculation starts. The result of the expression gives the value of the calculated attribute.`Required` `Default(10)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.CalculatedAttributes.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.CalculatedAttributes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Bpm.CalculatedAttributes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Bpm.CalculatedAttributes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Bpm.CalculatedAttributes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Bpm.CalculatedAttributes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Expressions | [CalculatedAttributeExpressions](Systems.Bpm.CalculatedAttributeExpressions.md) | List of `CalculatedAttribute<br />Expression`(Systems.Bpm.CalculatedAttribute<br />Expressions.md) child objects, based on the `Systems.Bpm.CalculatedAttribute<br />Expression.CalculatedAttribute`(Systems.Bpm.CalculatedAttribute<br />Expressions.md#calculatedattribute) back reference 


## Attribute Details

### Caption

The multi-language caption, used to display the attribute.`Required`

Type: **[MultilanguageString (512)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Hint

The hint, which is displayed alongside the attribute.`Filter(multi eq;like)` `Introduced in version 21.1.3.53`

Type: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

True if the attribute is activated and added to the repository.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The unique name of the attribute within the repository.`Required` `Filter(eq;like)`

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this CalculatedAttribute.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RepositoryName

The repository, for which the attribute is defined.`Required` `Filter(multi eq)` `ORD`

Type: **string (128)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### ScriptLanguage

The programming language used to evaluate the attribute. `Required` `Default("Integrated")` `Introduced in version 26.2.1.16`

Type: **[ScriptLanguage](Systems.Bpm.CalculatedAttributes.md#scriptlanguage)**  
Category: **System**  
Allowed values for the `ScriptLanguage`(Systems.Bpm.CalculatedAttributes.md#scriptlanguage) data attribute  
Allowed Values (Systems.Bpm.CalculatedAttributesRepository.ScriptLanguage Enum Members)  

| Value | Description |
| ---- | --- |
| Integrated | Integrated value. Stored as 'Integrated'. <br /> Database Value: 'Integrated' <br /> Model Value: 0 <br /> Domain API Value: 'Integrated' |
| JavaScript | JavaScript value. Stored as 'JavaScript'. <br /> Database Value: 'JavaScript' <br /> Model Value: 1 <br /> Domain API Value: 'JavaScript' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Integrated**  
Show in UI: **ShownByDefault**  

### ScriptText

The program code that defines how the attribute is evaluated. `Introduced in version 26.2.1.16`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### StartingExpressionNo

The expression, from which the calculation starts. The result of the expression gives the value of the calculated attribute.`Required` `Default(10)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **10**  
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

[!list limit=1000 erp.entity=Systems.Bpm.CalculatedAttributes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.CalculatedAttributes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_CalculatedAttributes

Domain API Entity Type: 
Systems_Bpm_CalculatedAttribute

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_CalculatedAttributes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_CalculatedAttributes?$top=10>

