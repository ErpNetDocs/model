---
uid: Communities.SocialReactionsSummary
---
# Communities.SocialReactionsSummary View

**Namespace:** [Communities](Communities.md)  

Summary with the social reactions per comment and dataobject. Entity: Cmm_Social_Reactions_Summary_Indexed_View

## Default Visualization
Default Display Text Format:  
_{DataObjectId}: {SocialCommentId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.SocialReactionsSummary](Communities.SocialReactionsSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cnt](Communities.SocialReactionsSummary.md#cnt) | int64 |  
| [ReactionType](Communities.SocialReactionsSummary.md#reactiontype) | [ReactionType](Communities.SocialReactionsSummary.md#reactiontype) | The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.SocialReactionsSummary.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | . `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id` |
| [SocialComment](Communities.SocialReactionsSummary.md#socialcomment) | [SocialComments](Communities.SocialComments.md) |  |


## Attribute Details

### Cnt

_Type_: **int64**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ReactionType

The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required`

_Type_: **[ReactionType](Communities.SocialReactionsSummary.md#reactiontype)**  
_Category_: **System**  
Allowed values for the `ReactionType`(Communities.SocialReactionsSummary.md#reactiontype) data attribute  
_Allowed Values (Communities.SocialReactionsSummaryRepository.ReactionType Enum Members)_  

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


## Reference Details

### DataObject

. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Sys_Objects_Table.Object_Id`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Inherited From_: **Sys_Objects_Table.Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### SocialComment

_Type_: **[SocialComments](Communities.SocialComments.md)**  
_Category_: **System**  
_Inherited From_: **Cmm_Social_Comments_Table.Social_Comment_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Communities_SocialReactionsSummary?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Communities_SocialReactionsSummary?$top=10>

