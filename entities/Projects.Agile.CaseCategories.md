---
uid: Projects.Agile.CaseCategories
---
# Projects.Agile.CaseCategories


Determines the type and workflow of the cases.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.CaseCategories  
Base Table: Apm_Case_Categories  
Introduced In Version: 24.1.1.84  
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
* [Projects.Agile.CaseCategories](Projects.Agile.CaseCategories.md)  
  * [Projects.Agile.CaseCategoryRelationships](Projects.Agile.CaseCategoryRelationships.md)  
  * [Projects.Agile.ProjectTypeCaseCategories](Projects.Agile.ProjectTypeCaseCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DescriptionTemplate](Projects.Agile.CaseCategories.md#descriptiontemplate) | string (max) __nullable__ | Interpolated string that sets a value for the Description field when creating new cases of this category.[Filter(like)] [Introduced in version 25.1.2.76] 
| [HideUnusedSystemStates](Projects.Agile.CaseCategories.md#hideunusedsystemstates) | boolean | If enabled, system states without at least one active user state will be hidden for cases of this category. If there are no active user states, all system states will be shown.[Required] [Default(false)] [Filter(eq)] [Introduced in version 25.1.3.32] 
| [Icon](Projects.Agile.CaseCategories.md#icon) | string (128) __nullable__ | Icon name from the Font Awesome icon set. 
| [IsActive](Projects.Agile.CaseCategories.md#isactive) | boolean | Specifies whether the category is active for new cases.[Required] [Default(true)] [Filter(eq)] 
| [Name](Projects.Agile.CaseCategories.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Use short, singular phrase to describe a category of cases[Required] [Filter(like)] 
| [Notes](Projects.Agile.CaseCategories.md#notes) | string (max) __nullable__ | Notes for this CaseCategory. 
| [Ord](Projects.Agile.CaseCategories.md#ord) | int32 | Display order of the category relative to other categories within the project type.[Required] [Default(1)] [Filter(eq)] 
| [RequiresParent](Projects.Agile.CaseCategories.md#requiresparent) | boolean | Specifies whether a parent case is required for cases of this category.[Required] [Default(false)] [Filter(eq)] [Introduced in version 25.1.3.39] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.CaseCategories.md#id) | guid |  
| [ObjectVersion](Projects.Agile.CaseCategories.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.CaseCategories.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.CaseCategories.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.CaseCategories.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.CaseCategories.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ProjectTypeCaseCategories | [ProjectTypeCaseCategories](Projects.Agile.ProjectTypeCaseCategories.md) | List of `ProjectTypeCaseCategory`(Projects.Agile.ProjectTypeCaseCategories.md) child objects, based on the `Projects.Agile.ProjectTypeCaseCategory.CaseCategory`(Projects.Agile.ProjectTypeCaseCategories.md#casecategory) back reference 
| Relationships | [CaseCategoryRelationships](Projects.Agile.CaseCategoryRelationships.md) | List of `CaseCategoryRelationship`(Projects.Agile.CaseCategoryRelationships.md) child objects, based on the `Projects.Agile.CaseCategoryRelationship.ChildCaseCategory`(Projects.Agile.CaseCategoryRelationships.md#childcasecategory) back reference 


## Attribute Details

### DescriptionTemplate

Interpolated string that sets a value for the Description field when creating new cases of this category.[Filter(like)] [Introduced in version 25.1.2.76]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### HideUnusedSystemStates

If enabled, system states without at least one active user state will be hidden for cases of this category. If there are no active user states, all system states will be shown.[Required] [Default(false)] [Filter(eq)] [Introduced in version 25.1.3.32]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Icon

Icon name from the Font Awesome icon set.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the category is active for new cases.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Use short, singular phrase to describe a category of cases[Required] [Filter(like)]

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this CaseCategory.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Ord

Display order of the category relative to other categories within the project type.[Required] [Default(1)] [Filter(eq)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### RequiresParent

Specifies whether a parent case is required for cases of this category.[Required] [Default(false)] [Filter(eq)] [Introduced in version 25.1.3.39]

Type: **boolean**  
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

[!list limit=1000 erp.entity=Projects.Agile.CaseCategories erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.CaseCategories erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_CaseCategories

Domain API Entity Type: 
Projects_Agile_CaseCategory

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_CaseCategories?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_CaseCategories?$top=10>

