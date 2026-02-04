---
uid: Crm.Sales.Customers
---
# Crm.Sales.Customers


Customers represent external persons or organizations that purchase goods or services from an enterprise company.
    
This entity type defines the commercial relationship between an enterprise company and an external party acting as a customer, including sales terms, pricing, discounts, credit limits, tax settings, and other settings related to working with the customer.
  
Customers are used across sales, orders, invoicing, deliveries, payments, CRM activities, and reporting.
  
For each combination of enterprise company and external party, there can be zero or one Customer record, establishing that party as a customer of the enterprise company.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.Customers  
Base Table: Crm_Customers  
API access:  ReadWrite  

## Renames

Old name: Crm.Customers  
New name: Crm.Sales.Customers  
Version: 25.1.2.28  
Case: 38176  



## Visualization
Display Format: {Party.PartyName:T}  
Search Members: Number; Party.PartyName  
Code Member: Number  
Name Member: Party.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  CustomerTypeId  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Sales.Customers](Crm.Sales.Customers.md)  
  * [Crm.Sales.CustomerExternalAccess](Crm.Sales.CustomerExternalAccess.md)  
  * [Crm.Sales.CustomerProducts](Crm.Sales.CustomerProducts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Crm.Sales.Customers.md#active) | boolean | 1 if the customer is active, 0 - not to list in combo boxes for choosing in new documents 
| [AllowUseAsPrimaryCustomer](Crm.Sales.Customers.md#allowuseasprimarycustomer) | boolean | Specifies whether to allow the customer to be used as primary customer in a sales deal. 
| [AllowUseAsShipToCustomer](Crm.Sales.Customers.md#allowuseasshiptocustomer) | boolean | True to allow the customer to be used as ship to customer in a sales deal. 
| [CreationTime](Crm.Sales.Customers.md#creationtime) | datetime __nullable__ | Date and time when the Customer was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Crm.Sales.Customers.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Customer. `Filter(like)` `ReadOnly` 
| [CreditLimit](Crm.Sales.Customers.md#creditlimit) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | Total credit limit for the customer in the enterprise company base currency. null means there is no limit. 
| [DefaultDeliveryTermDays](Crm.Sales.Customers.md#defaultdeliverytermdays) | int32 | Default term in days for goods delivery, starting at the day of sale 
| [DefaultPaymentStartDays](Crm.Sales.Customers.md#defaultpaymentstartdays) | int32 | Specifies the number of days after the sales order, when the payment becomes due. 0 means that the payment is due immediately. 
| [DefaultPaymentTermDays](Crm.Sales.Customers.md#defaultpaymenttermdays) | int32 | Default payment term in days when issuing documents for this customer 
| [FromDate](Crm.Sales.Customers.md#fromdate) | datetime __nullable__ | Start date of the customer relationship 
| [GracePeriodDays](Crm.Sales.Customers.md#graceperioddays) | int32 | Number of days after the payment deadline, during which the system still allows new sales orders for the customer. 
| [Number](Crm.Sales.Customers.md#number) | string (16) __nullable__ | Unique customer number 
| [PersistSalesOrdersLots](Crm.Sales.Customers.md#persistsalesorderslots) | boolean | If checked, specifies that the lots set in the Sales orders for this customer, cannot be changed during the execution of the Store transactions for these Sales orders. 
| [ThruDate](Crm.Sales.Customers.md#thrudate) | datetime __nullable__ | The date of customer relationship termination. NULL for active customers. 
| [UpdateTime](Crm.Sales.Customers.md#updatetime) | datetime __nullable__ | Date and time when the Customer was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Crm.Sales.Customers.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Customer. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CollectionsResponsible<br />Employee](Crm.Sales.Customers.md#collectionsresponsibleemployee) | [CompanyEmployees](General.Contacts.CompanyEmployees.md) (nullable) | The employee, who is responsible for the collections from the customer |
| [CustomerType](Crm.Sales.Customers.md#customertype) | [CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable) | The user-defined type of this customer. NULL when there is no specific type. Record-level security from the customer type is applied to the individual customers and can be used for security purposes |
| [DefaultCurrency](Crm.Sales.Customers.md#defaultcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The default currency to use when creating new documents for this customer. |
| [DefaultDistributionChannel](Crm.Sales.Customers.md#defaultdistributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | The default distribution channel used when selling to the customer |
| [DefaultPaymentAccount](Crm.Sales.Customers.md#defaultpaymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | The default payment account to use when creating new documents for this customer |
| [DefaultPaymentType](Crm.Sales.Customers.md#defaultpaymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Specifies default payment type for the sales, offers and invoices for this customer. |
| [DefaultPriceList](Crm.Sales.Customers.md#defaultpricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | If not NULL, specifies default price list when selling to this customer |
| [EnterpriseCompany](Crm.Sales.Customers.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company for which this customer is recorded. The same external party can be listed with different conditions for the different enterprise companies. |
| [Party](Crm.Sales.Customers.md#party) | [Parties](General.Contacts.Parties.md) | Base party Id |
| [SalesPerson](Crm.Sales.Customers.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable) | The default sales person for new sales documents for this customer |
| [ServicedByEnterprise<br />CompanyLocation](Crm.Sales.Customers.md#servicedbyenterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location, which sells to this client by default. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.Customers.md#id) | guid |  
| [ObjectVersion](Crm.Sales.Customers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Sales.Customers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Sales.Customers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Sales.Customers.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Sales.Customers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ExternalAccess | [CustomerExternalAccess](Crm.Sales.CustomerExternalAccess.md) | List of `CustomerExternalAcces`(Crm.Sales.CustomerExternalAccess.md) child objects, based on the `Crm.Sales.CustomerExternalAcces.Customer`(Crm.Sales.CustomerExternalAccess.md#customer) back reference 
| Products | [CustomerProducts](Crm.Sales.CustomerProducts.md) | List of `CustomerProduct`(Crm.Sales.CustomerProducts.md) child objects, based on the `Crm.Sales.CustomerProduct.Customer`(Crm.Sales.CustomerProducts.md#customer) back reference 


## Attribute Details

### Active

1 if the customer is active, 0 - not to list in combo boxes for choosing in new documents

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AllowUseAsPrimaryCustomer

Specifies whether to allow the customer to be used as primary customer in a sales deal.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AllowUseAsShipToCustomer

True to allow the customer to be used as ship to customer in a sales deal.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### CreationTime

Date and time when the Customer was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Customer. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### CreditLimit

Total credit limit for the customer in the enterprise company base currency. null means there is no limit.

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( obj.DefaultCurrency != null), obj.EnterpriseCompany.DefaultCustomerCreditLimitBase, obj.CreditLimit)`

Front-End Recalc Expressions:  
`IIF( ( obj.DefaultCurrency != null), obj.EnterpriseCompany.DefaultCustomerCreditLimitBase, obj.CreditLimit)`
### DefaultDeliveryTermDays

Default term in days for goods delivery, starting at the day of sale

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### DefaultPaymentStartDays

Specifies the number of days after the sales order, when the payment becomes due. 0 means that the payment is due immediately.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### DefaultPaymentTermDays

Default payment term in days when issuing documents for this customer

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### FromDate

Start date of the customer relationship

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### GracePeriodDays

Number of days after the payment deadline, during which the system still allows new sales orders for the customer.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Number

Unique customer number

Type: **string (16) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Number, null, "000000")`

### PersistSalesOrdersLots

If checked, specifies that the lots set in the Sales orders for this customer, cannot be changed during the execution of the Store transactions for these Sales orders.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ThruDate

The date of customer relationship termination. NULL for active customers.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UpdateTime

Date and time when the Customer was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Customer. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

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

### CollectionsResponsibleEmployee

The employee, who is responsible for the collections from the customer

Type: **[CompanyEmployees](General.Contacts.CompanyEmployees.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CustomerType

The user-defined type of this customer. NULL when there is no specific type. Record-level security from the customer type is applied to the individual customers and can be used for security purposes

Type: **[CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultCurrency

The default currency to use when creating new documents for this customer.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.EnterpriseCompany.BaseCurrency`
### DefaultDistributionChannel

The default distribution channel used when selling to the customer

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultPaymentAccount

The default payment account to use when creating new documents for this customer

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DefaultPaymentType.GetDefaultPaymentAccount( ).IfNullThen( obj.DefaultPaymentAccount)`
### DefaultPaymentType

Specifies default payment type for the sales, offers and invoices for this customer.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultPriceList

If not NULL, specifies default price list when selling to this customer

Type: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company for which this customer is recorded. The same external party can be listed with different conditions for the different enterprise companies.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Transaction.CurrentEnterpriseCompany`
### Party

Base party Id

Type: **[Parties](General.Contacts.Parties.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SalesPerson

The default sales person for new sales documents for this customer

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServicedByEnterpriseCompanyLocation

The enterprise company location, which sells to this client by default.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Crm.Sales.Customers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.Customers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_Customers

Domain API Entity Type: 
Crm_Sales_Customer

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_Customers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_Customers?$top=10>

