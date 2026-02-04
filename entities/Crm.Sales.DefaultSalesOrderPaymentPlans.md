---
uid: Crm.Sales.DefaultSalesOrderPaymentPlans
---
# Crm.Sales.DefaultSalesOrderPaymentPlans


Default payment plan for new documents of the specified document type

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.DefaultSalesOrderPaymentPlans  
Base Table: Crm_Default_Sales_Order_Payment_Plans  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentType.EntityName}  
Search Members: DocumentType.EntityName  
Name Member: DocumentType.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountPercent](Crm.Sales.DefaultSalesOrderPaymentPlans.md#amountpercent) | decimal (7, 6) __nullable__ | Percent of the sales order amount to be payed. 
| [DueDateFormMethod](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod) | [PaymentPlanDueDateSource](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod) | Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required` 
| [InstallmentNumber](Crm.Sales.DefaultSalesOrderPaymentPlans.md#installmentnumber) | int32 | Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required` 
| [PaymentTermDays](Crm.Sales.DefaultSalesOrderPaymentPlans.md#paymenttermdays) | int32 | Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by Due_Date_Form_Method and Explicit_Payment_Due_Date is taken as due date. `Required` `Default(0)` 
| [Remainder](Crm.Sales.DefaultSalesOrderPaymentPlans.md#remainder) | boolean | Indicates wheather this amount is the remainder of the document. Amount = Total amount of the sales order - explicitly specified amounts in the plan (by Amount_Percent). `Required` `Default(false)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Crm.Sales.DefaultSalesOrderPaymentPlans.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The <see cref="Systems.Documents.DocumentType"/> to which this DefaultSalesOrder<br />PaymentPlan belongs. `Required` `Filter(multi eq)` `Owner` |
| [EnterpriseCompany](Crm.Sales.DefaultSalesOrderPaymentPlans.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Enterprise company for which the current default installment template is valid. If enterprise company is not set then the installment template is valid for all enterprise companies. `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Crm.Sales.DefaultSalesOrderPaymentPlans.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | Enterprise company location (within the chosen enterprise company) for which the current default installment template is valid. If enterprise company location is not set then the installment template is valid for all enterprise company locations. `Filter(multi eq)` |
| [PaymentAccount](Crm.Sales.DefaultSalesOrderPaymentPlans.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | Default payment account for the current installment. null means that there is no default account. `Filter(multi eq)` |
| [PaymentType](Crm.Sales.DefaultSalesOrderPaymentPlans.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Default payment type for the current installment. null means that there is no default payment type. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.DefaultSalesOrderPaymentPlans.md#id) | guid |  
| [ObjectVersion](Crm.Sales.DefaultSalesOrderPaymentPlans.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.DefaultSalesOrderPaymentPlans.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AmountPercent

Percent of the sales order amount to be payed.

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.Remainder, null, obj.AmountPercent)`
### DueDateFormMethod

Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required`

Type: **[PaymentPlanDueDateSource](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod)**  
Category: **System**  
Generic enum type for PaymentPlanDueDateSource properties  
Allowed Values (Crm.Sales.PaymentPlanDueDateSource Enum Members)  

| Value | Description |
| ---- | --- |
| SpecifyTheDateExplicitly | SpecifyTheDateExplicitly value. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 0 <br /> Domain API Value: 'SpecifyTheDateExplicitly' |
| UseInvoiceDate | UseInvoiceDate value. Stored as 'INV'. <br /> Database Value: 'INV' <br /> Model Value: 1 <br /> Domain API Value: 'UseInvoiceDate' |
| UseSalesOrderDate | UseSalesOrderDate value. Stored as 'SLS'. <br /> Database Value: 'SLS' <br /> Model Value: 2 <br /> Domain API Value: 'UseSalesOrderDate' |
| UseSalesOrderDueDate | UseSalesOrderDueDate value. Stored as 'SDD'. <br /> Database Value: 'SDD' <br /> Model Value: 3 <br /> Domain API Value: 'UseSalesOrderDueDate' |
| UseInvoiceDueDate | UseInvoiceDueDate value. Stored as 'IDD'. <br /> Database Value: 'IDD' <br /> Model Value: 4 <br /> Domain API Value: 'UseInvoiceDueDate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InstallmentNumber

Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.DocumentType.DefaultSalesOrderPaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.DocumentType.DefaultSalesOrderPaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### PaymentTermDays

Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by Due_Date_Form_Method and Explicit_Payment_Due_Date is taken as due date. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`

Front-End Recalc Expressions:  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`
### Remainder

Indicates wheather this amount is the remainder of the document. Amount = Total amount of the sales order - explicitly specified amounts in the plan (by Amount_Percent). `Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`
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

### DocumentType

The <see cref="Systems.Documents.DocumentType"/> to which this DefaultSalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Enterprise company for which the current default installment template is valid. If enterprise company is not set then the installment template is valid for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

Enterprise company location (within the chosen enterprise company) for which the current default installment template is valid. If enterprise company location is not set then the installment template is valid for all enterprise company locations. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.EnterpriseCompany.Company != obj.EnterpriseCompanyLocation.Company), null, obj.EnterpriseCompanyLocation)`
### PaymentAccount

Default payment account for the current installment. null means that there is no default account. `Filter(multi eq)`

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PaymentType.GetDefaultPaymentAccount( ).IfNullThen( obj.PaymentAccount)`
### PaymentType

Default payment type for the current installment. null means that there is no default payment type. `Filter(multi eq)`

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Sales.DefaultSalesOrderPaymentPlans erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.DefaultSalesOrderPaymentPlans erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_DefaultSalesOrderPaymentPlans

Domain API Entity Type: 
Crm_Sales_DefaultSalesOrderPaymentPlan

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_DefaultSalesOrderPaymentPlans?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_DefaultSalesOrderPaymentPlans?$top=10>

