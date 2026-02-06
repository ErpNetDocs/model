---
uid: Logistics.Wms.WarehouseWorkers
---
# Logistics.Wms.WarehouseWorkers


Human or robot worker, which can execute warehouse tasks.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseWorkers  
Base Table: Wms_Warehouse_Workers  
Introduced In Version: 22.1.6.31  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
Aggregate Root:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActiveFrom](Logistics.Wms.WarehouseWorkers.md#activefrom) | date | The date, from which the worker record has become active in the warehouse.[Required] [Default(Today)] [Filter(eq;ge;le)] 
| [ActiveTo](Logistics.Wms.WarehouseWorkers.md#activeto) | date __nullable__ | The date of termination of the activity of the worker in the warehouse. Can be NULL for workers, which are still active and do not have previous terminations.[Filter(eq;ge;le)] 
| [IsActive](Logistics.Wms.WarehouseWorkers.md#isactive) | boolean | Specifies whether the worker is active and can execute new warehouse tasks.[Required] [Default(true)] [Filter(eq)] 
| [Name](Logistics.Wms.WarehouseWorkers.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the worker (multi-language).[Required] [Filter(multi eq;like)] 
| [Notes](Logistics.Wms.WarehouseWorkers.md#notes) | string (max) __nullable__ | Notes for this WarehouseWorker. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Person](Logistics.Wms.WarehouseWorkers.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The definition of the person, when the worker is human worker. NULL means that the person is unknown or the worker is non-person. |
| [User](Logistics.Wms.WarehouseWorkers.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user who is going to work in the selected warehouse |
| [Warehouse](Logistics.Wms.WarehouseWorkers.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse, where the worker works. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseWorkers.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseWorkers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehouseWorkers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActiveFrom

The date, from which the worker record has become active in the warehouse.[Required] [Default(Today)] [Filter(eq;ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### ActiveTo

The date of termination of the activity of the worker in the warehouse. Can be NULL for workers, which are still active and do not have previous terminations.[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the worker is active and can execute new warehouse tasks.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the worker (multi-language).[Required] [Filter(multi eq;like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WarehouseWorker.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### Person

The definition of the person, when the worker is human worker. NULL means that the person is unknown or the worker is non-person.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user who is going to work in the selected warehouse

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

The warehouse, where the worker works.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseWorkers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseWorkers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseWorkers

Domain API Entity Type: 
Logistics_Wms_WarehouseWorker

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseWorkers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseWorkers?$top=10>

