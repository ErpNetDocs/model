---
uid: Crm.Marketing.Competitors
---
# Crm.Marketing.Competitors


Competitors to our marketing solutions.

## General
Namespace: [Crm.Marketing](Crm.Marketing.md)  
Repository: Crm.Marketing.Competitors  
Base Table: Crm_Competitors  
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

Aggregate Tree  
* [Crm.Marketing.Competitors](Crm.Marketing.Competitors.md)  
  * [Crm.Marketing.CompetitorSolutions](Crm.Marketing.CompetitorSolutions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](Crm.Marketing.Competitors.md#fromdate) | datetime __nullable__ | Start date when this company became a competitor.[Default(Today)] [Filter(ge;le)] [Introduced in version 25.1.0.62] 
| [IsActive](Crm.Marketing.Competitors.md#isactive) | boolean | Indicates whether the current Competitor is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.0.18] 
| [Name](Crm.Marketing.Competitors.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this Competitor. `Required` `Filter(like)` 
| [Notes](Crm.Marketing.Competitors.md#notes) | string (max) __nullable__ | Notes for this Competitor. 
| [ToDate](Crm.Marketing.Competitors.md#todate) | datetime __nullable__ | Date until which this company was considered a competitor. The field is blank if the company is still a competitor.[Filter(ge;le)] [Introduced in version 25.1.0.62] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Marketing.Competitors.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Our enterprise company, for which we are defining the competitor. NULL means that the competitor is defined for all the companies in the ERP instance. |
| [Party](Crm.Marketing.Competitors.md#party) | [Parties](General.Contacts.Parties.md) (nullable) | When not null, specifies the party of the competitor. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Marketing.Competitors.md#id) | guid |  
| [ObjectVersion](Crm.Marketing.Competitors.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Marketing.Competitors.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Marketing.Competitors.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Marketing.Competitors.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Marketing.Competitors.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Solutions | [CompetitorSolutions](Crm.Marketing.CompetitorSolutions.md) | List of `CompetitorSolution`(Crm.Marketing.CompetitorSolutions.md) child objects, based on the `Crm.Marketing.CompetitorSolution.Competitor`(Crm.Marketing.CompetitorSolutions.md#competitor) back reference 


## Attribute Details

### FromDate

Start date when this company became a competitor.[Default(Today)] [Filter(ge;le)] [Introduced in version 25.1.0.62]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Competitor is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.0.18]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this Competitor. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Competitor.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ToDate

Date until which this company was considered a competitor. The field is blank if the company is still a competitor.[Filter(ge;le)] [Introduced in version 25.1.0.62]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### EnterpriseCompany

Our enterprise company, for which we are defining the competitor. NULL means that the competitor is defined for all the companies in the ERP instance.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

When not null, specifies the party of the competitor.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Marketing.Competitors erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.Competitors erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Marketing_Competitors

Domain API Entity Type: 
Crm_Marketing_Competitor

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Marketing_Competitors?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Marketing_Competitors?$top=10>

