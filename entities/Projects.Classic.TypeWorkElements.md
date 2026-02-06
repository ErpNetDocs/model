---
uid: Projects.Classic.TypeWorkElements
---
# Projects.Classic.TypeWorkElements


The work elements of the work breakdown structure of each project type.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.TypeWorkElements  
Base Table: Prj_Type_Work_Elements  
API access:  ReadWrite  

## Visualization
Display Format: {WorkElementName}  
Search Members: WorkElementCode; WorkElementName  
Code Member: WorkElementCode  
Name Member: WorkElementName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.ProjectTypes](Projects.Classic.ProjectTypes.md)  
Aggregate Root:  
[Projects.Classic.ProjectTypes](Projects.Classic.ProjectTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FullPath](Projects.Classic.TypeWorkElements.md#fullpath) | string (25) __nullable__ | The full path of the node in the format of dot-delimited, dot-terminated codes of the parents. 
| [Notes](Projects.Classic.TypeWorkElements.md#notes) | string (max) __nullable__ | Notes for this TypeWorkElement. 
| [ParentFullPath](Projects.Classic.TypeWorkElements.md#parentfullpath) | string (25) __nullable__ | The full path of the parent work element in this project type. NULL when this is root element. 
| [WorkElementCode](Projects.Classic.TypeWorkElements.md#workelementcode) | string (3) | The code of the work element, unique among the sibling elements within the parent work element. 
| [WorkElementName](Projects.Classic.TypeWorkElements.md#workelementname) | string (254) | The name of the work element, unique among the sibling elements within the parent work element. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectType](Projects.Classic.TypeWorkElements.md#projecttype) | [ProjectTypes](Projects.Classic.ProjectTypes.md) | The <see cref="ProjectType"/> to which this TypeWorkElement belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.TypeWorkElements.md#id) | guid |  
| [ObjectVersion](Projects.Classic.TypeWorkElements.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.TypeWorkElements.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FullPath

The full path of the node in the format of dot-delimited, dot-terminated codes of the parents.

Type: **string (25) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **25**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this TypeWorkElement.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ParentFullPath

The full path of the parent work element in this project type. NULL when this is root element.

Type: **string (25) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **25**  
Show in UI: **ShownByDefault**  

### WorkElementCode

The code of the work element, unique among the sibling elements within the parent work element.

Type: **string (3)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **3**  
Show in UI: **ShownByDefault**  

### WorkElementName

The name of the work element, unique among the sibling elements within the parent work element.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals**  
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

### ProjectType

The <see cref="ProjectType"/> to which this TypeWorkElement belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ProjectTypes](Projects.Classic.ProjectTypes.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Projects.Classic.TypeWorkElements erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.TypeWorkElements erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_TypeWorkElements

Domain API Entity Type: 
Projects_Classic_TypeWorkElement

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_TypeWorkElements?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_TypeWorkElements?$top=10>

