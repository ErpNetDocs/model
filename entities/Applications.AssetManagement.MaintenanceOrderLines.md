---
uid: Applications.AssetManagement.MaintenanceOrderLines
---
# Applications.AssetManagement.MaintenanceOrderLines


Contains the types of maintenance and maintained assets in the maintenance orders.

## General
Namespace: [Applications.AssetManagement](Applications.AssetManagement.md)  
Repository: Applications.AssetManagement.MaintenanceOrderLines  
Base Table: Eam_Maintenance_Order_Lines  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {MaintenanceOrder.DocumentNo} {MaintenanceOrder.DocumentType.TypeName:T}  
Search Members: MaintenanceOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.AssetManagement.MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md)  
Aggregate Root:  
[Applications.AssetManagement.MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineNo](Applications.AssetManagement.MaintenanceOrderLines.md#lineno) | int32 | Consecutive line number, unique within the maintenance order.`Required` 
| [NextServiceDate](Applications.AssetManagement.MaintenanceOrderLines.md#nextservicedate) | date __nullable__ | Specifies, that the maintenance required a specific date for the next maintenance. NULL means that default scheduling should be used.`Filter(ge;le)` 
| [NextServiceTracked<br />ParameterValue](Applications.AssetManagement.MaintenanceOrderLines.md#nextservicetrackedparametervalue) | int32 __nullable__ | Specifies, that the maintenance required the next maintenance to be performed on a specific value of the tracked parameter. NULL means that default scheduling should be used. 
| [Notes](Applications.AssetManagement.MaintenanceOrderLines.md#notes) | string (max) __nullable__ | Notes for this MaintenanceOrderLine. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.AssetManagement.MaintenanceOrderLines.md#document) | [MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md) | The owner document. The <see cref="MaintenanceOrder"/> to which this MaintenanceOrderLine belongs. `Required` `Filter(multi eq)` |
| [MaintenanceOrder](Applications.AssetManagement.MaintenanceOrderLines.md#maintenanceorder) | [MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md) | The <see cref="MaintenanceOrder"/> to which this MaintenanceOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [MaintenanceType](Applications.AssetManagement.MaintenanceOrderLines.md#maintenancetype) | [MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | The type of maintenance performed. |
| [ManagedAsset](Applications.AssetManagement.MaintenanceOrderLines.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The maintained asset. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.MaintenanceOrderLines.md#id) | guid |  
| [ObjectVersion](Applications.AssetManagement.MaintenanceOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.AssetManagement.MaintenanceOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineNo

Consecutive line number, unique within the maintenance order.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.MaintenanceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.MaintenanceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### NextServiceDate

Specifies, that the maintenance required a specific date for the next maintenance. NULL means that default scheduling should be used.`Filter(ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NextServiceTrackedParameterValue

Specifies, that the maintenance required the next maintenance to be performed on a specific value of the tracked parameter. NULL means that default scheduling should be used.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this MaintenanceOrderLine.

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

### Document

The owner document. The <see cref="MaintenanceOrder"/> to which this MaintenanceOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MaintenanceOrder

The <see cref="MaintenanceOrder"/> to which this MaintenanceOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### MaintenanceType

The type of maintenance performed.

Type: **[MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

The maintained asset.

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
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

[!list limit=1000 erp.entity=Applications.AssetManagement.MaintenanceOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.MaintenanceOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_MaintenanceOrderLines

Domain API Entity Type: 
Applications_AssetManagement_MaintenanceOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_MaintenanceOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_MaintenanceOrderLines?$top=10>

