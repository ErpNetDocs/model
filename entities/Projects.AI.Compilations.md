---
uid: Projects.AI.Compilations
---
# Projects.AI.Compilations


Compilation is a conversation-ready build of a model. It is created through the Build compilation function of a model.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.Compilations  
Base Table: Llm_Compilations  
Introduced In Version: 24.1.2.4  
API access:  ReadWrite  

## Visualization
Display Format: {CompiledModelName}  
Search Members: CompiledModelName  
Name Member: CompiledModelName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.Compilations](Projects.AI.Compilations.md)  
  * [Projects.AI.CompilationAssets](Projects.AI.CompilationAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BuildLog](Projects.AI.Compilations.md#buildlog) | string (max) __nullable__ | Detailed log of the build process of the compilation.[ReadOnly] 
| [CompiledModelName](Projects.AI.Compilations.md#compiledmodelname) | string (256) __nullable__ | The name of the model, which was created in the providers space, as a result of the compilation.[Filter(eq;like)] [ReadOnly] 
| [CompletionTimeUtc](Projects.AI.Compilations.md#completiontimeutc) | datetime __nullable__ | The time, when the compilation has completed.[Filter(eq;ge;le)] [ORD] [ReadOnly] 
| [ErrorMessage](Projects.AI.Compilations.md#errormessage) | string (max) __nullable__ | Human-readable error message indicating the problem, when a build is not successful.[ReadOnly] 
| [IsSuccessful](Projects.AI.Compilations.md#issuccessful) | boolean | Indicated whether the build process was successful and the compilation can be used for conversations.[Required] [Default(false)] [Filter(eq)] [ReadOnly] 
| [StartTimeUtc](Projects.AI.Compilations.md#starttimeutc) | datetime | The time, when the compilation was started.[Required] [Default(NowUtc)] [Filter(eq;ge;le)] [ORD] [ReadOnly] 
| [Status](Projects.AI.Compilations.md#status) | [Status](Projects.AI.Compilations.md#status) | The status of the build job of the compilation. Building the compilation runs through New, Running and Completed. Deleting the compilation from the providers space marks it as Deleted.[Required] [Default(&quot;N&quot;)] [Filter(multi eq)] [ReadOnly] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Model](Projects.AI.Compilations.md#model) | [Models](Projects.AI.Models.md) | The model, on which the compilation is based. |
| [User](Projects.AI.Compilations.md#user) | [Users](Systems.Security.Users.md) | The user, who started the compilation. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.Compilations.md#id) | guid |  
| [ObjectVersion](Projects.AI.Compilations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.AI.Compilations.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.Compilations.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.AI.Compilations.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.AI.Compilations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Assets | [CompilationAssets](Projects.AI.CompilationAssets.md) | List of `CompilationAsset`(Projects.AI.CompilationAssets.md) child objects, based on the `Projects.AI.CompilationAsset.Compilation`(Projects.AI.CompilationAssets.md#compilation) back reference 


## Attribute Details

### BuildLog

Detailed log of the build process of the compilation.[ReadOnly]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### CompiledModelName

The name of the model, which was created in the providers space, as a result of the compilation.[Filter(eq;like)] [ReadOnly]

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### CompletionTimeUtc

The time, when the compilation has completed.[Filter(eq;ge;le)] [ORD] [ReadOnly]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### ErrorMessage

Human-readable error message indicating the problem, when a build is not successful.[ReadOnly]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### IsSuccessful

Indicated whether the build process was successful and the compilation can be used for conversations.[Required] [Default(false)] [Filter(eq)] [ReadOnly]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### StartTimeUtc

The time, when the compilation was started.[Required] [Default(NowUtc)] [Filter(eq;ge;le)] [ORD] [ReadOnly]

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Status

The status of the build job of the compilation. Building the compilation runs through New, Running and Completed. Deleting the compilation from the providers space marks it as Deleted.[Required] [Default(&quot;N&quot;)] [Filter(multi eq)] [ReadOnly]

Type: **[Status](Projects.AI.Compilations.md#status)**  
Category: **System**  
Allowed values for the `Status`(Projects.AI.Compilations.md#status) data attribute  
Allowed Values (Projects.AI.CompilationsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Running | Running value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Running' |
| Completed | Completed value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 2 <br /> Domain API Value: 'Completed' |
| Deleted | Deleted value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 3 <br /> Domain API Value: 'Deleted' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **New**  
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


## Reference Details

### Model

The model, on which the compilation is based.

Type: **[Models](Projects.AI.Models.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, who started the compilation.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

