---
uid: Communities.Social.FollowedEntities
---
# Communities.Social.FollowedEntities (View)


Optimized view returning social followed entities by users.

## General
Namespace: [Communities.Social](Communities.Social.md)  
Repository: Communities.Social.FollowedEntities  
Introduced In Version: 22.1.6.3  
API access:  ReadWrite  

## Visualization
Display Format: {UserId}: {DataObjectId}  
Search Members:   
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.FollowedEntities](Communities.Social.FollowedEntities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Communities.Social.FollowedEntities.md#creationtimeutc) | datetime | The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Inherited from Cmm_Social_Follows_Table.Creation_Time_Utc` `Introduced in version 22.1.6.73` 
| [EntityItemId](Communities.Social.FollowedEntities.md#entityitemid) | guid | The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Item_Id` 
| [EntityType](Communities.Social.FollowedEntities.md#entitytype) | string (64) | The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Type` 
| [FollowLevel](Communities.Social.FollowedEntities.md#followlevel) | [FollowLevel](Communities.Social.FollowedEntities.md#followlevel) | Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Follow_Level` `Introduced in version 26.2.0.70` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.FollowedEntities.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object being followed by the user. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Data_Object_Id` `Introduced in version 22.1.6.73` |
| [User](Communities.Social.FollowedEntities.md#user) | [Users](Systems.Security.Users.md) | The user which follows the object. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.User_Id` `Introduced in version 22.1.6.73` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Inherited from Cmm_Social_Follows_Table.Creation_Time_Utc` `Introduced in version 22.1.6.73`

Type: **datetime**  
Category: **System**  
Inherited From: **Cmm_Social_Follows_Table.Creation_Time_Utc**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### EntityItemId

The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Item_Id`

Type: **guid**  
Category: **System**  
Inherited From: **Sys_Objects_Table.Entity_Item_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EntityType

The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Entity_Type`

Type: **string (64)**  
Category: **System**  
Inherited From: **Sys_Objects_Table.Entity_Type**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Default Value: ** **  
Show in UI: **ShownByDefault**  

### FollowLevel

Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Follow_Level` `Introduced in version 26.2.0.70`

Type: **[FollowLevel](Communities.Social.FollowedEntities.md#followlevel)**  
Category: **System**  
Allowed values for the `FollowLevel`(Communities.Social.Follows.md#followlevel) data attribute  
Allowed Values (Communities.Social.FollowsRepository.FollowLevel Enum Members)  

| Value | Description |
| ---- | --- |
| Tagged | Automatically followed due to mention or assignment.. Stored as 'TAG'. <br /> Database Value: 'TAG' <br /> Model Value: 0 <br /> Domain API Value: 'Tagged' |
| Follow | User willingly chose to follow this object.. Stored as 'FLW'. <br /> Database Value: 'FLW' <br /> Model Value: 1 <br /> Domain API Value: 'Follow' |
| Favorite | User marked this object as a favorite.. Stored as 'FAV'. <br /> Database Value: 'FAV' <br /> Model Value: 2 <br /> Domain API Value: 'Favorite' |

Inherited From: **Cmm_Social_Follows_Table.Follow_Level**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Tagged**  
Show in UI: **ShownByDefault**  


## Reference Details

### DataObject

The object being followed by the user. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.Data_Object_Id` `Introduced in version 22.1.6.73`

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Category: **System**  
Inherited From: **Cmm_Social_Follows_Table.Data_Object_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user which follows the object. `Required` `Filter(multi eq)` `Inherited from Cmm_Social_Follows_Table.User_Id` `Introduced in version 22.1.6.73`

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Inherited From: **Cmm_Social_Follows_Table.User_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Communities_Social_FollowedEntities

Domain API Entity Type: 
Communities_Social_FollowedEntity

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_FollowedEntities?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_FollowedEntities?$top=10>

