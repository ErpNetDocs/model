---
uid: Production.Resources.WorkgroupResources
---
# Production.Resources.WorkgroupResources


Describes the availability of resources in the active workgroups

## General
Namespace: [Production.Resources](Production.Resources.md)  
Repository: Production.Resources.WorkgroupResources  
Base Table: Prd_Workgroup_Resources  
API access:  ReadWrite  

## Visualization
Display Format: {Workgroup.Name}  
Search Members: Workgroup.Name  
Name Member: Workgroup.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  
Aggregate Root:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Production.Resources.WorkgroupResources.md#active) | boolean | Indicates whether the current workgroup resource is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 22.1.5.26] 
| [AvailableQuantity](Production.Resources.WorkgroupResources.md#availablequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity available of the resource in this workgroup. The measurement unit is specified in Prd_Resources[Unit: Resource.PrimaryUnit] [Required] [Default(0)] 
| [Notes](Production.Resources.WorkgroupResources.md#notes) | string (254) __nullable__ | User notes for the workgroup resource 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Resource](Production.Resources.WorkgroupResources.md#resource) | [Resources](Production.Resources.Resources.md) | The contained resource type |
| [Workgroup](Production.Resources.WorkgroupResources.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) | Id of the workgroup, containing the resource |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.WorkgroupResources.md#id) | guid |  
| [ObjectVersion](Production.Resources.WorkgroupResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Resources.WorkgroupResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Capacity | [Capacity](Production.Resources.Capacity.md) | List of `Capacity`(Production.Resources.Capacity.md) child objects, based on the `Production.Resources.Capacity.WorkgroupResource`(Production.Resources.Capacity.md#workgroupresource) back reference 


## Attribute Details

### Active

Indicates whether the current workgroup resource is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 22.1.5.26]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AvailableQuantity

Quantity available of the resource in this workgroup. The measurement unit is specified in Prd_Resources[Unit: Resource.PrimaryUnit] [Required] [Default(0)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Notes

User notes for the workgroup resource

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### Resource

The contained resource type

Type: **[Resources](Production.Resources.Resources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Workgroup

Id of the workgroup, containing the resource

Type: **[Workgroups](Production.Resources.Workgroups.md)**  
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

[!list limit=1000 erp.entity=Production.Resources.WorkgroupResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Resources.WorkgroupResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Resources_WorkgroupResources

Domain API Entity Type: 
Production_Resources_WorkgroupResource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Resources_WorkgroupResources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Resources_WorkgroupResources?$top=10>

