---
uid: Systems.Core.AttributeChangesHistory
---
# Systems.Core.AttributeChangesHistory (View)


Each entry represents an entity attribute change with previous and new value

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.AttributeChangesHistory  
Introduced In Version: 23.1.2.37  
API access:  ReadWrite  

## Visualization
Display Format: {RepositoryName}: {EntityItemId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.AttributeChangesHistory](Systems.Core.AttributeChangesHistory.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AttributeName](Systems.Core.AttributeChangesHistory.md#attributename) | string (64) | The name of the attribute. 
| [EntityItemId](Systems.Core.AttributeChangesHistory.md#entityitemid) | guid | The id of the actual changed object, described by this change. `Required` `Filter(multi eq)` `Inherited from Sys_Object_Changes_Table.Entity_Item_Id` 
| [NewValue](Systems.Core.AttributeChangesHistory.md#newvalue) | string (max) __nullable__ | The new value 
| [PreviousValue](Systems.Core.AttributeChangesHistory.md#previousvalue) | string (max) | The previous value 
| [RepositoryName](Systems.Core.AttributeChangesHistory.md#repositoryname) | string (64) | The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. 
| [TimeUtc](Systems.Core.AttributeChangesHistory.md#timeutc) | datetime | Date and time (in Utc) when the changeset was processed by the server. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Core.AttributeChangesHistory.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user which initiated the change. NULL when it is unknown. |


## Attribute Details

### AttributeName

The name of the attribute.

Type: **string (64)**  
Category: **System**  
Inherited From: **Sys_Attribute_Changes_Table.Attribute_Name**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### EntityItemId

The id of the actual changed object, described by this change. `Required` `Filter(multi eq)` `Inherited from Sys_Object_Changes_Table.Entity_Item_Id`

Type: **guid**  
Category: **System**  
Inherited From: **Sys_Object_Changes_Table.Entity_Item_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### NewValue

The new value

Type: **string (max) __nullable__**  
Category: **System**  
Inherited From: **Sys_Attribute_Changes_Table.New_Value**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PreviousValue

The previous value

Type: **string (max)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RepositoryName

The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object.

Type: **string (64)**  
Category: **System**  
Inherited From: **Sys_Object_Changes_Table.Repository_Name**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### TimeUtc

Date and time (in Utc) when the changeset was processed by the server.

Type: **datetime**  
Category: **System**  
Inherited From: **Sys_Object_Changesets_Table.Time_Utc**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  


## Reference Details

### User

The user which initiated the change. NULL when it is unknown.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Inherited From: **Sys_Object_Changesets_Table.User_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Core_AttributeChangesHistory

Domain API Entity Type: 
Systems_Core_AttributeChangesHistoryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_AttributeChangesHistory?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_AttributeChangesHistory?$top=10>

