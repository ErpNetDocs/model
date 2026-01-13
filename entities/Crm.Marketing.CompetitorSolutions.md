---
uid: Crm.Marketing.CompetitorSolutions
---
# Crm.Marketing.CompetitorSolutions Entity

**Namespace:** [Crm.Marketing](Crm.Marketing.md)  

The solutions offered by a competitor. Entity: Crm_Competitor_Solutions (Introduced in version 22.1.4.70)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Marketing.Competitors](Crm.Marketing.Competitors.md)  
Aggregate Root:  
[Crm.Marketing.Competitors](Crm.Marketing.Competitors.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Crm.Marketing.CompetitorSolutions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Marketing.CompetitorSolutions.md#id) | guid |  
| [Name](Crm.Marketing.CompetitorSolutions.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of solution. `Required` `Filter(like)` 
| [Notes](Crm.Marketing.CompetitorSolutions.md#notes) | string (max) __nullable__ | Notes for this CompetitorSolution. 
| [ObjectVersion](Crm.Marketing.CompetitorSolutions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanySizeClass](Crm.Marketing.CompetitorSolutions.md#companysizeclass) | [CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable) | When not null, specifies the company size, for which the solution is targeted. `Filter(multi eq)` |
| [Competitor](Crm.Marketing.CompetitorSolutions.md#competitor) | [Competitors](Crm.Marketing.Competitors.md) | Competitor to our marketing solutions. `Required` `Filter(multi eq)` `Owner` |
| [Industry](Crm.Marketing.CompetitorSolutions.md#industry) | [Industries](Crm.Marketing.Industries.md) (nullable) | When not null, specifies the industry, for which the solution is targeted. `Filter(multi eq)` |
| [OurMarketingSolution](Crm.Marketing.CompetitorSolutions.md#ourmarketingsolution) | [MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable) | Our marketing solution, which is competing with the competitor solution. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

Name of solution. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this CompetitorSolution.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### CompanySizeClass

When not null, specifies the company size, for which the solution is targeted. `Filter(multi eq)`

_Type_: **[CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Competitor

Competitor to our marketing solutions. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Competitors](Crm.Marketing.Competitors.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Industry

When not null, specifies the industry, for which the solution is targeted. `Filter(multi eq)`

_Type_: **[Industries](Crm.Marketing.Industries.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OurMarketingSolution

Our marketing solution, which is competing with the competitor solution. `Filter(multi eq)`

_Type_: **[MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
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


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.CompetitorSolutions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.CompetitorSolutions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Marketing_CompetitorSolutions

Domain API Entity Type: 
Crm_Marketing_CompetitorSolution

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Marketing_CompetitorSolutions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Marketing_CompetitorSolutions?$top=10>

