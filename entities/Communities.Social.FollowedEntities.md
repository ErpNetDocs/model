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
| [CreationTimeUtc](Communities.Social.FollowedEntities.md#creationtimeutc) | datetime | The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Inherited from Cmm_Social_Follows_Table.Creation_Time_Utc` `Introduced in version 22.1.6.73` 
| [EntityItemId](Communities.Social.FollowedEntities.md#entityitemid) | guid | The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Item_Id` 
| [EntityType](Communities.Social.FollowedEntities.md#entitytype) | string (64) | The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)` `Inherited from Sys_Objects_Table.Entity_Type` 
| [FollowLevel](Communities.Social.FollowedEntities.md#followlevel) | [FollowLevel](Communities.Social.FollowedEntities.md#followlevel) | Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Inherited from Cmm_Social_Follows_Table.Follow_Level` `Introduced in version 26.2.0.70` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.FollowedEntities.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object being followed by the user. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Data_Object_Id` `Introduced in version 22.1.6.73` |
| [User](Communities.Social.FollowedEntities.md#user) | [Users](Systems.Security.Users.md) | The user which follows the object. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.User_Id` `Introduced in version 22.1.6.73` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Inherited from Cmm_Social_Follows_Table.Creation_Time_Utc` `Introduced in version 22.1.6.73`

_Type_: **datetime**  
_Category_: **System**  
_Inherited From_: **Cmm_Social_Follows_Table.Creation_Time_Utc**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### EntityItemId

The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Item_Id`

_Type_: **guid**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Entity_Item_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EntityType

The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)` `Inherited from Sys_Objects_Table.Entity_Type`

_Type_: **string (64)**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Entity_Type**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: ** **  
_Show in UI_: **ShownByDefault**  

### FollowLevel

Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Inherited from Cmm_Social_Follows_Table.Follow_Level` `Introduced in version 26.2.0.70`

_Type_: **[FollowLevel](Communities.Social.FollowedEntities.md#followlevel)**  
_Category_: **System**  
Allowed values for the `FollowLevel`(Communities.Social.FollowedEntities.md#followlevel) data attribute  
_Allowed Values (Communities.Social.FollowedEntitiesRepository.FollowLevel Enum Members)_  

| Value | Description |
| ---- | --- |
| Tagged | Tagged value. Stored as 'TAG'. <br /> _Database Value:_ 'TAG' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Tagged' |
| Follow | Follow value. Stored as 'FLW'. <br /> _Database Value:_ 'FLW' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Follow' |
| Favorite | Favorite value. Stored as 'FAV'. <br /> _Database Value:_ 'FAV' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Favorite' |

_Inherited From_: **Cmm_Social_Follows_Table.Follow_Level**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Tagged**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataObject

The object being followed by the user. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Data_Object_Id` `Introduced in version 22.1.6.73`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Category_: **System**  
_Inherited From_: **Cmm_Social_Follows_Table.Data_Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user which follows the object. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.User_Id` `Introduced in version 22.1.6.73`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Inherited From_: **Cmm_Social_Follows_Table.User_Id**  
_Supported Filters_: **Equals, EqualsIn**  
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

