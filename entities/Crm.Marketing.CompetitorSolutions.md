---
uid: Crm.Marketing.CompetitorSolutions
---
# Crm.Marketing.CompetitorSolutions


The solutions offered by a competitor.

## General
Namespace: [Crm.Marketing](Crm.Marketing.md)  
Repository: Crm.Marketing.CompetitorSolutions  
Base Table: Crm_Competitor_Solutions  
Introduced In Version: 22.1.4.70  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Marketing.Competitors](Crm.Marketing.Competitors.md)  
Aggregate Root:  
[Crm.Marketing.Competitors](Crm.Marketing.Competitors.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Name](Crm.Marketing.CompetitorSolutions.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of solution. `Required` `Filter(like)` 
| [Notes](Crm.Marketing.CompetitorSolutions.md#notes) | string (max) __nullable__ | Notes for this CompetitorSolution. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanySizeClass](Crm.Marketing.CompetitorSolutions.md#companysizeclass) | [CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable) | When not null, specifies the company size, for which the solution is targeted. `Filter(multi eq)` |
| [Competitor](Crm.Marketing.CompetitorSolutions.md#competitor) | [Competitors](Crm.Marketing.Competitors.md) | Competitor to our marketing solutions. `Required` `Filter(multi eq)` `Owner` |
| [Industry](Crm.Marketing.CompetitorSolutions.md#industry) | [Industries](Crm.Marketing.Industries.md) (nullable) | When not null, specifies the industry, for which the solution is targeted. `Filter(multi eq)` |
| [OurMarketingSolution](Crm.Marketing.CompetitorSolutions.md#ourmarketingsolution) | [MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable) | Our marketing solution, which is competing with the competitor solution. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Marketing.CompetitorSolutions.md#id) | guid |  
| [ObjectVersion](Crm.Marketing.CompetitorSolutions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Marketing.CompetitorSolutions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Name

Name of solution. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this CompetitorSolution.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### CompanySizeClass

When not null, specifies the company size, for which the solution is targeted. `Filter(multi eq)`

Type: **[CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Competitor

Competitor to our marketing solutions. `Required` `Filter(multi eq)` `Owner`

Type: **[Competitors](Crm.Marketing.Competitors.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Industry

When not null, specifies the industry, for which the solution is targeted. `Filter(multi eq)`

Type: **[Industries](Crm.Marketing.Industries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OurMarketingSolution

Our marketing solution, which is competing with the competitor solution. `Filter(multi eq)`

Type: **[MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


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

