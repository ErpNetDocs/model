---
uid: Crm.Subscriptions.SubscriptionLines
---
# Crm.Subscriptions.SubscriptionLines


Billable products within a subscription.

## General
Namespace: [Crm.Subscriptions](Crm.Subscriptions.md)  
Repository: Crm.Subscriptions.SubscriptionLines  
Base Table: Sm_Subscription_Lines  
Introduced In Version: 24.1.2.6  
API access:  ReadWrite  

## Visualization
Display Format: {Subscription}  
Search Members: Subscription  
Name Member: Subscription  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Subscriptions.Subscriptions](Crm.Subscriptions.Subscriptions.md)  
Aggregate Root:  
[Crm.Subscriptions.Subscriptions](Crm.Subscriptions.Subscriptions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineNo](Crm.Subscriptions.SubscriptionLines.md#lineno) | int32 | Consecutive number of the line within the subscription. `Required` `Filter(eq)` `ORD` 
| [Notes](Crm.Subscriptions.SubscriptionLines.md#notes) | string (max) __nullable__ | Notes for this SubscriptionLine. 
| [Quantity](Crm.Subscriptions.SubscriptionLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, which should be billed. `Unit: QuantityUnit` `Required` `Filter(ge;le)` 
| [SpecificDiscountPercent](Crm.Subscriptions.SubscriptionLines.md#specificdiscountpercent) | decimal (7, 6) __nullable__ | The specific discount to apply for this line. `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Crm.Subscriptions.SubscriptionLines.md#product) | [Products](General.Products.Products.md) | The product to be billed. `Required` `Filter(multi eq)` |
| [QuantityUnit](Crm.Subscriptions.SubscriptionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [Subscription](Crm.Subscriptions.SubscriptionLines.md#subscription) | [Subscriptions](Crm.Subscriptions.Subscriptions.md) | The <see cref="Subscription"/> to which this SubscriptionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Subscriptions.SubscriptionLines.md#id) | guid |  
| [ObjectVersion](Crm.Subscriptions.SubscriptionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Subscriptions.SubscriptionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineNo

Consecutive number of the line within the subscription. `Required` `Filter(eq)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Subscription.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Subscription.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this SubscriptionLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity, which should be billed. `Unit: QuantityUnit` `Required` `Filter(ge;le)`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SpecificDiscountPercent

The specific discount to apply for this line. `Default(0)`

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

### Product

The product to be billed. `Required` `Filter(multi eq)`

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Subscription

The <see cref="Subscription"/> to which this SubscriptionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Subscriptions](Crm.Subscriptions.Subscriptions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Crm.Subscriptions.SubscriptionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Subscriptions.SubscriptionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Subscriptions_SubscriptionLines

Domain API Entity Type: 
Crm_Subscriptions_SubscriptionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Subscriptions_SubscriptionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Subscriptions_SubscriptionLines?$top=10>

