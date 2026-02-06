---
uid: Crm.Pricing.LineDiscounts
---
# Crm.Pricing.LineDiscounts


Discount policies for sales documents.

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.LineDiscounts  
Base Table: Crm_Line_Discounts  
API access:  ReadWrite  

## Renames

Old name: Crm.LineDiscounts  
New name: Crm.Pricing.LineDiscounts  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {DiscountPercent:P} {Description}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.LineDiscounts](Crm.Pricing.LineDiscounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Crm.Pricing.LineDiscounts.md#description) | string (50) __nullable__ | The description of the discount that is shown to the operator when they should choose between different discounts 
| [DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel) | [DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel) | Specifies the cascade level (1..3), on which the discount is applied. The discounts from level 1,2 and 3 are applied to three different discount fields in the sales order. The discount for each level is determined separately, by applying the same algorithm. 
| [DiscountPercent](Crm.Pricing.LineDiscounts.md#discountpercent) | decimal (7, 6) | The discount percent that should be applied if all the matching criteria are met. 
| [FromDate](Crm.Pricing.LineDiscounts.md#fromdate) | datetime __nullable__ | Starting date of validity of the discount. NULL means no from date restriction 
| [IsActive](Crm.Pricing.LineDiscounts.md#isactive) | boolean | Indicates whether the current Line Discount is active. 
| [MaxQuantity](Crm.Pricing.LineDiscounts.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or less than the specified here. 
| [MinQuantity](Crm.Pricing.LineDiscounts.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or more than the specified here. 
| [Priority](Crm.Pricing.LineDiscounts.md#priority) | [Priority](Crm.Pricing.LineDiscounts.md#priority) | The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied. 
| [ThruDate](Crm.Pricing.LineDiscounts.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of validity of the discount. If NULL, the discount is valid forever 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Campaign](Crm.Pricing.LineDiscounts.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) (nullable) | Тhe marketing campaign to which the current definition belongs. |
| [Customer](Crm.Pricing.LineDiscounts.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Apply the discount only if this is the customer |
| [CustomerType](Crm.Pricing.LineDiscounts.md#customertype) | [CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable) | Apply the discount only if the customer is of this customer type |
| [DistributionChannel](Crm.Pricing.LineDiscounts.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | Apply the discount only when the sales document is on the specified channel |
| [DocumentAmountType](Crm.Pricing.LineDiscounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | The document amount type that is used as category for this discount. When specified, triggers the recording of the applied discount amount in the Document Distributed Amounts panel in sales orders. |
| [EnterpriseCompany](Crm.Pricing.LineDiscounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not NULL, the policy is applied only for documents of the specified enterprise company |
| [EnterpriseCompanyLocation](Crm.Pricing.LineDiscounts.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When set, the policy is applied only for documents of the specified enterprise company location. |
| [PriceList](Crm.Pricing.LineDiscounts.md#pricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | Apply the discount only if this price list is used |
| [Product](Crm.Pricing.LineDiscounts.md#product) | [Products](General.Products.Products.md) (nullable) | Apply the discount only when this specific product is sold |
| [ProductGroup](Crm.Pricing.LineDiscounts.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Apply the discount only if the product sold is contained in this product group or any of its sub-groups |
| [TargetGroup](Crm.Pricing.LineDiscounts.md#targetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | Apply the discount only if the customer is included in this target group |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.LineDiscounts.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.LineDiscounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.LineDiscounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.LineDiscounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.LineDiscounts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.LineDiscounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Description

The description of the discount that is shown to the operator when they should choose between different discounts

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### DiscountLevel

Specifies the cascade level (1..3), on which the discount is applied. The discounts from level 1,2 and 3 are applied to three different discount fields in the sales order. The discount for each level is determined separately, by applying the same algorithm.

Type: **[DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel)**  
Indexed: **True**  
Category: **System**  
Allowed values for the `DiscountLevel`(Crm.Pricing.LineDiscounts.md#discountlevel) data attribute  
Allowed Values (Crm.Pricing.LineDiscountsRepository.DiscountLevel Enum Members)  

| Value | Description |
| ---- | --- |
| One | One value. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'One' |
| Two | Two value. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'Three' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Default Value: **One**  
Show in UI: **ShownByDefault**  

### DiscountPercent

The discount percent that should be applied if all the matching criteria are met.

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### FromDate

Starting date of validity of the discount. NULL means no from date restriction

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Line Discount is active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### MaxQuantity

Apply the discount only if the quantity sold is equal to or less than the specified here.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MinQuantity

Apply the discount only if the quantity sold is equal to or more than the specified here.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Priority

The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied.

Type: **[Priority](Crm.Pricing.LineDiscounts.md#priority)**  
Category: **System**  
Generic enum type for Priority properties  
Allowed Values (General.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Lowest' |
| Low | Low value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
| Medium | Medium value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Medium' |
| High | High value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'High' |
| Highest | Highest value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Highest' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **3**  
Show in UI: **ShownByDefault**  

### ThruDate

Ending date (inclusive) of validity of the discount. If NULL, the discount is valid forever

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

### Campaign

Тhe marketing campaign to which the current definition belongs.

Type: **[Campaigns](Crm.Marketing.Campaigns.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Customer

Apply the discount only if this is the customer

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CustomerType

Apply the discount only if the customer is of this customer type

Type: **[CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DistributionChannel

Apply the discount only when the sales document is on the specified channel

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentAmountType

The document amount type that is used as category for this discount. When specified, triggers the recording of the applied discount amount in the Document Distributed Amounts panel in sales orders.

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When not NULL, the policy is applied only for documents of the specified enterprise company

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

When set, the policy is applied only for documents of the specified enterprise company location.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.EnterpriseCompanyLocation != null) AndAlso ( obj.EnterpriseCompanyLocation.Company != obj.EnterpriseCompany)), null, obj.EnterpriseCompanyLocation.Company)`
### PriceList

Apply the discount only if this price list is used

Type: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

Apply the discount only when this specific product is sold

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductGroup

Apply the discount only if the product sold is contained in this product group or any of its sub-groups

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TargetGroup

Apply the discount only if the customer is included in this target group

Type: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.LineDiscounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.LineDiscounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_LineDiscounts

Domain API Entity Type: 
Crm_Pricing_LineDiscount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_LineDiscounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_LineDiscounts?$top=10>

