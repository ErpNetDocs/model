---
uid: Crm.Pos.SaleLines
---
# Crm.Pos.SaleLines Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Stores line-level details for items or services sold in a POS transaction. Each line is linked to a POS Sales record and typically represents a single product, quantity, and unit price. It supports complex tracking in environments like retail chains, restaurants, and service centers, including execution status for kitchen/service integration, discounts, and tax breakdowns. Entity: Pos_Sale_Lines

## Default Visualization
Default Display Text Format:  
_{PosSale.DocumentNumber}_  
Default Search Members:  
_PosSale.DocumentNumber_  
Name Data Member:  
_PosSale.DocumentNumber_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  
Aggregate Root:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedAt](Crm.Pos.SaleLines.md#createdat) | datetime __nullable__ | The time when this line was created. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Default(NowUtc)` `Filter(ge;le)` 
| [DiscountAmount](Crm.Pos.SaleLines.md#discountamount) | decimal (12, 2) | The amount of discount applied to the line. Positive for normal sales, negative for refunds. `Required` `Default(0)` 
| [DisplayText](Crm.Pos.SaleLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExecutionChangedAt](Crm.Pos.SaleLines.md#executionchangedat) | datetime __nullable__ | Indicates the time of the last execution status change. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(ge;le)` 
| [ExecutionNote](Crm.Pos.SaleLines.md#executionnote) | string (64) __nullable__ | Notes for the kitchen or service team, e.g., “no garlic”, “extra ice”, “medium rare”. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). 
| [ExecutionStage](Crm.Pos.SaleLines.md#executionstage) | string (3) __nullable__ | Execution status of the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). 
| [Id](Crm.Pos.SaleLines.md#id) | guid |  
| [IsVoided](Crm.Pos.SaleLines.md#isvoided) | boolean | Specifies whether the current line was voided. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Required` `Default(false)` 
| [LineAmount](Crm.Pos.SaleLines.md#lineamount) | decimal (12, 2) | Final total amount for the line after discount and tax. Positive for normal sales, negative for refunds. `Required` 
| [LineNo](Crm.Pos.SaleLines.md#lineno) | int32 | Line number within the POS sale. `Required` 
| [Notes](Crm.Pos.SaleLines.md#notes) | string (64) __nullable__ | Notes for the line. 
| [ObjectVersion](Crm.Pos.SaleLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Crm.Pos.SaleLines.md#quantity) | decimal (12, 3) | The quantity sold (in Quantity Unit). Positive for normal sales, negative for returns. `Required` 
| [QuantityBase](Crm.Pos.SaleLines.md#quantitybase) | decimal (12, 3) | Quantity sold in base measurement unit of the product. Positive for normal sales, negative for returns. `Required` 
| [TaxAmount](Crm.Pos.SaleLines.md#taxamount) | decimal (12, 2) | Amount of tax (VAT) for this line. The tax amount is already included in Unit Price and Line Amount and is provided for reference. Positive for normal sales, negative for refunds. `Required` `Default(0)` 
| [UnitPrice](Crm.Pos.SaleLines.md#unitprice) | decimal (12, 2) | Gross price (incl. VAT if applicable) at the time of the sale. Should always by a positive number. `Required` 
| [VoidedAt](Crm.Pos.SaleLines.md#voidedat) | datetime __nullable__ | Time of voiding the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedBy](Crm.Pos.SaleLines.md#createdby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who created the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |
| [ExecutionArea](Crm.Pos.SaleLines.md#executionarea) | [LocationAreas](Crm.Pos.LocationAreas.md) (nullable) | Route items to the correct kitchen/bar section. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |
| [ExecutionChangedBy](Crm.Pos.SaleLines.md#executionchangedby) | [Operators](Crm.Pos.Operators.md) (nullable) | Which staff member last updated the execution status. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |
| [ExecutionResource](Crm.Pos.SaleLines.md#executionresource) | [ExecutionResources](Crm.Pos.ExecutionResources.md) (nullable) | The resource (table, room, etc.) used to execute the current line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |
| [ExecutionStatus](Crm.Pos.SaleLines.md#executionstatus) | [ExecutionStatuses](Crm.Pos.ExecutionStatuses.md) (nullable) | User-configurable status of the process. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |
| [PosSale](Crm.Pos.SaleLines.md#possale) | [Sales](Crm.Pos.Sales.md) | The main POS sale. `Required` `Filter(multi eq)` `Owner` |
| [Product](Crm.Pos.SaleLines.md#product) | [Products](General.Products.Products.md) | The sold product. `Required` `Filter(multi eq)` |
| [QuantityUnit](Crm.Pos.SaleLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [VoidedBy](Crm.Pos.SaleLines.md#voidedby) | [Operators](Crm.Pos.Operators.md) (nullable) | Operator who voided the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)` |


## Attribute Details

### CreatedAt

The time when this line was created. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Default(NowUtc)` `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DiscountAmount

The amount of discount applied to the line. Positive for normal sales, negative for refunds. `Required` `Default(0)`

_Type_: **decimal (12, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExecutionChangedAt

Indicates the time of the last execution status change. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExecutionNote

Notes for the kitchen or service team, e.g., “no garlic”, “extra ice”, “medium rare”. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ExecutionStage

Execution status of the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.).

_Type_: **string (3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **3**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### IsVoided

Specifies whether the current line was voided. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LineAmount

Final total amount for the line after discount and tax. Positive for normal sales, negative for refunds. `Required`

_Type_: **decimal (12, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineNo

Line number within the POS sale. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the line.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity sold (in Quantity Unit). Positive for normal sales, negative for returns. `Required`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity sold in base measurement unit of the product. Positive for normal sales, negative for returns. `Required`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TaxAmount

Amount of tax (VAT) for this line. The tax amount is already included in Unit Price and Line Amount and is provided for reference. Positive for normal sales, negative for refunds. `Required` `Default(0)`

_Type_: **decimal (12, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UnitPrice

Gross price (incl. VAT if applicable) at the time of the sale. Should always by a positive number. `Required`

_Type_: **decimal (12, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VoidedAt

Time of voiding the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreatedBy

The operator who created the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExecutionArea

Route items to the correct kitchen/bar section. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[LocationAreas](Crm.Pos.LocationAreas.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExecutionChangedBy

Which staff member last updated the execution status. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExecutionResource

The resource (table, room, etc.) used to execute the current line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[ExecutionResources](Crm.Pos.ExecutionResources.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExecutionStatus

User-configurable status of the process. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[ExecutionStatuses](Crm.Pos.ExecutionStatuses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PosSale

The main POS sale. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Sales](Crm.Pos.Sales.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Product

The sold product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

Measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VoidedBy

Operator who voided the line. Used only for businesses with real-time execution tracking (restaurants, bars, services, etc.). `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pos.SaleLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.SaleLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Pos_SaleLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Pos_SaleLines?$top=10>

