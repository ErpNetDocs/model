---
uid: Projects.Agile.CaseCategories
---
# Projects.Agile.CaseCategories Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Determines the type and workflow of the cases. Entity: Apm_Case_Categories (Introduced in version 24.1.1.84)

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
* [Projects.Agile.CaseCategories](Projects.Agile.CaseCategories.md)  
  * [Projects.Agile.CaseCategoryRelationships](Projects.Agile.CaseCategoryRelationships.md)  
  * [Projects.Agile.ProjectTypeCaseCategories](Projects.Agile.ProjectTypeCaseCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DescriptionTemplate](Projects.Agile.CaseCategories.md#descriptiontemplate) | string (max) __nullable__ | Interpolated string that sets a value for the Description field when creating new cases of this category. `Filter(like)` `Introduced in version 25.1.2.76` 
| [DisplayText](Projects.Agile.CaseCategories.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Agile.CaseCategories.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.CaseCategories.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [HideUnusedSystemStates](Projects.Agile.CaseCategories.md#hideunusedsystemstates) | boolean | If enabled, system states without at least one active user state will be hidden for cases of this category. If there are no active user states, all system states will be shown. `Required` `Default(false)` `Filter(eq)` `Introduced in version 25.1.3.32` 
| [Icon](Projects.Agile.CaseCategories.md#icon) | string (128) __nullable__ | Icon name from the Font Awesome icon set. 
| [Id](Projects.Agile.CaseCategories.md#id) | guid |  
| [IsActive](Projects.Agile.CaseCategories.md#isactive) | boolean | Specifies whether the category is active for new cases. `Required` `Default(true)` `Filter(eq)` 
| [Name](Projects.Agile.CaseCategories.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Use short, singular phrase to describe a category of cases. `Required` `Filter(like)` 
| [Notes](Projects.Agile.CaseCategories.md#notes) | string (max) __nullable__ | Notes for this CaseCategory. 
| [ObjectVersion](Projects.Agile.CaseCategories.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](Projects.Agile.CaseCategories.md#ord) | int32 | Display order of the category relative to other categories within the project type. `Required` `Default(1)` `Filter(eq)` 
| [RequiresParent](Projects.Agile.CaseCategories.md#requiresparent) | boolean | Specifies whether a parent case is required for cases of this category. `Required` `Default(false)` `Filter(eq)` `Introduced in version 25.1.3.39` 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ProjectTypeCaseCategories | [ProjectTypeCaseCategories](Projects.Agile.ProjectTypeCaseCategories.md) | List of `ProjectTypeCaseCategory`(Projects.Agile.ProjectTypeCaseCategories.md) child objects, based on the `Projects.Agile.ProjectTypeCaseCategory.CaseCategory`(Projects.Agile.ProjectTypeCaseCategories.md#casecategory) back reference 
| Relationships | [CaseCategoryRelationships](Projects.Agile.CaseCategoryRelationships.md) | List of `CaseCategoryRelationship`(Projects.Agile.CaseCategoryRelationships.md) child objects, based on the `Projects.Agile.CaseCategoryRelationship.ChildCaseCategory`(Projects.Agile.CaseCategoryRelationships.md#childcasecategory) back reference 


## Attribute Details

### DescriptionTemplate

Interpolated string that sets a value for the Description field when creating new cases of this category. `Filter(like)` `Introduced in version 25.1.2.76`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
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

### HideUnusedSystemStates

If enabled, system states without at least one active user state will be hidden for cases of this category. If there are no active user states, all system states will be shown. `Required` `Default(false)` `Filter(eq)` `Introduced in version 25.1.3.32`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Icon

Icon name from the Font Awesome icon set.

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Specifies whether the category is active for new cases. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Use short, singular phrase to describe a category of cases. `Required` `Filter(like)`

_Type_: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this CaseCategory.

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

### Ord

Display order of the category relative to other categories within the project type. `Required` `Default(1)` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### RequiresParent

Specifies whether a parent case is required for cases of this category. `Required` `Default(false)` `Filter(eq)` `Introduced in version 25.1.3.39`

_Type_: **boolean**  
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

