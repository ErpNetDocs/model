---
uid: Communities.Social.ReactionsSummary
---
# Communities.Social.ReactionsSummary View

**Namespace:** [Communities.Social](Communities.Social.md)  

Summary with the social reactions per comment and dataobject. Entity: Cmm_Social_Reactions_Summary (Introduced in version 22.1.6.73)

## Default Visualization
Default Display Text Format:  
_{DataObjectId}: {SocialCommentId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.ReactionsSummary](Communities.Social.ReactionsSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cnt](Communities.Social.ReactionsSummary.md#cnt) | int64 | Count of social reactions. `Required` 
| [ReactionType](Communities.Social.ReactionsSummary.md#reactiontype) | [ReactionType](Communities.Social.ReactionsSummary.md#reactiontype) | The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.ReactionsSummary.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The extensible data object. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` |
| [SocialComment](Communities.Social.ReactionsSummary.md#socialcomment) | [Comments](Communities.Social.Comments.md) | The social comment. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cmm_Social_Comments_Table.Social_Comment_Id` |


## Attribute Details

### Cnt

Count of social reactions. `Required`

_Type_: **int64**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ReactionType

The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required`

_Type_: **[ReactionType](Communities.Social.ReactionsSummary.md#reactiontype)**  
_Category_: **System**  
Allowed values for the `ReactionType`(Communities.Social.ReactionsSummary.md#reactiontype) data attribute  
_Allowed Values (Communities.Social.ReactionsSummaryRepository.ReactionType Enum Members)_  

| Value | Description |
| ---- | --- |
| Like | Like value. Stored as 'LIK'. <br /> _Database Value:_ 'LIK' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Like' |
| Love | Love value. Stored as 'LOV'. <br /> _Database Value:_ 'LOV' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Love' |
| Haha | Haha value. Stored as 'HAH'. <br /> _Database Value:_ 'HAH' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Haha' |
| Wow | Wow value. Stored as 'WOW'. <br /> _Database Value:_ 'WOW' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Wow' |
| Sad | Sad value. Stored as 'SAD'. <br /> _Database Value:_ 'SAD' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Sad' |
| Angry | Angry value. Stored as 'ANG'. <br /> _Database Value:_ 'ANG' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Angry' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataObject

The extensible data object. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### SocialComment

The social comment. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cmm_Social_Comments_Table.Social_Comment_Id`

_Type_: **[Comments](Communities.Social.Comments.md)**  
_Category_: **System**  
_Inherited From_: **Cmm_Social_Comments_Table.Social_Comment_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Communities_Social_ReactionsSummary

Domain API Entity Type: 
Communities_Social_ReactionsSummary

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_ReactionsSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_ReactionsSummary?$top=10>

