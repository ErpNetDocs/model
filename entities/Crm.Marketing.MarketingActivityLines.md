---
uid: Crm.Marketing.MarketingActivityLines
---
# Crm.Marketing.MarketingActivityLines


Detail records (lines) of the marketing activities.

## General
Namespace: [Crm.Marketing](Crm.Marketing.md)  
Repository: Crm.Marketing.MarketingActivityLines  
Base Table: Crm_Marketing_Activity_Lines  
Introduced In Version: 22.1.5.56  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {MarketingActivity.DocumentNo} {MarketingActivity.DocumentType.TypeName:T}  
Search Members: MarketingActivity.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Marketing.MarketingActivities](Crm.Marketing.MarketingActivities.md)  
Aggregate Root:  
[Crm.Marketing.MarketingActivities](Crm.Marketing.MarketingActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompetitorPrice](Crm.Marketing.MarketingActivityLines.md#competitorprice) | decimal (15, 5) __nullable__ | Price of the competitor 
| [InStoreAvailableQuantity](Crm.Marketing.MarketingActivityLines.md#instoreavailablequantity) | [Quantity (10, 3)](../data-types.md#quantity) __nullable__ | The quantity found in store (in Quantity Unit). NULL means that count was not performed.[Unit: OrderQuantityUnit] [Filter(eq;ge;le)] 
| [InStoreLocation](Crm.Marketing.MarketingActivityLines.md#instorelocation) | string (32) __nullable__ | Location in store, like row, stand, etc. 
| [InStorePrice](Crm.Marketing.MarketingActivityLines.md#instoreprice) | decimal (15, 5) __nullable__ | Price displayed in store.[Filter(eq;ge;le)] 
| [LineNo](Crm.Marketing.MarketingActivityLines.md#lineno) | int32 | Consecutive line number, unique within the marketing activity. Usually is increasing in steps of 10, like in 10, 20, 30, etc.[Required] [Filter(eq)] 
| [Notes](Crm.Marketing.MarketingActivityLines.md#notes) | string (max) __nullable__ | Notes for this MarketingActivityLine. 
| [OrderQuantity](Crm.Marketing.MarketingActivityLines.md#orderquantity) | [Quantity (15, 3)](../data-types.md#quantity) __nullable__ | Recommended quantity (in Quantity Unit) for  new order as a result of the marketing activity. NULL means that there is no specific recommendation.[Unit: OrderQuantityUnit] [Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Competitor](Crm.Marketing.MarketingActivityLines.md#competitor) | [Competitors](Crm.Marketing.Competitors.md) (nullable) | Competitor where marketing activity was held. |
| [Document](Crm.Marketing.MarketingActivityLines.md#document) | [MarketingActivities](Crm.Marketing.MarketingActivities.md) | The owner document. Marketing activity. `Required` `Filter(multi eq)` |
| [MarketingActivity](Crm.Marketing.MarketingActivityLines.md#marketingactivity) | [MarketingActivities](Crm.Marketing.MarketingActivities.md) | Marketing activity |
| [MarketingActivityLineType](Crm.Marketing.MarketingActivityLines.md#marketingactivitylinetype) | [MarketingActivityLineTypes](Crm.Marketing.MarketingActivityLineTypes.md) | Describes what the purpose of the marketing activity is. |
| [OrderQuantityUnit](Crm.Marketing.MarketingActivityLines.md#orderquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of In_Store_Available_<br />Quantity and Order_Quantity. |
| [Product](Crm.Marketing.MarketingActivityLines.md#product) | [Products](General.Products.Products.md) | The specific product that was target of the marketing activity. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Marketing.MarketingActivityLines.md#id) | guid |  
| [ObjectVersion](Crm.Marketing.MarketingActivityLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Marketing.MarketingActivityLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CompetitorPrice

Price of the competitor

Type: **decimal (15, 5) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InStoreAvailableQuantity

The quantity found in store (in Quantity Unit). NULL means that count was not performed.[Unit: OrderQuantityUnit] [Filter(eq;ge;le)]

Type: **[Quantity (10, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InStoreLocation

Location in store, like row, stand, etc.

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### InStorePrice

Price displayed in store.[Filter(eq;ge;le)]

Type: **decimal (15, 5) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the marketing activity. Usually is increasing in steps of 10, like in 10, 20, 30, etc.[Required] [Filter(eq)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.MarketingActivity.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.MarketingActivity.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this MarketingActivityLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### OrderQuantity

Recommended quantity (in Quantity Unit) for  new order as a result of the marketing activity. NULL means that there is no specific recommendation.[Unit: OrderQuantityUnit] [Filter(eq;ge;le)]

Type: **[Quantity (15, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Competitor

Competitor where marketing activity was held.

Type: **[Competitors](Crm.Marketing.Competitors.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The owner document. Marketing activity. `Required` `Filter(multi eq)`

Type: **[MarketingActivities](Crm.Marketing.MarketingActivities.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MarketingActivity

Marketing activity

Type: **[MarketingActivities](Crm.Marketing.MarketingActivities.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### MarketingActivityLineType

Describes what the purpose of the marketing activity is.

Type: **[MarketingActivityLineTypes](Crm.Marketing.MarketingActivityLineTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OrderQuantityUnit

The measurement unit of In_Store_Available_Quantity and Order_Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### Product

The specific product that was target of the marketing activity.

Type: **[Products](General.Products.Products.md)**  
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

[!list limit=1000 erp.entity=Crm.Marketing.MarketingActivityLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.MarketingActivityLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Marketing_MarketingActivityLines

Domain API Entity Type: 
Crm_Marketing_MarketingActivityLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Marketing_MarketingActivityLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Marketing_MarketingActivityLines?$top=10>

