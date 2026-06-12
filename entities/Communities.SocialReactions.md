---
uid: Communities.SocialReactions
---
# Communities.SocialReactions Entity

**Namespace:** [Communities](Communities.md)  

Reaction of a user to any social comment to an object of the system. Entity: Cmm_Social_Reactions (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{Id}: {DataObjectId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.SocialReactions](Communities.SocialReactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Communities.SocialReactions.md#creationtimeutc) | datetime | The exact server time (in UTC), when the reaction was created. `Required` `Default(NowUtc)` 
| [DisplayText](Communities.SocialReactions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Communities.SocialReactions.md#id) | guid |  
| [ObjectVersion](Communities.SocialReactions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ReactionType](Communities.SocialReactions.md#reactiontype) | [ReactionType](Communities.SocialReactions.md#reactiontype) | The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.SocialReactions.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The root data object (post, marketplace product, document, etc), for which the reaction is. `Required` `Filter(multi eq)` |
| [SocialComment](Communities.SocialReactions.md#socialcomment) | [SocialComments](Communities.SocialComments.md) (nullable) | When not null, specifies that the reaction is for the specified comment within the data object. `Filter(multi eq)` |
| [User](Communities.SocialReactions.md#user) | [Users](Systems.Security.Users.md) | The user, who reacted. `Required` `Filter(multi eq)` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the reaction was created. `Required` `Default(NowUtc)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ReactionType

The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` `Filter(multi eq)`

_Type_: **[ReactionType](Communities.SocialReactions.md#reactiontype)**  
_Category_: **System**  
Allowed values for the `ReactionType`(Communities.SocialReactions.md#reactiontype) data attribute  
_Allowed Values (Communities.SocialReactionsRepository.ReactionType Enum Members)_  

| Value | Description |
| ---- | --- |
| Like | Compare by mask. Use * (asterisk) as wildcard char.. Stored as 'LIK'. <br /> _Database Value:_ 'LIK' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Like' |
| Love | Love value. Stored as 'LOV'. <br /> _Database Value:_ 'LOV' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Love' |
| Haha | Haha value. Stored as 'HAH'. <br /> _Database Value:_ 'HAH' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Haha' |
| Wow | Wow value. Stored as 'WOW'. <br /> _Database Value:_ 'WOW' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Wow' |
| Sad | Sad value. Stored as 'SAD'. <br /> _Database Value:_ 'SAD' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Sad' |
| Angry | Angry value. Stored as 'ANG'. <br /> _Database Value:_ 'ANG' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Angry' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  


## Reference Details

### DataObject

The root data object (post, marketplace product, document, etc), for which the reaction is. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### SocialComment

When not null, specifies that the reaction is for the specified comment within the data object. `Filter(multi eq)`

_Type_: **[SocialComments](Communities.SocialComments.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### User

The user, who reacted. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  



## Business Rules

[!list limit=1000 erp.entity=Communities.SocialReactions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.SocialReactions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Communities_SocialReactions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Communities_SocialReactions?$top=10>

