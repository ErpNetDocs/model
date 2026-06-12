---
uid: Projects.AI.ModelBuilds
---
# Projects.AI.ModelBuilds Entity

**Namespace:** [Projects.AI](Projects.AI.md)  

Successive builds of sub-models, containing the QAs available at the time of the build. Created automatically by the Build now function in the model. Entity: Llm_Model_Builds (Introduced in version 24.1.1.93)

## Default Visualization
Default Display Text Format:  
_{JobName}_  
Default Search Members:  
_JobName_  
Name Data Member:  
_JobName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.AI.Models](Projects.AI.Models.md)  
Aggregate Root:  
[Projects.AI.Models](Projects.AI.Models.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BuildCompletionTimeUtc](Projects.AI.ModelBuilds.md#buildcompletiontimeutc) | datetime __nullable__ | The time when the build was completed. `Filter(eq;ge;le)` `ReadOnly` 
| [BuildLog](Projects.AI.ModelBuilds.md#buildlog) | string (max) __nullable__ | Build log, as returned by the model provider. `ReadOnly` 
| [BuildStartTimeUtc](Projects.AI.ModelBuilds.md#buildstarttimeutc) | datetime | The time when the build job was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly` 
| [DisplayText](Projects.AI.ModelBuilds.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.AI.ModelBuilds.md#id) | guid |  
| [JobName](Projects.AI.ModelBuilds.md#jobname) | string (256) __nullable__ | The name of the build job in the provider cloud. null if the provider does not support job names. `Filter(eq;like)` `ReadOnly` `Introduced in version 24.1.1.94` 
| [ObjectVersion](Projects.AI.ModelBuilds.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ResultModelName](Projects.AI.ModelBuilds.md#resultmodelname) | string (256) __nullable__ | The name of the model, which was created by the build. Updated after the build job completes. `Filter(eq;like)` `ReadOnly` 
| [Status](Projects.AI.ModelBuilds.md#status) | [Status](Projects.AI.ModelBuilds.md#status) | Indicates the status of the build - New, Running or Completed. `Required` `Default("N")` `Filter(multi eq)` `ReadOnly` 
| [Success](Projects.AI.ModelBuilds.md#success) | boolean | Indicates whether the build was successfully built. `Required` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BuildUser](Projects.AI.ModelBuilds.md#builduser) | [Users](Systems.Security.Users.md) | The user which started the build. `Required` `Filter(multi eq)` `ReadOnly` |
| [Model](Projects.AI.ModelBuilds.md#model) | [Models](Projects.AI.Models.md) | The <see cref="Model"/> to which this ModelBuild belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |


## Attribute Details

### BuildCompletionTimeUtc

The time when the build was completed. `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BuildLog

Build log, as returned by the model provider. `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### BuildStartTimeUtc

The time when the build job was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### JobName

The name of the build job in the provider cloud. null if the provider does not support job names. `Filter(eq;like)` `ReadOnly` `Introduced in version 24.1.1.94`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ResultModelName

The name of the model, which was created by the build. Updated after the build job completes. `Filter(eq;like)` `ReadOnly`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Status

Indicates the status of the build - New, Running or Completed. `Required` `Default("N")` `Filter(multi eq)` `ReadOnly`

_Type_: **[Status](Projects.AI.ModelBuilds.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Projects.AI.ModelBuilds.md#status) data attribute  
_Allowed Values (Projects.AI.ModelBuildsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Running | Running value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Running' |
| Completed | Completed value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Completed' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  

### Success

Indicates whether the build was successfully built. `Required` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BuildUser

The user which started the build. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Model

The <see cref="Model"/> to which this ModelBuild belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[Models](Projects.AI.Models.md)**  
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

[!list limit=1000 erp.entity=Projects.AI.ModelBuilds erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.ModelBuilds erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_AI_ModelBuilds?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_AI_ModelBuilds?$top=10>

