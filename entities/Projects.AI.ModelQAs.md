---
uid: Projects.AI.ModelQAs
---
# Projects.AI.ModelQAs


Questions and desired answers, forming the actual knowledge base of the model.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.ModelQAs  
Base Table: Llm_Model_QAs  
Introduced In Version: 24.1.1.93  
API access:  ReadWrite  

## Visualization
Display Format: {Model.Name:T}  
Search Members: Model.Name  
Name Member: Model.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.AI.Models](Projects.AI.Models.md)  
Aggregate Root:  
[Projects.AI.Models](Projects.AI.Models.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Answer](Projects.AI.ModelQAs.md#answer) | string (max) | Desired answer.`Required` `Filter(like)` 
| [CreationTimeUtc](Projects.AI.ModelQAs.md#creationtimeutc) | datetime | The time when the QA was created.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [DeactivatonTimeUtc](Projects.AI.ModelQAs.md#deactivatontimeutc) | datetime __nullable__ | The time when the QA was deactivated.`Filter(eq;ge;le)` `ReadOnly` 
| [IsActive](Projects.AI.ModelQAs.md#isactive) | boolean | Indicates whether to include this QA in future builds.`Required` `Default(true)` `Filter(eq)` 
| [Notes](Projects.AI.ModelQAs.md#notes) | string (max) __nullable__ | Notes for this ModelQA. 
| [QAType](Projects.AI.ModelQAs.md#qatype) | [QAType](Projects.AI.ModelQAs.md#qatype) | Specifies whether the QA is training or validation. Validation QAs are used to test the correctness of the model and are only reported in the build logs.`Required` `Default(&quot;T&quot;)` `Filter(eq)` 
| [Question](Projects.AI.ModelQAs.md#question) | string (max) | User question.`Required` `Filter(like)` 
| [Section](Projects.AI.ModelQAs.md#section) | string (128) | Free text organizational section of the QA.`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AddedByUser](Projects.AI.ModelQAs.md#addedbyuser) | [Users](Systems.Security.Users.md) | The user which added the QA. |
| [Model](Projects.AI.ModelQAs.md#model) | [Models](Projects.AI.Models.md) | The model to which the question belongs. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.ModelQAs.md#id) | guid |  
| [ObjectVersion](Projects.AI.ModelQAs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.AI.ModelQAs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Answer

Desired answer.`Required` `Filter(like)`

Type: **string (max)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The time when the QA was created.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### DeactivatonTimeUtc

The time when the QA was deactivated.`Filter(eq;ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether to include this QA in future builds.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ModelQA.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### QAType

Specifies whether the QA is training or validation. Validation QAs are used to test the correctness of the model and are only reported in the build logs.`Required` `Default(&quot;T&quot;)` `Filter(eq)`

Type: **[QAType](Projects.AI.ModelQAs.md#qatype)**  
Category: **System**  
Allowed values for the `QAType`(Projects.AI.ModelQAs.md#qatype) data attribute  
Allowed Values (Projects.AI.ModelQAsRepository.QAType Enum Members)  

| Value | Description |
| ---- | --- |
| Training | Training value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 0 <br /> Domain API Value: 'Training' |
| Validation | Validation value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 1 <br /> Domain API Value: 'Validation' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Training**  
Show in UI: **ShownByDefault**  

### Question

User question.`Required` `Filter(like)`

Type: **string (max)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Section

Free text organizational section of the QA.`Required`

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
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

### AddedByUser

The user which added the QA.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Model

The model to which the question belongs.

Type: **[Models](Projects.AI.Models.md)**  
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

[!list limit=1000 erp.entity=Projects.AI.ModelQAs erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.ModelQAs erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_ModelQAs

Domain API Entity Type: 
Projects_AI_ModelQA

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_ModelQAs?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_ModelQAs?$top=10>

