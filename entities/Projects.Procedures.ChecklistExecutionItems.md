---
uid: Projects.Procedures.ChecklistExecutionItems
---
# Projects.Procedures.ChecklistExecutionItems


The actual tickable items for a checklist instance (stores progress and immutable snapshots).

## General
Namespace: [Projects.Procedures](Projects.Procedures.md)  
Repository: Projects.Procedures.ChecklistExecutionItems  
Base Table: Op_Checklist_Execution_Items  
Introduced In Version: 26.2.1.0  
API access:  ReadWrite  

## Visualization
Display Format: {OperationalProcedureExecution}  
Search Members: OperationalProcedureExecution  
Name Member: OperationalProcedureExecution  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Procedures.OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md)  
Aggregate Root:  
[Projects.Procedures.OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DoneAtUtc](Projects.Procedures.ChecklistExecutionItems.md#doneatutc) | datetime __nullable__ | When it was completed. `Filter(eq;ge;le)` 
| [IsDone](Projects.Procedures.ChecklistExecutionItems.md#isdone) | boolean | Completion flag. `Required` `Default(false)` `Filter(eq)` 
| [LineNo](Projects.Procedures.ChecklistExecutionItems.md#lineno) | int32 | Item order. `Required` `Filter(eq)` 
| [Notes](Projects.Procedures.ChecklistExecutionItems.md#notes) | string (max) __nullable__ | Optional comment/evidence. `Filter(like)` 
| [TextSnapshot](Projects.Procedures.ChecklistExecutionItems.md#textsnapshot) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Text copied from template at creation. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ChecklistTemplate](Projects.Procedures.ChecklistExecutionItems.md#checklisttemplate) | [ChecklistTemplates](Projects.Procedures.ChecklistTemplates.md) | Source template. `Required` `Filter(multi eq)` |
| [DoneByUser](Projects.Procedures.ChecklistExecutionItems.md#donebyuser) | [Users](Systems.Security.Users.md) (nullable) | Who completed it. `Filter(multi eq)` |
| [OperationalProcedure<br />Execution](Projects.Procedures.ChecklistExecutionItems.md#operationalprocedureexecution) | [OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md) | Parent procedure execution. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Procedures.ChecklistExecutionItems.md#id) | guid |  
| [ObjectVersion](Projects.Procedures.ChecklistExecutionItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Procedures.ChecklistExecutionItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DoneAtUtc

When it was completed. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsDone

Completion flag. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Item order. `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.OperationalProcedureExecution.ChecklistExecutionItems.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.OperationalProcedureExecution.ChecklistExecutionItems.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Optional comment/evidence. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### TextSnapshot

Text copied from template at creation. `Required` `Filter(like)`

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
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

### ChecklistTemplate

Source template. `Required` `Filter(multi eq)`

Type: **[ChecklistTemplates](Projects.Procedures.ChecklistTemplates.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DoneByUser

Who completed it. `Filter(multi eq)`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OperationalProcedureExecution

Parent procedure execution. `Required` `Filter(multi eq)` `Owner`

Type: **[OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md)**  
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

[!list limit=1000 erp.entity=Projects.Procedures.ChecklistExecutionItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Procedures.ChecklistExecutionItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Procedures_ChecklistExecutionItems

Domain API Entity Type: 
Projects_Procedures_ChecklistExecutionItem

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Procedures_ChecklistExecutionItems?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Procedures_ChecklistExecutionItems?$top=10>

