---
uid: Crm.Sales.DefaultSalesOrderPaymentPlans
---
# Crm.Sales.DefaultSalesOrderPaymentPlans Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Default payment plan for new documents of the specified document type. Entity: Crm_Default_Sales_Order_Payment_Plans

## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Crm.Sales.DefaultSalesOrderPaymentPlans.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DueDateFormMethod](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod) | [PaymentPlanDueDateSource](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod) | Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required` 
| [Id](Crm.Sales.DefaultSalesOrderPaymentPlans.md#id) | guid |  
| [InstallmentNumber](Crm.Sales.DefaultSalesOrderPaymentPlans.md#installmentnumber) | int32 | Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required` 
| [ObjectVersion](Crm.Sales.DefaultSalesOrderPaymentPlans.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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


## Attribute Details

### AmountPercent

Percent of the sales order amount to be payed.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.Remainder, null, obj.AmountPercent)`
### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DueDateFormMethod

Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required`

_Type_: **[PaymentPlanDueDateSource](Crm.Sales.DefaultSalesOrderPaymentPlans.md#duedateformmethod)**  
_Category_: **System**  
Generic enum type for PaymentPlanDueDateSource properties  
_Allowed Values (Crm.Sales.PaymentPlanDueDateSource Enum Members)_  

| Value | Description |
| ---- | --- |
| SpecifyTheDateExplicitly | SpecifyTheDateExplicitly value. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'SpecifyTheDateExplicitly' |
| UseInvoiceDate | UseInvoiceDate value. Stored as 'INV'. <br /> _Database Value:_ 'INV' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'UseInvoiceDate' |
| UseSalesOrderDate | UseSalesOrderDate value. Stored as 'SLS'. <br /> _Database Value:_ 'SLS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'UseSalesOrderDate' |
| UseSalesOrderDueDate | UseSalesOrderDueDate value. Stored as 'SDD'. <br /> _Database Value:_ 'SDD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'UseSalesOrderDueDate' |
| UseInvoiceDueDate | UseInvoiceDueDate value. Stored as 'IDD'. <br /> _Database Value:_ 'IDD' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'UseInvoiceDueDate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InstallmentNumber

Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.DocumentType.DefaultSalesOrderPaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.DocumentType.DefaultSalesOrderPaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PaymentTermDays

Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by Due_Date_Form_Method and Explicit_Payment_Due_Date is taken as due date. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`

_Front-End Recalc Expressions:_  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`
### Remainder

Indicates wheather this amount is the remainder of the document. Amount = Total amount of the sales order - explicitly specified amounts in the plan (by Amount_Percent). `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`

## Reference Details

### DocumentType

The <see cref="Systems.Documents.DocumentType"/> to which this DefaultSalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Enterprise company for which the current default installment template is valid. If enterprise company is not set then the installment template is valid for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

Enterprise company location (within the chosen enterprise company) for which the current default installment template is valid. If enterprise company location is not set then the installment template is valid for all enterprise company locations. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.EnterpriseCompany.Company != obj.EnterpriseCompanyLocation.Company), null, obj.EnterpriseCompanyLocation)`
### PaymentAccount

Default payment account for the current installment. null means that there is no default account. `Filter(multi eq)`

_Type_: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PaymentType.GetDefaultPaymentAccount( ).IfNullThen( obj.PaymentAccount)`
### PaymentType

Default payment type for the current installment. null means that there is no default payment type. `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
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

