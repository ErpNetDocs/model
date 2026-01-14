---
uid: Crm.Pos.Sales
---
# Crm.Pos.Sales Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Stores header-level information for individual retail transactions processed through the Point-of-Sale (POS) system. Each record represents a single sale event, typically associated with a shop, POS terminal, operator, and one or more payment methods. It is optimized for high-volume, anonymous sales, such as those in retail stores, restaurants, and service centers. It supports lifecycle tracking (open, closed, voided), date-based aggregation, and operator accountability. Entity: Pos_Sales (Introduced in version 25.1.3.46)

## Default Visualization
Default Display Text Format:  
_{DocumentNumber}_  
Default Search Members:  
_DocumentNumber_  
Code Data Member:  
_DocumentNumber_  
Category:  _Documents_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.Sales](Crm.Pos.Sales.md)  
  * [Crm.Pos.SaleLines](Crm.Pos.SaleLines.md)  
  * [Crm.Pos.SalePayments](Crm.Pos.SalePayments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Crm.Pos.Sales.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [ClosedAt](Crm.Pos.Sales.md#closedat) | datetime __nullable__ | When the sale was finalized (paid, voided, or completed). `Filter(eq;ge;le)` 
| [DisplayText](Crm.Pos.Sales.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentNumber](Crm.Pos.Sales.md#documentnumber) | string (16) | Receipt document number. `Required` `Filter(eq;like)` 
| [ExternalId](Crm.Pos.Sales.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.Sales.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Pos.Sales.md#id) | guid |  
| [IsVoided](Crm.Pos.Sales.md#isvoided) | boolean | Marked true if sale is canceled/voided. `Required` `Default(false)` `Filter(eq)` 
| [ObjectVersion](Crm.Pos.Sales.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OpenedAt](Crm.Pos.Sales.md#openedat) | datetime | Time of the opening of the POS sale. `Required` `Default(Now)` `Filter(eq;ge;le)` 
| [OriginalSaleNumber](Crm.Pos.Sales.md#originalsalenumber) | string (16) __nullable__ | Original sale document number. Might be specified when this sale refunds/returns another POS sale. Especially useful when the original document is not in the system. `Filter(eq;like)` 
| [SaleDate](Crm.Pos.Sales.md#saledate) | date | Represents the business date of the sale (used for aggregations, reporting, accounting). Typically aligns with date when it was closed, not necessarily when it was opened. `Required` `Default(Now)` `Filter(eq;ge;le)` 
| [SaleKind](Crm.Pos.Sales.md#salekind) | [SaleKind](Crm.Pos.Sales.md#salekind) | Kind of POS sale event. Typically it is "Normal sale". `Required` `Default("SAL")` `Filter(eq)` 
| [SaleStage](Crm.Pos.Sales.md#salestage) | [SaleStage](Crm.Pos.Sales.md#salestage) | General stage of the sale. Finalized sales must have matching amounts between header and detail lines. `Required` `Default("NEW")` `Filter(eq)` 
| [TotalAmount](Crm.Pos.Sales.md#totalamount) | [Amount (14, 2)](../data-types.md#amount) | Total net amount in the sale currency (positive for normal sale, negative for returns/refunds). `Currency: SaleCurrency` `Required` `Filter(eq)` `Introduced in version 25.1.3.47` 
| [TotalAmountBase](Crm.Pos.Sales.md#totalamountbase) | [Amount (14, 2)](../data-types.md#amount) | Total net amount in base currency (positive for normal sale, negative for returns/refunds). `Currency: Location.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)` 
| [TotalAmountReporting](Crm.Pos.Sales.md#totalamountreporting) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Total net amount in reporting currency (if applicable). `Currency: Location.EnterpriseCompany.ReportingCurrency` `Filter(eq;ge;le)` 
| [VoidedAt](Crm.Pos.Sales.md#voidedat) | datetime __nullable__ | Date and time when the document was voided. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ClosedBy](Crm.Pos.Sales.md#closedby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who finalized or closed the sale (may differ from opener). `Filter(multi eq)` |
| [Customer](Crm.Pos.Sales.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Set for known customers (e.g. loyalty program), otherwise null. `Filter(multi eq)` |
| [Location](Crm.Pos.Sales.md#location) | [Locations](Crm.Pos.Locations.md) | Link to location where the sale occurred. `Required` `Filter(multi eq)` |
| [OpenedBy](Crm.Pos.Sales.md#openedby) | [Operators](Crm.Pos.Operators.md) | The operator who created the sale. `Required` `Filter(multi eq)` |
| [Operator](Crm.Pos.Sales.md#operator) | [Operators](Crm.Pos.Operators.md) | Primary operator, responsible for the POS sale (used for reports, commissions, etc.). Typically and by default it is set to the OpenedBy operator. `Required` `Filter(multi eq)` |
| [OriginalSale](Crm.Pos.Sales.md#originalsale) | [Sales](Crm.Pos.Sales.md) (nullable) | Might be specified when this sale refunds/returns another POS sale (and the original POS sale is in the system). `Filter(multi eq)` |
| [PaymentType](Crm.Pos.Sales.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Set when there is single payment type (method) for the whole sale. null when there are multiple payments. `Filter(multi eq)` |
| [SaleCurrency](Crm.Pos.Sales.md#salecurrency) | [Currencies](General.Currencies.Currencies.md) | Reference to the currency in which this POS sale is recorded. `Required` `Filter(multi eq)` `Introduced in version 25.1.3.47` |
| [Terminal](Crm.Pos.Sales.md#terminal) | [Terminals](Crm.Pos.Terminals.md) | Link to specific POS workspace terminal used. `Required` `Filter(multi eq)` |
| [VoidedBy](Crm.Pos.Sales.md#voidedby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who voided the document. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Lines | [SaleLines](Crm.Pos.SaleLines.md) | List of `SaleLine`(Crm.Pos.SaleLines.md) child objects, based on the `Crm.Pos.SaleLine.PosSale`(Crm.Pos.SaleLines.md#possale) back reference 
| Payments | [SalePayments](Crm.Pos.SalePayments.md) | List of `SalePayment`(Crm.Pos.SalePayments.md) child objects, based on the `Crm.Pos.SalePayment.PosSale`(Crm.Pos.SalePayments.md#possale) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ClosedAt

When the sale was finalized (paid, voided, or completed). `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentNumber

Receipt document number. `Required` `Filter(eq;like)`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### IsVoided

Marked true if sale is canceled/voided. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OpenedAt

Time of the opening of the POS sale. `Required` `Default(Now)` `Filter(eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### OriginalSaleNumber

Original sale document number. Might be specified when this sale refunds/returns another POS sale. Especially useful when the original document is not in the system. `Filter(eq;like)`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### SaleDate

Represents the business date of the sale (used for aggregations, reporting, accounting). Typically aligns with date when it was closed, not necessarily when it was opened. `Required` `Default(Now)` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### SaleKind

Kind of POS sale event. Typically it is "Normal sale". `Required` `Default("SAL")` `Filter(eq)`

_Type_: **[SaleKind](Crm.Pos.Sales.md#salekind)**  
_Category_: **System**  
Allowed values for the `SaleKind`(Crm.Pos.Sales.md#salekind) data attribute  
_Allowed Values (Crm.Pos.SalesRepository.SaleKind Enum Members)_  

| Value | Description |
| ---- | --- |
| NormalSale | Normal sale. Stored as 'SAL'. <br /> _Database Value:_ 'SAL' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NormalSale' |
| ReturnOrrefund | Return/refund. Stored as 'RET'. <br /> _Database Value:_ 'RET' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ReturnOrrefund' |
| Mixed | Mixed. Stored as 'MIX'. <br /> _Database Value:_ 'MIX' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Mixed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **NormalSale**  
_Show in UI_: **ShownByDefault**  

### SaleStage

General stage of the sale. Finalized sales must have matching amounts between header and detail lines. `Required` `Default("NEW")` `Filter(eq)`

_Type_: **[SaleStage](Crm.Pos.Sales.md#salestage)**  
_Category_: **System**  
Allowed values for the `SaleStage`(Crm.Pos.Sales.md#salestage) data attribute  
_Allowed Values (Crm.Pos.SalesRepository.SaleStage Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New. Stored as 'NEW'. <br /> _Database Value:_ 'NEW' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Finalized | Finalized. Stored as 'FIN'. <br /> _Database Value:_ 'FIN' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Finalized' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  

### TotalAmount

Total net amount in the sale currency (positive for normal sale, negative for returns/refunds). `Currency: SaleCurrency` `Required` `Filter(eq)` `Introduced in version 25.1.3.47`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalAmountBase

Total net amount in base currency (positive for normal sale, negative for returns/refunds). `Currency: Location.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalAmountReporting

Total net amount in reporting currency (if applicable). `Currency: Location.EnterpriseCompany.ReportingCurrency` `Filter(eq;ge;le)`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VoidedAt

Date and time when the document was voided. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ClosedBy

The operator who finalized or closed the sale (may differ from opener). `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Customer

Set for known customers (e.g. loyalty program), otherwise null. `Filter(multi eq)`

_Type_: **[Customers](Crm.Sales.Customers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Location

Link to location where the sale occurred. `Required` `Filter(multi eq)`

_Type_: **[Locations](Crm.Pos.Locations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OpenedBy

The operator who created the sale. `Required` `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Operator

Primary operator, responsible for the POS sale (used for reports, commissions, etc.). Typically and by default it is set to the OpenedBy operator. `Required` `Filter(multi eq)`

_Type_: **[Operators](Crm.Pos.Operators.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OriginalSale

Might be specified when this sale refunds/returns another POS sale (and the original POS sale is in the system). `Filter(multi eq)`

_Type_: **[Sales](Crm.Pos.Sales.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentType

Set when there is single payment type (method) for the whole sale. null when there are multiple payments. `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SaleCurrency

Reference to the currency in which this POS sale is recorded. `Required` `Filter(multi eq)` `Introduced in version 25.1.3.47`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.Location.EnterpriseCompany.BaseCurrency`

### Terminal

Link to specific POS workspace terminal used. `Required` `Filter(multi eq)`

_Type_: **[Terminals](Crm.Pos.Terminals.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VoidedBy

The operator who voided the document. `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Crm.Pos.Sales erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.Sales erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_Sales

Domain API Entity Type: 
Crm_Pos_Sale

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_Sales?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_Sales?$top=10>

