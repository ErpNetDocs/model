---
uid: Projects.TypeWorkElements
---
# Projects.TypeWorkElements Entity

**Namespace:** [Projects](Projects.md)  

The work elements of the work breakdown structure of each project type. Entity: Prj_Type_Work_Elements

## Default Visualization
Default Display Text Format:  
_{WorkElementName}_  
Default Search Members:  
_WorkElementCode; WorkElementName_  
Code Data Member:  
_WorkElementCode_  
Name Data Member:  
_WorkElementName_  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.ProjectTypes](Projects.ProjectTypes.md)  
Aggregate Root:  
[Projects.ProjectTypes](Projects.ProjectTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Projects.TypeWorkElements.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FullPath](Projects.TypeWorkElements.md#fullpath) | string (25) __nullable__ | The full path of the node in the format of dot-delimited, dot-terminated codes of the parents. `Filter(eq;like)` `ReadOnly` 
| [Id](Projects.TypeWorkElements.md#id) | guid |  
| [Notes](Projects.TypeWorkElements.md#notes) | string (max) __nullable__ | Notes for this TypeWorkElement. 
| [ObjectVersion](Projects.TypeWorkElements.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentFullPath](Projects.TypeWorkElements.md#parentfullpath) | string (25) __nullable__ | The full path of the parent work element in this project type. null when this is root element. `Filter(eq;like)` 
| [WorkElementCode](Projects.TypeWorkElements.md#workelementcode) | string (3) | The code of the work element, unique among the sibling elements within the parent work element. `Required` `Filter(eq)` 
| [WorkElementName](Projects.TypeWorkElements.md#workelementname) | string (254) | The name of the work element, unique among the sibling elements within the parent work element. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectType](Projects.TypeWorkElements.md#projecttype) | [ProjectTypes](Projects.ProjectTypes.md) | The <see cref="ProjectType"/> to which this TypeWorkElement belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FullPath

The full path of the node in the format of dot-delimited, dot-terminated codes of the parents. `Filter(eq;like)` `ReadOnly`

_Type_: **string (25) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **25**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this TypeWorkElement.

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

### ParentFullPath

The full path of the parent work element in this project type. null when this is root element. `Filter(eq;like)`

_Type_: **string (25) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **25**  
_Show in UI_: **ShownByDefault**  

### WorkElementCode

The code of the work element, unique among the sibling elements within the parent work element. `Required` `Filter(eq)`

_Type_: **string (3)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **3**  
_Show in UI_: **ShownByDefault**  

### WorkElementName

The name of the work element, unique among the sibling elements within the parent work element. `Required` `Filter(eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ProjectType

The <see cref="ProjectType"/> to which this TypeWorkElement belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProjectTypes](Projects.ProjectTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Projects.TypeWorkElements erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.TypeWorkElements erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TypeWorkElements?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TypeWorkElements?$top=10>

