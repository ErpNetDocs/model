---
uid: Projects.AI.Compilations
---
# Projects.AI.Compilations Entity

**Namespace:** [Projects.AI](Projects.AI.md)  

Compilation is created, when a Model is being compiled through the AI provider into a conversational model. Entity: Llm_Compilations (Introduced in version 24.1.2.4)

## Default Visualization
Default Display Text Format:  
_{CompiledModelName}_  
Default Search Members:  
_CompiledModelName_  
Name Data Member:  
_CompiledModelName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.Compilations](Projects.AI.Compilations.md)  
  * [Projects.AI.CompilationAssets](Projects.AI.CompilationAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Projects.AI.Compilations.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [BuildLog](Projects.AI.Compilations.md#buildlog) | string (max) __nullable__ | Detailed log of the build process of the compilation. `ReadOnly` 
| [CompiledModelName](Projects.AI.Compilations.md#compiledmodelname) | string (256) __nullable__ | The name of the model, which was created in the providers space, as a result of the compilation. `Filter(eq;like)` `ReadOnly` 
| [CompletionTimeUtc](Projects.AI.Compilations.md#completiontimeutc) | datetime __nullable__ | The time, when the compilation has completed. `Filter(eq;ge;le)` `ORD` `ReadOnly` 
| [DisplayText](Projects.AI.Compilations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ErrorMessage](Projects.AI.Compilations.md#errormessage) | string (max) __nullable__ | Human-readable error message indicating the problem, when a build is not successful. `ReadOnly` 
| [ExternalId](Projects.AI.Compilations.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.Compilations.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.AI.Compilations.md#id) | guid |  
| [IsSuccessful](Projects.AI.Compilations.md#issuccessful) | boolean | Indicated whether the build process was successful and the compilation can be used for conversations. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [ObjectVersion](Projects.AI.Compilations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartTimeUtc](Projects.AI.Compilations.md#starttimeutc) | datetime | The time, when the compilation was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly` 
| [Status](Projects.AI.Compilations.md#status) | [Status](Projects.AI.Compilations.md#status) | The status of the build job of the compilation. Building the compilation runs through New, Running and Completed. Deleting the compilation from the providers space marks it as Deleted. `Required` `Default("N")` `Filter(multi eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Model](Projects.AI.Compilations.md#model) | [Models](Projects.AI.Models.md) | The model, on which the compilation is based. `Required` `Filter(multi eq)` `ReadOnly` |
| [User](Projects.AI.Compilations.md#user) | [Users](Systems.Security.Users.md) | The user, who started the compilation. `Required` `Filter(multi eq)` `ReadOnly` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Assets | [CompilationAssets](Projects.AI.CompilationAssets.md) | List of `CompilationAsset`(Projects.AI.CompilationAssets.md) child objects, based on the `Projects.AI.CompilationAsset.Compilation`(Projects.AI.CompilationAssets.md#compilation) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### BuildLog

Detailed log of the build process of the compilation. `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### CompiledModelName

The name of the model, which was created in the providers space, as a result of the compilation. `Filter(eq;like)` `ReadOnly`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### CompletionTimeUtc

The time, when the compilation has completed. `Filter(eq;ge;le)` `ORD` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ErrorMessage

Human-readable error message indicating the problem, when a build is not successful. `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsSuccessful

Indicated whether the build process was successful and the compilation can be used for conversations. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartTimeUtc

The time, when the compilation was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Status

The status of the build job of the compilation. Building the compilation runs through New, Running and Completed. Deleting the compilation from the providers space marks it as Deleted. `Required` `Default("N")` `Filter(multi eq)` `ReadOnly`

_Type_: **[Status](Projects.AI.Compilations.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Projects.AI.Compilations.md#status) data attribute  
_Allowed Values (Projects.AI.CompilationsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Running | Running value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Running' |
| Completed | Completed value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Completed' |
| Deleted | Deleted value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Deleted' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Model

The model, on which the compilation is based. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Models](Projects.AI.Models.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user, who started the compilation. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Projects.AI.Compilations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.Compilations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_Compilations

Domain API Entity Type: 
Projects_AI_Compilation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_Compilations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_Compilations?$top=10>

