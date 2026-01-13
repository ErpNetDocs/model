---
uid: Projects.AI.ModelQAs
---
# Projects.AI.ModelQAs Entity

**Namespace:** [Projects.AI](Projects.AI.md)  

Questions and desired answers, forming the actual knowledge base of the model. Entity: Llm_Model_QAs (Introduced in version 24.1.1.93)

## Default Visualization
Default Display Text Format:  
_{Model.Name:T}_  
Default Search Members:  
_Model.Name_  
Name Data Member:  
_Model.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.AI.Models](Projects.AI.Models.md)  
Aggregate Root:  
[Projects.AI.Models](Projects.AI.Models.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Answer](Projects.AI.ModelQAs.md#answer) | string (max) | Desired answer. `Required` `Filter(like)` 
| [CreationTimeUtc](Projects.AI.ModelQAs.md#creationtimeutc) | datetime | The time when the QA was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [DeactivatonTimeUtc](Projects.AI.ModelQAs.md#deactivatontimeutc) | datetime __nullable__ | The time when the QA was deactivated. `Filter(eq;ge;le)` `ReadOnly` 
| [DisplayText](Projects.AI.ModelQAs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.AI.ModelQAs.md#id) | guid |  
| [IsActive](Projects.AI.ModelQAs.md#isactive) | boolean | Indicates whether to include this QA in future builds. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Projects.AI.ModelQAs.md#notes) | string (max) __nullable__ | Notes for this ModelQA. 
| [ObjectVersion](Projects.AI.ModelQAs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [QAType](Projects.AI.ModelQAs.md#qatype) | [QAType](Projects.AI.ModelQAs.md#qatype) | Specifies whether the QA is training or validation. Validation QAs are used to test the correctness of the model and are only reported in the build logs. `Required` `Default("T")` `Filter(eq)` 
| [Question](Projects.AI.ModelQAs.md#question) | string (max) | User question. `Required` `Filter(like)` 
| [Section](Projects.AI.ModelQAs.md#section) | string (128) | Free text organizational section of the QA. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AddedByUser](Projects.AI.ModelQAs.md#addedbyuser) | [Users](Systems.Security.Users.md) | The user which added the QA. `Required` `Filter(multi eq)` `ReadOnly` |
| [Model](Projects.AI.ModelQAs.md#model) | [Models](Projects.AI.Models.md) | The model to which the question belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Answer

Desired answer. `Required` `Filter(like)`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

The time when the QA was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DeactivatonTimeUtc

The time when the QA was deactivated. `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether to include this QA in future builds. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this ModelQA.

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

### QAType

Specifies whether the QA is training or validation. Validation QAs are used to test the correctness of the model and are only reported in the build logs. `Required` `Default("T")` `Filter(eq)`

_Type_: **[QAType](Projects.AI.ModelQAs.md#qatype)**  
_Category_: **System**  
Allowed values for the `QAType`(Projects.AI.ModelQAs.md#qatype) data attribute  
_Allowed Values (Projects.AI.ModelQAsRepository.QAType Enum Members)_  

| Value | Description |
| ---- | --- |
| Training | Training value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Training' |
| Validation | Validation value. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Validation' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Training**  
_Show in UI_: **ShownByDefault**  

### Question

User question. `Required` `Filter(like)`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Section

Free text organizational section of the QA. `Required`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AddedByUser

The user which added the QA. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Model

The model to which the question belongs. `Required` `Filter(multi eq)` `Owner`

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

