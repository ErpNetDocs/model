---
uid: Systems.Internal.AttributeChangesHistory
---
# Systems.Internal.AttributeChangesHistory View

**Namespace:** [Systems.Internal](Systems.Internal.md)  

Each entry represents an entity attribute change with previous and new value. Entity: Sys_Attribute_Changes_History_View (Introduced in version 23.1.2.37)

## Renames

Old name: **Systems.Core.AttributeChangesHistory**  
New name: **Systems.Internal.AttributeChangesHistory**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{RepositoryName}: {EntityItemId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Internal.AttributeChangesHistory](Systems.Internal.AttributeChangesHistory.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AttributeName](Systems.Internal.AttributeChangesHistory.md#attributename) | string (64) | The name of the attribute. `Required` `Filter(eq)` `Inherited from Sys_Attribute_<br />Changes_Table.Attribute_Name` 
| [EntityItemId](Systems.Internal.AttributeChangesHistory.md#entityitemid) | guid | The id of the actual changed object, described by this change. `Required` `Filter(multi eq)` `Inherited from Sys_Object_Changes_Table.Entity_Item_Id` 
| [NewValue](Systems.Internal.AttributeChangesHistory.md#newvalue) | string (max) __nullable__ | The new value. `Filter(eq;like)` `Inherited from Sys_Attribute_<br />Changes_Table.New_Value` 
| [PreviousValue](Systems.Internal.AttributeChangesHistory.md#previousvalue) | string (max) | The previous value. `Required` `Filter(eq)` 
| [RepositoryName](Systems.Internal.AttributeChangesHistory.md#repositoryname) | string (64) | The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq;like)` `Inherited from Sys_Object_Changes_Table.Repository_Name` 
| [TimeUtc](Systems.Internal.AttributeChangesHistory.md#timeutc) | datetime | Date and time (in Utc) when the changeset was processed by the server. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `Inherited from Sys_Object_Changesets_<br />Table.Time_Utc` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Internal.AttributeChangesHistory.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user which initiated the change. null when it is unknown. `Filter(multi eq)` `Inherited from Sys_Object_Changesets_<br />Table.User_Id` |


## Attribute Details

### AttributeName

The name of the attribute. `Required` `Filter(eq)` `Inherited from Sys_Attribute_Changes_Table.Attribute_Name`

_Type_: **string (64)**  
_Category_: **System**  
_Inherited From_: **Sys_Attribute_Changes_Table.Attribute_Name**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### EntityItemId

The id of the actual changed object, described by this change. `Required` `Filter(multi eq)` `Inherited from Sys_Object_Changes_Table.Entity_Item_Id`

_Type_: **guid**  
_Category_: **System**  
_Inherited From_: **Sys_Object_Changes_Table.Entity_Item_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### NewValue

The new value. `Filter(eq;like)` `Inherited from Sys_Attribute_Changes_Table.New_Value`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Inherited From_: **Sys_Attribute_Changes_Table.New_Value**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### PreviousValue

The previous value. `Required` `Filter(eq)`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### RepositoryName

The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq;like)` `Inherited from Sys_Object_Changes_Table.Repository_Name`

_Type_: **string (64)**  
_Category_: **System**  
_Inherited From_: **Sys_Object_Changes_Table.Repository_Name**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### TimeUtc

Date and time (in Utc) when the changeset was processed by the server. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `Inherited from Sys_Object_Changesets_Table.Time_Utc`

_Type_: **datetime**  
_Category_: **System**  
_Inherited From_: **Sys_Object_Changesets_Table.Time_Utc**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### User

The user which initiated the change. null when it is unknown. `Filter(multi eq)` `Inherited from Sys_Object_Changesets_Table.User_Id`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Sys_Object_Changesets_Table.User_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Internal_AttributeChangesHistory?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Internal_AttributeChangesHistory?$top=10>

