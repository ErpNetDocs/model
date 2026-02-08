---
uid: Crm.Pos.SaleLines
---
# Crm.Pos.SaleLines


Stores line-level details for items or services sold in a POS transaction. Each line is linked to a POS Sales record and typically represents a single product, quantity, and unit price. It supports complex tracking in environments like retail chains, restaurants, and service centers, including execution status for kitchen/service integration, discounts, and tax breakdowns.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.SaleLines  
Base Table: Pos_Sale_Lines  
Introduced In Version: 25.1.3.46  
API access:  ReadWrite  

## Visualization
Display Format: {PosSale.DocumentNumber}  
Search Members: PosSale.DocumentNumber  
Name Member: PosSale.DocumentNumber  
Category:  Documents  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  
Aggregate Root:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedAt](Crm.Pos.SaleLines.md#createdat) | datetime __nullable__ | The time when this line was created. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Default(Now)` `Filter(eq;ge;le)` 
| [DiscountAmount](Crm.Pos.SaleLines.md#discountamount) | [Amount (12, 2)](../data-types.md#amount) | The amount of discount applied to the line. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Default(0)` `Filter(eq)` 
| [ExecutionChangedAt](Crm.Pos.SaleLines.md#executionchangedat) | datetime __nullable__ | Indicates the time of the last execution status change. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq;ge;le)` 
| [ExecutionNote](Crm.Pos.SaleLines.md#executionnote) | string (64) __nullable__ | Notes for the kitchen or service team, e.g., “no garlic”, “extra ice”, “medium rare”. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(like)` 
| [ExecutionStage](Crm.Pos.SaleLines.md#executionstage) | [ExecutionStage](Crm.Pos.SaleLines.md#executionstage) __nullable__ | Execution status of the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq)` 
| [IsVoided](Crm.Pos.SaleLines.md#isvoided) | boolean | Specifies whether the current line was voided. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Required` `Default(false)` `Filter(eq)` 
| [LineAmount](Crm.Pos.SaleLines.md#lineamount) | [Amount (12, 2)](../data-types.md#amount) | Final total amount for the line after discount and tax. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Filter(eq)` 
| [LineNo](Crm.Pos.SaleLines.md#lineno) | int32 | Line number within the POS sale.`Required` `Filter(eq)` 
| [Notes](Crm.Pos.SaleLines.md#notes) | string (64) __nullable__ | Notes for the line.`Filter(like)` 
| [Quantity](Crm.Pos.SaleLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity sold (in Quantity Unit). Positive for normal sales, negative for returns.`Unit: QuantityUnit` `Required` `Filter(eq;ge;le)` 
| [QuantityBase](Crm.Pos.SaleLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity sold in base measurement unit of the product. Positive for normal sales, negative for returns.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq)` 
| [TaxAmount](Crm.Pos.SaleLines.md#taxamount) | [Amount (12, 2)](../data-types.md#amount) | Amount of tax (VAT) for this line. The tax amount is already included in Unit Price and Line Amount and is provided for reference. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Default(0)` `Filter(eq)` 
| [UnitPrice](Crm.Pos.SaleLines.md#unitprice) | [Amount (12, 2)](../data-types.md#amount) | Gross price (incl. VAT if applicable) at the time of the sale. Should always by a positive number.`Currency: PosSale.SaleCurrency` `Required` `Filter(eq)` 
| [VoidedAt](Crm.Pos.SaleLines.md#voidedat) | datetime __nullable__ | Time of voiding the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedBy](Crm.Pos.SaleLines.md#createdby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who created the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |
| [ExecutionArea](Crm.Pos.SaleLines.md#executionarea) | [LocationAreas](Crm.Pos.LocationAreas.md) (nullable) | Route items to the correct kitchen/bar section. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |
| [ExecutionChangedBy](Crm.Pos.SaleLines.md#executionchangedby) | [Operators](Crm.Pos.Operators.md) (nullable) | Which staff member last updated the execution status. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |
| [ExecutionResource](Crm.Pos.SaleLines.md#executionresource) | [ExecutionResources](Crm.Pos.ExecutionResources.md) (nullable) | The resource (table, room, etc.) used to execute the current line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |
| [ExecutionStatus](Crm.Pos.SaleLines.md#executionstatus) | [ExecutionStatuses](Crm.Pos.ExecutionStatuses.md) (nullable) | User-configurable status of the process. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |
| [PosSale](Crm.Pos.SaleLines.md#possale) | [Sales](Crm.Pos.Sales.md) | The main POS sale. |
| [Product](Crm.Pos.SaleLines.md#product) | [Products](General.Products.Products.md) | The sold product. |
| [QuantityUnit](Crm.Pos.SaleLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Measurement unit of Quantity. |
| [VoidedBy](Crm.Pos.SaleLines.md#voidedby) | [Operators](Crm.Pos.Operators.md) (nullable) | Operator who voided the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.SaleLines.md#id) | guid |  
| [ObjectVersion](Crm.Pos.SaleLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pos.SaleLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreatedAt

The time when this line was created. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Default(Now)` `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### DiscountAmount

The amount of discount applied to the line. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Default(0)` `Filter(eq)`

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ExecutionChangedAt

Indicates the time of the last execution status change. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionNote

Notes for the kitchen or service team, e.g., “no garlic”, “extra ice”, “medium rare”. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ExecutionStage

Execution status of the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq)`

Type: **[ExecutionStage](Crm.Pos.SaleLines.md#executionstage) __nullable__**  
Category: **System**  
Allowed values for the `ExecutionStage`(Crm.Pos.ExecutionStatuses.md#executionstage) data attribute  
Allowed Values (Crm.Pos.ExecutionStatusesRepository.ExecutionStage Enum Members)  

| Value | Description |
| ---- | --- |
| Pending | Pending. Stored as 'PND'. <br /> Database Value: 'PND' <br /> Model Value: 0 <br /> Domain API Value: 'Pending' |
| Prepare | Prepare. Stored as 'PRP'. <br /> Database Value: 'PRP' <br /> Model Value: 1 <br /> Domain API Value: 'Prepare' |
| Deliver | Deliver. Stored as 'DEL'. <br /> Database Value: 'DEL' <br /> Model Value: 2 <br /> Domain API Value: 'Deliver' |
| Finalize | Finalize. Stored as 'FIN'. <br /> Database Value: 'FIN' <br /> Model Value: 3 <br /> Domain API Value: 'Finalize' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsVoided

Specifies whether the current line was voided. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LineAmount

Final total amount for the line after discount and tax. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Filter(eq)`

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Line number within the POS sale.`Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PosSale.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.PosSale.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for the line.`Filter(like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity sold (in Quantity Unit). Positive for normal sales, negative for returns.`Unit: QuantityUnit` `Required` `Filter(eq;ge;le)`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity sold in base measurement unit of the product. Positive for normal sales, negative for returns.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq)`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxAmount

Amount of tax (VAT) for this line. The tax amount is already included in Unit Price and Line Amount and is provided for reference. Positive for normal sales, negative for refunds.`Currency: PosSale.SaleCurrency` `Required` `Default(0)` `Filter(eq)`

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### UnitPrice

Gross price (incl. VAT if applicable) at the time of the sale. Should always by a positive number.`Currency: PosSale.SaleCurrency` `Required` `Filter(eq)`

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VoidedAt

Time of voiding the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).`Filter(eq;ge;le)`

Type: **datetime __nullable__**  
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

### CreatedBy

The operator who created the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[Operators](Crm.Pos.Operators.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExecutionArea

Route items to the correct kitchen/bar section. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[LocationAreas](Crm.Pos.LocationAreas.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExecutionChangedBy

Which staff member last updated the execution status. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[Operators](Crm.Pos.Operators.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExecutionResource

The resource (table, room, etc.) used to execute the current line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[ExecutionResources](Crm.Pos.ExecutionResources.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExecutionStatus

User-configurable status of the process. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[ExecutionStatuses](Crm.Pos.ExecutionStatuses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosSale

The main POS sale.

Type: **[Sales](Crm.Pos.Sales.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Product

The sold product.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

Measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VoidedBy

Operator who voided the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

Type: **[Operators](Crm.Pos.Operators.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pos.SaleLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.SaleLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_SaleLines

Domain API Entity Type: 
Crm_Pos_SaleLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_SaleLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_SaleLines?$top=10>

