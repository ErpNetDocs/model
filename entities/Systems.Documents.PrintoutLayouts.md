---
uid: Systems.Documents.PrintoutLayouts
---
# Systems.Documents.PrintoutLayouts


Contains design layouts for document printouts.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.PrintoutLayouts  
Base Table: Gen_Printout_Layouts  
API access:  ReadWrite  

## Renames

Old name: General.PrintoutLayouts  
New name: Systems.Documents.PrintoutLayouts  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  4 - Track object attribute and blob changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Documents.PrintoutLayouts](Systems.Documents.PrintoutLayouts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BinaryLayout](Systems.Documents.PrintoutLayouts.md#binarylayout) | byte[] __nullable__ | The printout layout, when the format requires binary storage. Alternative to Layout 
| [DocumentEntityName](Systems.Documents.PrintoutLayouts.md#documententityname) | string (64) | The entity name of the document type e.g. Crm_Sales_Orders, Inv_Store_Orders etc.`Required` `Filter(eq)` 
| [Layout](Systems.Documents.PrintoutLayouts.md#layout) | string (max) __nullable__ | The textual representation of the printout layout, when the format requires text representation. Alternative to Binary_Layout 
| [LayoutFormat](Systems.Documents.PrintoutLayouts.md#layoutformat) | string (32) | Format specifier of the layout. Recognized by the application`Required` `Filter(multi eq)` 
| [Name](Systems.Documents.PrintoutLayouts.md#name) | string (64) | The name of this PrintoutLayout. `Required` `Filter(eq;like)` `ORD` 
| [Notes](Systems.Documents.PrintoutLayouts.md#notes) | string (254) __nullable__ | Notes for this PrintoutLayout. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataSource](Systems.Documents.PrintoutLayouts.md#datasource) | [DataSources](Systems.Documents.DataSources.md) (nullable) | The data source for the printout |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.PrintoutLayouts.md#id) | guid |  
| [ObjectVersion](Systems.Documents.PrintoutLayouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Documents.PrintoutLayouts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Documents.PrintoutLayouts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Documents.PrintoutLayouts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Documents.PrintoutLayouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BinaryLayout

The printout layout, when the format requires binary storage. Alternative to Layout

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### DocumentEntityName

The entity name of the document type e.g. Crm_Sales_Orders, Inv_Store_Orders etc.`Required` `Filter(eq)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Layout

The textual representation of the printout layout, when the format requires text representation. Alternative to Binary_Layout

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### LayoutFormat

Format specifier of the layout. Recognized by the application`Required` `Filter(multi eq)`

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **CannotBeShown**  

### Name

The name of this PrintoutLayout. `Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( Not( IsNullOrEmpty( obj.DocumentEntityName)), obj.GetDefaultName( ), null)`
### Notes

Notes for this PrintoutLayout.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

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

### DataSource

The data source for the printout

Type: **[DataSources](Systems.Documents.DataSources.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Documents.PrintoutLayouts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.PrintoutLayouts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_PrintoutLayouts

Domain API Entity Type: 
Systems_Documents_PrintoutLayout

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_PrintoutLayouts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_PrintoutLayouts?$top=10>

