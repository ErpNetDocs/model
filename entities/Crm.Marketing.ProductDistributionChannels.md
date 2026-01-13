---
uid: Crm.Marketing.ProductDistributionChannels
---
# Crm.Marketing.ProductDistributionChannels Entity

**Namespace:** [Crm.Marketing](Crm.Marketing.md)  

Channel assignments (listing) for products. Entity: Crm_Product_Distribution_Channels

## Default Visualization
Default Display Text Format:  
_{Product.Name:T}_  
Default Search Members:  
_Product.Name_  
Name Data Member:  
_Product.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Crm.Marketing.ProductDistributionChannels.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](Crm.Marketing.ProductDistributionChannels.md#fromdate) | date __nullable__ | When the product was listed. null-the product was not yet listed. The data is for informational purposes only and does not affect the listing status of the product (Is_Active does). `Default(Today)` `Filter(ge;le)` 
| [Id](Crm.Marketing.ProductDistributionChannels.md#id) | guid |  
| [IsActive](Crm.Marketing.ProductDistributionChannels.md#isactive) | boolean | Is this product listing active? true=Yes, false=No. `Required` `Default(true)` `Filter(eq)` 
| [MinimalSalesPricePerLot](Crm.Marketing.ProductDistributionChannels.md#minimalsalespriceperlot) | [Amount (18, 4)](../data-types.md#amount) __nullable__ | Minimal allowed price for sales of this product through this channel. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. null means that there is no minimal sales price enforcement. `Currency: Product.CostingCurrency` 
| [MinimalSalesQuantityBase](Crm.Marketing.ProductDistributionChannels.md#minimalsalesquantitybase) | decimal (18, 3) __nullable__ | Minimal base quantity of the current product that has to be specified in any sale for this distribution channel. 
| [ObjectVersion](Crm.Marketing.ProductDistributionChannels.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ToDate](Crm.Marketing.ProductDistributionChannels.md#todate) | date __nullable__ | When the product was de-listed. null=unknown or the product was not de-listed. The data is for informational purposes only and does not affect the listing status of the product (Is_Active does). `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DistributionChannel](Crm.Marketing.ProductDistributionChannels.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) | The distribution channel in which the product is listed. `Required` `Filter(multi eq)` |
| [Product](Crm.Marketing.ProductDistributionChannels.md#product) | [Products](General.Products.Products.md) | The listed product. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

When the product was listed. null-the product was not yet listed. The data is for informational purposes only and does not affect the listing status of the product (Is_Active does). `Default(Today)` `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Is this product listing active? true=Yes, false=No. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### MinimalSalesPricePerLot

Minimal allowed price for sales of this product through this channel. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. null means that there is no minimal sales price enforcement. `Currency: Product.CostingCurrency`

_Type_: **[Amount (18, 4)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MinimalSalesQuantityBase

Minimal base quantity of the current product that has to be specified in any sale for this distribution channel.

_Type_: **decimal (18, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ToDate

When the product was de-listed. null=unknown or the product was not de-listed. The data is for informational purposes only and does not affect the listing status of the product (Is_Active does). `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DistributionChannel

The distribution channel in which the product is listed. `Required` `Filter(multi eq)`

_Type_: **[DistributionChannels](Crm.Marketing.DistributionChannels.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The listed product. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

[!list limit=1000 erp.entity=Crm.Marketing.ProductDistributionChannels erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.ProductDistributionChannels erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Marketing_ProductDistributionChannels

Domain API Entity Type: 
Crm_Marketing_ProductDistributionChannel

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Marketing_ProductDistributionChannels?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Marketing_ProductDistributionChannels?$top=10>

