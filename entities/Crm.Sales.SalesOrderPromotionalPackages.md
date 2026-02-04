---
uid: Crm.Sales.SalesOrderPromotionalPackages
---
# Crm.Sales.SalesOrderPromotionalPackages


Sales Order Promotional Packages represent promotional bundles or offers applied within a Sales Order.
    
This data type defines the promotional packages included in a sales order, consisting of a predefined combination of products or services offered under special commercial conditions, such as bundled pricing, discounts, or promotional rules.

Promotional packages are used to apply, track, and analyze promotions in sales orders, ensuring consistent pricing, correct fulfillment, and accurate reporting of promotion-driven sales.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.SalesOrderPromotionalPackages  
Base Table: Crm_Sales_Order_Promotional_Packages  
API access:  ReadWrite  

## Visualization
Display Format: {Id}. {SalesOrder.DocumentNo} {SalesOrder.DocumentType.TypeName:T}  
Search Members: SalesOrder.DocumentNo  
Name Member: SalesOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  
Aggregate Root:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineNumber](Crm.Sales.SalesOrderPromotionalPackages.md#linenumber) | int32 | Consecutive line number of the package, unique within the document. `Required` `Filter(eq)` 
| [NumberOfPackages](Crm.Sales.SalesOrderPromotionalPackages.md#numberofpackages) | int32 | Number of packages sold. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Sales.SalesOrderPromotionalPackages.md#document) | [SalesOrders](Crm.Sales.SalesOrders.md) | The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPromotional<br />Package belongs. `Required` `Filter(multi eq)` |
| [PromotionalPackage](Crm.Sales.SalesOrderPromotionalPackages.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) | The type of promotional package sold. `Required` `Filter(multi eq)` |
| [SalesOrder](Crm.Sales.SalesOrderPromotionalPackages.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) | The <see cref="SalesOrder"/> to which this SalesOrderPromotional<br />Package belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.SalesOrderPromotionalPackages.md#id) | guid |  
| [ObjectVersion](Crm.Sales.SalesOrderPromotionalPackages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.SalesOrderPromotionalPackages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineNumber

Consecutive line number of the package, unique within the document. `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.SalesOrder.PromotionalPackages.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.SalesOrder.PromotionalPackages.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### NumberOfPackages

Number of packages sold. `Required` `Default(0)`

Type: **int32**  
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

### Document

The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPromotionalPackage belongs. `Required` `Filter(multi eq)`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PromotionalPackage

The type of promotional package sold. `Required` `Filter(multi eq)`

Type: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesOrder

The <see cref="SalesOrder"/> to which this SalesOrderPromotionalPackage belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
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

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderPromotionalPackages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderPromotionalPackages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_SalesOrderPromotionalPackages

Domain API Entity Type: 
Crm_Sales_SalesOrderPromotionalPackage

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_SalesOrderPromotionalPackages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_SalesOrderPromotionalPackages?$top=10>

