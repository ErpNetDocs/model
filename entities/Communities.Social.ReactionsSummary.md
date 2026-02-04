---
uid: Communities.Social.ReactionsSummary
---
# Communities.Social.ReactionsSummary (View)


Summary with the social reactions per comment and dataobject

## General
Namespace: [Communities.Social](Communities.Social.md)  
Repository: Communities.Social.ReactionsSummary  
Introduced In Version: 22.1.6.73  
API access:  ReadWrite  

## Visualization
Display Format: {DataObjectId}: {SocialCommentId}  
Search Members:   
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.ReactionsSummary](Communities.Social.ReactionsSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cnt](Communities.Social.ReactionsSummary.md#cnt) | int64 | Count of social reactions. 
| [ReactionType](Communities.Social.ReactionsSummary.md#reactiontype) | [ReactionType](Communities.Social.ReactionsSummary.md#reactiontype) | The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.ReactionsSummary.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The extensible data object. |
| [SocialComment](Communities.Social.ReactionsSummary.md#socialcomment) | [Comments](Communities.Social.Comments.md) | The social comment. |


## Attribute Details

### Cnt

Count of social reactions.

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReactionType

The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry.

Type: **[ReactionType](Communities.Social.ReactionsSummary.md#reactiontype)**  
Category: **System**  
Allowed values for the `ReactionType`(Communities.Social.ReactionsSummary.md#reactiontype) data attribute  
Allowed Values (Communities.Social.ReactionsSummaryRepository.ReactionType Enum Members)  

| Value | Description |
| ---- | --- |
| Like | Like value. Stored as 'LIK'. <br /> Database Value: 'LIK' <br /> Model Value: 0 <br /> Domain API Value: 'Like' |
| Love | Love value. Stored as 'LOV'. <br /> Database Value: 'LOV' <br /> Model Value: 1 <br /> Domain API Value: 'Love' |
| Haha | Haha value. Stored as 'HAH'. <br /> Database Value: 'HAH' <br /> Model Value: 2 <br /> Domain API Value: 'Haha' |
| Wow | Wow value. Stored as 'WOW'. <br /> Database Value: 'WOW' <br /> Model Value: 3 <br /> Domain API Value: 'Wow' |
| Sad | Sad value. Stored as 'SAD'. <br /> Database Value: 'SAD' <br /> Model Value: 4 <br /> Domain API Value: 'Sad' |
| Angry | Angry value. Stored as 'ANG'. <br /> Database Value: 'ANG' <br /> Model Value: 5 <br /> Domain API Value: 'Angry' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### DataObject

The extensible data object.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Category: **System**  
Inherited From: **Sys_Objects_Table.Object_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### SocialComment

The social comment.

Type: **[Comments](Communities.Social.Comments.md)**  
Category: **System**  
Inherited From: **Cmm_Social_Comments_Table.Social_Comment_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Communities_Social_ReactionsSummary

Domain API Entity Type: 
Communities_Social_ReactionsSummary

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_ReactionsSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_ReactionsSummary?$top=10>

