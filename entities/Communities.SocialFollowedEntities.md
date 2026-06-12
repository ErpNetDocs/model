---
uid: Communities.SocialFollowedEntities
---
# Communities.SocialFollowedEntities View

**Namespace:** [Communities](Communities.md)  

Optimized view returning social followed entities by users. Entity: Cmm_Social_Followed_Entities_Indexed_View (Introduced in version 22.1.6.3)

## Default Visualization
Default Display Text Format:  
_{UserId}: {DataObjectId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.SocialFollowedEntities](Communities.SocialFollowedEntities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EntityItemId](Communities.SocialFollowedEntities.md#entityitemid) | guid | The followed entity item. `Required` `Filter(multi eq)` 
| [EntityType](Communities.SocialFollowedEntities.md#entitytype) | string (64) | The followed entity type. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.SocialFollowedEntities.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The data object subject to the social follow. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` `Introduced in version 22.1.6.8` |
| [User](Communities.SocialFollowedEntities.md#user) | [Users](Systems.Security.Users.md) | The user which follows the entity. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sec_Users_Table.User_Id` |


## Attribute Details

### EntityItemId

The followed entity item. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### EntityType

The followed entity type. `Required` `Filter(multi eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  


## Reference Details

### DataObject

The data object subject to the social follow. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` `Introduced in version 22.1.6.8`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### User

The user which follows the entity. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sec_Users_Table.User_Id`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.User_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Communities_SocialFollowedEntities?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Communities_SocialFollowedEntities?$top=10>

