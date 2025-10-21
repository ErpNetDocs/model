---
uid: Communities.Social.FollowedEntities
---
# Communities.Social.FollowedEntities View

**Namespace:** [Communities.Social](Communities.Social.md)  

Optimized view returning social followed entities by users. Entity: Cmm_Social_Followed_Entities (Introduced in version 22.1.6.3)

## Default Visualization
Default Display Text Format:  
_{UserId}: {DataObjectId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.FollowedEntities](Communities.Social.FollowedEntities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EntityItemId](Communities.Social.FollowedEntities.md#entityitemid) | guid | The followed entity item. `Required` `Filter(multi eq)` 
| [EntityType](Communities.Social.FollowedEntities.md#entitytype) | string (64) | The followed entity type. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.FollowedEntities.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The data object subject to the social follow. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` `Introduced in version 22.1.6.8` |
| [User](Communities.Social.FollowedEntities.md#user) | [Users](Systems.Security.Users.md) | The user which follows the entity. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sec_Users_Table.User_Id` |


## Attribute Details

### EntityItemId

The followed entity item. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EntityType

The followed entity type. `Required` `Filter(multi eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataObject

The data object subject to the social follow. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` `Introduced in version 22.1.6.8`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### User

The user which follows the entity. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sec_Users_Table.User_Id`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.User_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Communities_Social_FollowedEntities

Domain API Entity Type: 
Communities_Social_FollowedEntity

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_FollowedEntities?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_FollowedEntities?$top=10>

