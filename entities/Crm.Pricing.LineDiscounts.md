---
uid: Crm.Pricing.LineDiscounts
---
# Crm.Pricing.LineDiscounts Entity

**Namespace:** [Crm.Pricing](Crm.Pricing.md)  

Discount policies for sales documents. Entity: Crm_Line_Discounts

## Renames

Old name: **Crm.LineDiscounts**  
New name: **Crm.Pricing.LineDiscounts**  
Version: **25.1.1.36**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{DiscountPercent:P} {Description}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.LineDiscounts](Crm.Pricing.LineDiscounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Crm.Pricing.LineDiscounts.md#description) | string (50) __nullable__ | The description of the discount that is shown to the operator when they should choose between different discounts. `Filter(like)` 
| [DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel) | [DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel) | Specifies the cascade level (1..3), on which the discount is applied. The discounts from level 1,2 and 3 are applied to three different discount fields in the sales order. The discount for each level is determined separately, by applying the same algorithm. `Required` `Default("1")` `Filter(multi eq)` `ORD` `Introduced in version 23.1.2.8` 
| [DiscountPercent](Crm.Pricing.LineDiscounts.md#discountpercent) | decimal (7, 6) | The discount percent that should be applied if all the matching criteria are met. `Required` `Default(0)` `Filter(ge;le)` 
| [DisplayText](Crm.Pricing.LineDiscounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.Pricing.LineDiscounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.LineDiscounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FromDate](Crm.Pricing.LineDiscounts.md#fromdate) | datetime __nullable__ | Starting date of validity of the discount. null means no from date restriction. `Filter(eq;ge;le)` 
| [Id](Crm.Pricing.LineDiscounts.md#id) | guid |  
| [IsActive](Crm.Pricing.LineDiscounts.md#isactive) | boolean | Indicates whether the current Line Discount is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.2.5` 
| [MaxQuantity](Crm.Pricing.LineDiscounts.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or less than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [MinQuantity](Crm.Pricing.LineDiscounts.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or more than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [ObjectVersion](Crm.Pricing.LineDiscounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Priority](Crm.Pricing.LineDiscounts.md#priority) | [Priority](Crm.Pricing.LineDiscounts.md#priority) | The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied. `Required` `Default(3)` 
| [ThruDate](Crm.Pricing.LineDiscounts.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of validity of the discount. If null, the discount is valid forever. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Campaign](Crm.Pricing.LineDiscounts.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) (nullable) | Тhe marketing campaign to which the current definition belongs. `Filter(multi eq)` `Introduced in version 22.1.4.67` |
| [Customer](Crm.Pricing.LineDiscounts.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Apply the discount only if this is the customer. `Filter(multi eq)` |
| [CustomerType](Crm.Pricing.LineDiscounts.md#customertype) | [CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable) | Apply the discount only if the customer is of this customer type. `Filter(multi eq)` |
| [DistributionChannel](Crm.Pricing.LineDiscounts.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | Apply the discount only when the sales document is on the specified channel. `Filter(multi eq)` |
| [DocumentAmountType](Crm.Pricing.LineDiscounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | The document amount type that is used as category for this discount. When specified, triggers the recording of the applied discount amount in the Document Distributed Amounts panel in sales orders. `Filter(multi eq)` `Introduced in version 25.1.1.26` |
| [EnterpriseCompany](Crm.Pricing.LineDiscounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, the policy is applied only for documents of the specified enterprise company . `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Crm.Pricing.LineDiscounts.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When set, the policy is applied only for documents of the specified enterprise company location. `Filter(multi eq)` |
| [PriceList](Crm.Pricing.LineDiscounts.md#pricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | Apply the discount only if this price list is used. `Filter(multi eq)` |
| [Product](Crm.Pricing.LineDiscounts.md#product) | [Products](General.Products.Products.md) (nullable) | Apply the discount only when this specific product is sold. `Filter(multi eq)` |
| [ProductGroup](Crm.Pricing.LineDiscounts.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Apply the discount only if the product sold is contained in this product group or any of its sub-groups. `Filter(multi eq)` |
| [TargetGroup](Crm.Pricing.LineDiscounts.md#targetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | Apply the discount only if the customer is included in this target group. `Filter(multi eq)` |


## Attribute Details

### Description

The description of the discount that is shown to the operator when they should choose between different discounts. `Filter(like)`

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### DiscountLevel

Specifies the cascade level (1..3), on which the discount is applied. The discounts from level 1,2 and 3 are applied to three different discount fields in the sales order. The discount for each level is determined separately, by applying the same algorithm. `Required` `Default("1")` `Filter(multi eq)` `ORD` `Introduced in version 23.1.2.8`

_Type_: **[DiscountLevel](Crm.Pricing.LineDiscounts.md#discountlevel)**  
_Indexed_: **True**  
_Category_: **System**  
Allowed values for the `DiscountLevel`(Crm.Pricing.LineDiscounts.md#discountlevel) data attribute  
_Allowed Values (Crm.Pricing.LineDiscountsRepository.DiscountLevel Enum Members)_  

| Value | Description |
| ---- | --- |
| One | One value. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'One' |
| Two | Two value. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Three' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Default Value_: **One**  
_Show in UI_: **ShownByDefault**  

### DiscountPercent

The discount percent that should be applied if all the matching criteria are met. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
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

### FromDate

Starting date of validity of the discount. null means no from date restriction. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the current Line Discount is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.2.5`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### MaxQuantity

Apply the discount only if the quantity sold is equal to or less than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MinQuantity

Apply the discount only if the quantity sold is equal to or more than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Priority

The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied. `Required` `Default(3)`

_Type_: **[Priority](Crm.Pricing.LineDiscounts.md#priority)**  
_Category_: **System**  
Generic enum type for Priority properties  
_Allowed Values (General.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Low | Low value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
| Medium | Medium value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Medium' |
| High | High value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **3**  
_Show in UI_: **ShownByDefault**  

### ThruDate

Ending date (inclusive) of validity of the discount. If null, the discount is valid forever. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Campaign

Тhe marketing campaign to which the current definition belongs. `Filter(multi eq)` `Introduced in version 22.1.4.67`

_Type_: **[Campaigns](Crm.Marketing.Campaigns.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Customer

Apply the discount only if this is the customer. `Filter(multi eq)`

_Type_: **[Customers](Crm.Sales.Customers.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CustomerType

Apply the discount only if the customer is of this customer type. `Filter(multi eq)`

_Type_: **[CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DistributionChannel

Apply the discount only when the sales document is on the specified channel. `Filter(multi eq)`

_Type_: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentAmountType

The document amount type that is used as category for this discount. When specified, triggers the recording of the applied discount amount in the Document Distributed Amounts panel in sales orders. `Filter(multi eq)` `Introduced in version 25.1.1.26`

_Type_: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

When not null, the policy is applied only for documents of the specified enterprise company . `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### EnterpriseCompanyLocation

When set, the policy is applied only for documents of the specified enterprise company location. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.EnterpriseCompanyLocation != null) AndAlso ( obj.EnterpriseCompanyLocation.Company != obj.EnterpriseCompany)), null, obj.EnterpriseCompanyLocation.Company)`
### PriceList

Apply the discount only if this price list is used. `Filter(multi eq)`

_Type_: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

Apply the discount only when this specific product is sold. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductGroup

Apply the discount only if the product sold is contained in this product group or any of its sub-groups. `Filter(multi eq)`

_Type_: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TargetGroup

Apply the discount only if the customer is included in this target group. `Filter(multi eq)`

_Type_: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
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

