---
uid: Production.Resources.WorkgroupResources
---
# Production.Resources.WorkgroupResources Entity

**Namespace:** [Production.Resources](Production.Resources.md)  

Describes the availability of resources in the active workgroups. Entity: Prd_Workgroup_Resources

## Default Visualization
Default Display Text Format:  
_{Workgroup.Name}_  
Default Search Members:  
_Workgroup.Name_  
Name Data Member:  
_Workgroup.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  
Aggregate Root:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Production.Resources.WorkgroupResources.md#active) | boolean | Indicates whether the current workgroup resource is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26` 
| [AvailableQuantity](Production.Resources.WorkgroupResources.md#availablequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity available of the resource in this workgroup. The measurement unit is specified in Prd_Resources. `Unit: Resource.PrimaryUnit` `Required` `Default(0)` 
| [DisplayText](Production.Resources.WorkgroupResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.Resources.WorkgroupResources.md#id) | guid |  
| [Notes](Production.Resources.WorkgroupResources.md#notes) | string (254) __nullable__ | User notes for the workgroup resource. 
| [ObjectVersion](Production.Resources.WorkgroupResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Resource](Production.Resources.WorkgroupResources.md#resource) | [Resources](Production.Resources.Resources.md) | The contained resource type. `Required` `Filter(multi eq)` |
| [Workgroup](Production.Resources.WorkgroupResources.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) | Id of the workgroup, containing the resource. `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Capacity | [Capacity](Production.Resources.Capacity.md) | List of `Capacity`(Production.Resources.Capacity.md) child objects, based on the `Production.Resources.Capacity.WorkgroupResource`(Production.Resources.Capacity.md#workgroupresource) back reference 


## Attribute Details

### Active

Indicates whether the current workgroup resource is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AvailableQuantity

Quantity available of the resource in this workgroup. The measurement unit is specified in Prd_Resources. `Unit: Resource.PrimaryUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
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

### Notes

User notes for the workgroup resource.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Resource

The contained resource type. `Required` `Filter(multi eq)`

_Type_: **[Resources](Production.Resources.Resources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Workgroup

Id of the workgroup, containing the resource. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Workgroups](Production.Resources.Workgroups.md)**  
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

