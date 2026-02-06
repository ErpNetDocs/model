---
uid: Crm.Pos.Sales
---
# Crm.Pos.Sales


Stores header-level information for individual retail transactions processed through the Point-of-Sale (POS) system. Each record represents a single sale event, typically associated with a shop, POS terminal, operator, and one or more payment methods. It is optimized for high-volume, anonymous sales, such as those in retail stores, restaurants, and service centers. It supports lifecycle tracking (open, closed, voided), date-based aggregation, and operator accountability.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.Sales  
Base Table: Pos_Sales  
Introduced In Version: 25.1.3.46  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentNumber}  
Search Members: DocumentNumber  
Code Member: DocumentNumber  
Category:  Documents  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.Sales](Crm.Pos.Sales.md)  
  * [Crm.Pos.SaleLines](Crm.Pos.SaleLines.md)  
  * [Crm.Pos.SalePayments](Crm.Pos.SalePayments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ClosedAt](Crm.Pos.Sales.md#closedat) | datetime __nullable__ | When the sale was finalized (paid, voided, or completed).[Filter(eq;ge;le)] 
| [DocumentNumber](Crm.Pos.Sales.md#documentnumber) | string (25) | Receipt document number.[Required] [Filter(eq;like)] 
| [FiscalSalesNumber](Crm.Pos.Sales.md#fiscalsalesnumber) | string (32) __nullable__ | Unique number of the sale, assigned for fiscal reporting purposes. The format is according to the applicable legislation. NULL means that there is no requirement for fiscal sales number for this document or it is unknown.[Filter(multi eq)] [Introduced in version 26.2.1.33] 
| [IsVoided](Crm.Pos.Sales.md#isvoided) | boolean | Marked true if sale is canceled/voided.[Required] [Default(false)] [Filter(eq)] 
| [OpenedAt](Crm.Pos.Sales.md#openedat) | datetime | Time of the opening of the POS sale.[Required] [Default(Now)] [Filter(eq;ge;le)] 
| [OriginalSaleNumber](Crm.Pos.Sales.md#originalsalenumber) | string (25) __nullable__ | Original sale document number. Might be specified when this sale refunds/returns another POS sale. Especially useful when the original document is not in the system.[Filter(eq;like)] 
| [SaleDate](Crm.Pos.Sales.md#saledate) | date | Represents the business date of the sale (used for aggregations, reporting, accounting). Typically aligns with date when it was closed, not necessarily when it was opened.[Required] [Default(Now)] [Filter(eq;ge;le)] 
| [SaleKind](Crm.Pos.Sales.md#salekind) | [SaleKind](Crm.Pos.Sales.md#salekind) | Kind of POS sale event. Typically it is "Normal sale".[Required] [Default(&quot;SAL&quot;)] [Filter(eq)] 
| [SaleStage](Crm.Pos.Sales.md#salestage) | [SaleStage](Crm.Pos.Sales.md#salestage) | General stage of the sale. Finalized sales must have matching amounts between header and detail lines.[Required] [Default(&quot;NEW&quot;)] [Filter(eq)] 
| [TotalAmount](Crm.Pos.Sales.md#totalamount) | [Amount (14, 2)](../data-types.md#amount) | Total gross amount in the sale currency.[Currency: SaleCurrency] [Required] [Filter(eq)] [Introduced in version 25.1.3.47] 
| [TotalAmountBase](Crm.Pos.Sales.md#totalamountbase) | [Amount (14, 2)](../data-types.md#amount) | Total gross amount in base currency.[Currency: Location.EnterpriseCompany.BaseCurrency] [Required] [Filter(eq;ge;le)] 
| [TotalAmountReporting](Crm.Pos.Sales.md#totalamountreporting) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Total gross amount in reporting currency (if applicable).[Currency: Location.EnterpriseCompany.ReportingCurrency] [Filter(eq;ge;le)] 
| [VoidedAt](Crm.Pos.Sales.md#voidedat) | datetime __nullable__ | Date and time when the document was voided.[Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ClosedBy](Crm.Pos.Sales.md#closedby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who finalized or closed the sale (may differ from opener). |
| [Customer](Crm.Pos.Sales.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Set for known customers (e.g. loyalty program), otherwise null. |
| [Location](Crm.Pos.Sales.md#location) | [Locations](Crm.Pos.Locations.md) | Link to location where the sale occurred. |
| [OpenedBy](Crm.Pos.Sales.md#openedby) | [Operators](Crm.Pos.Operators.md) | The operator who created the sale. |
| [Operator](Crm.Pos.Sales.md#operator) | [Operators](Crm.Pos.Operators.md) | Primary operator, responsible for the POS sale (used for reports, commissions, etc.). Typically and by default it is set to the OpenedBy operator. |
| [OriginalSale](Crm.Pos.Sales.md#originalsale) | [Sales](Crm.Pos.Sales.md) (nullable) | Might be specified when this sale refunds/returns another POS sale (and the original POS sale is in the system). |
| [PaymentType](Crm.Pos.Sales.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Set when there is single payment type (method) for the whole sale. NULL when there are multiple payments. |
| [SaleCurrency](Crm.Pos.Sales.md#salecurrency) | [Currencies](General.Currencies.Currencies.md) | Reference to the currency in which this POS sale is recorded. |
| [Terminal](Crm.Pos.Sales.md#terminal) | [Terminals](Crm.Pos.Terminals.md) | Link to specific POS workspace terminal used. |
| [VoidedBy](Crm.Pos.Sales.md#voidedby) | [Operators](Crm.Pos.Operators.md) (nullable) | The operator who voided the document. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.Sales.md#id) | guid |  
| [ObjectVersion](Crm.Pos.Sales.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.Sales.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.Sales.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.Sales.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.Sales.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Lines | [SaleLines](Crm.Pos.SaleLines.md) | List of `SaleLine`(Crm.Pos.SaleLines.md) child objects, based on the `Crm.Pos.SaleLine.PosSale`(Crm.Pos.SaleLines.md#possale) back reference 
| Payments | [SalePayments](Crm.Pos.SalePayments.md) | List of `SalePayment`(Crm.Pos.SalePayments.md) child objects, based on the `Crm.Pos.SalePayment.PosSale`(Crm.Pos.SalePayments.md#possale) back reference 


## Attribute Details

### ClosedAt

When the sale was finalized (paid, voided, or completed).[Filter(eq;ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DocumentNumber

Receipt document number.[Required] [Filter(eq;like)]

Type: **string (25)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **25**  
Show in UI: **ShownByDefault**  

### FiscalSalesNumber

Unique number of the sale, assigned for fiscal reporting purposes. The format is according to the applicable legislation. NULL means that there is no requirement for fiscal sales number for this document or it is unknown.[Filter(multi eq)] [Introduced in version 26.2.1.33]

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### IsVoided

Marked true if sale is canceled/voided.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### OpenedAt

Time of the opening of the POS sale.[Required] [Default(Now)] [Filter(eq;ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### OriginalSaleNumber

Original sale document number. Might be specified when this sale refunds/returns another POS sale. Especially useful when the original document is not in the system.[Filter(eq;like)]

Type: **string (25) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **25**  
Show in UI: **ShownByDefault**  

### SaleDate

Represents the business date of the sale (used for aggregations, reporting, accounting). Typically aligns with date when it was closed, not necessarily when it was opened.[Required] [Default(Now)] [Filter(eq;ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### SaleKind

Kind of POS sale event. Typically it is "Normal sale".[Required] [Default(&quot;SAL&quot;)] [Filter(eq)]

Type: **[SaleKind](Crm.Pos.Sales.md#salekind)**  
Category: **System**  
Allowed values for the `SaleKind`(Crm.Pos.Sales.md#salekind) data attribute  
Allowed Values (Crm.Pos.SalesRepository.SaleKind Enum Members)  

| Value | Description |
| ---- | --- |
| NormalSale | Normal sale. Stored as 'SAL'. <br /> Database Value: 'SAL' <br /> Model Value: 0 <br /> Domain API Value: 'NormalSale' |
| ReturnOrrefund | Return/refund. Stored as 'RET'. <br /> Database Value: 'RET' <br /> Model Value: 1 <br /> Domain API Value: 'ReturnOrrefund' |
| Invoice | Invoice value. Stored as 'INV'. <br /> Database Value: 'INV' <br /> Model Value: 2 <br /> Domain API Value: 'Invoice' |
| CreditNote | CreditNote value. Stored as 'CRN'. <br /> Database Value: 'CRN' <br /> Model Value: 3 <br /> Domain API Value: 'CreditNote' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **NormalSale**  
Show in UI: **ShownByDefault**  

### SaleStage

General stage of the sale. Finalized sales must have matching amounts between header and detail lines.[Required] [Default(&quot;NEW&quot;)] [Filter(eq)]

Type: **[SaleStage](Crm.Pos.Sales.md#salestage)**  
Category: **System**  
Allowed values for the `SaleStage`(Crm.Pos.Sales.md#salestage) data attribute  
Allowed Values (Crm.Pos.SalesRepository.SaleStage Enum Members)  

| Value | Description |
| ---- | --- |
| New | New. Stored as 'NEW'. <br /> Database Value: 'NEW' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Finalized | Finalized. Stored as 'FIN'. <br /> Database Value: 'FIN' <br /> Model Value: 1 <br /> Domain API Value: 'Finalized' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **New**  
Show in UI: **ShownByDefault**  

### TotalAmount

Total gross amount in the sale currency.[Currency: SaleCurrency] [Required] [Filter(eq)] [Introduced in version 25.1.3.47]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalAmountBase

Total gross amount in base currency.[Currency: Location.EnterpriseCompany.BaseCurrency] [Required] [Filter(eq;ge;le)]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalAmountReporting

Total gross amount in reporting currency (if applicable).[Currency: Location.EnterpriseCompany.ReportingCurrency] [Filter(eq;ge;le)]

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VoidedAt

Date and time when the document was voided.[Filter(eq;ge;le)]

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

### ClosedBy

The operator who finalized or closed the sale (may differ from opener).

Type: **[Operators](Crm.Pos.Operators.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Customer

Set for known customers (e.g. loyalty program), otherwise null.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Location

Link to location where the sale occurred.

Type: **[Locations](Crm.Pos.Locations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OpenedBy

The operator who created the sale.

Type: **[Operators](Crm.Pos.Operators.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Operator

Primary operator, responsible for the POS sale (used for reports, commissions, etc.). Typically and by default it is set to the OpenedBy operator.

Type: **[Operators](Crm.Pos.Operators.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OriginalSale

Might be specified when this sale refunds/returns another POS sale (and the original POS sale is in the system).

Type: **[Sales](Crm.Pos.Sales.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentType

Set when there is single payment type (method) for the whole sale. NULL when there are multiple payments.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SaleCurrency

Reference to the currency in which this POS sale is recorded.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.Location.EnterpriseCompany.BaseCurrency`

### Terminal

Link to specific POS workspace terminal used.

Type: **[Terminals](Crm.Pos.Terminals.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VoidedBy

The operator who voided the document.

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

