---
uid: Finance.Saft.ProfileAccountByProducts
---
# Finance.Saft.ProfileAccountByProducts Entity

**Namespace:** [Finance.Saft](Finance.Saft.md)  

Maps the SAF-T account by product type for a selected SAF-T profile. Entity: Saft_Profile_Account_By_Products (Introduced in version 26.2.0.73)

## Default Visualization
Default Display Text Format:  
_{Profile.Name}_  
Default Search Members:  
_Profile.Name_  
Name Data Member:  
_Profile.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  
Aggregate Root:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DebitCreditIndicator](Finance.Saft.ProfileAccountByProducts.md#debitcreditindicator) | [DebitCreditIndicator](Finance.Saft.ProfileAccountByProducts.md#debitcreditindicator) | Debit/credit indicator for SAF-T invoice lines. `Required` `Default("D")` `Filter(eq)` `Introduced in version 26.2.1.9` 
| [DisplayText](Finance.Saft.ProfileAccountByProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityKind](Finance.Saft.ProfileAccountByProducts.md#entitykind) | [EntityKind](Finance.Saft.ProfileAccountByProducts.md#entitykind) | Specifies whether the product type to SAF-T account mapping applies to sales invoices or purchase invoices. `Required` `Default("S")` `Filter(eq)` `Introduced in version 26.2.1.9` 
| [Id](Finance.Saft.ProfileAccountByProducts.md#id) | guid |  
| [Notes](Finance.Saft.ProfileAccountByProducts.md#notes) | string (max) __nullable__ | Additional information or comments about the mapping. `Filter(like)` 
| [ObjectVersion](Finance.Saft.ProfileAccountByProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountCodeEntry](Finance.Saft.ProfileAccountByProducts.md#accountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T account used during SAF-T generation for the selected product type. `Required` `Filter(multi eq)` |
| [DocumentType](Finance.Saft.ProfileAccountByProducts.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The ERP.net document type under which this mapping rule should be applied. `Filter(multi eq)` |
| [ProductType](Finance.Saft.ProfileAccountByProducts.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The ERP.net product type for which the SAF-T account is defined. `Required` `Filter(multi eq)` |
| [Profile](Finance.Saft.ProfileAccountByProducts.md#profile) | [Profiles](Finance.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DebitCreditIndicator

Debit/credit indicator for SAF-T invoice lines. `Required` `Default("D")` `Filter(eq)` `Introduced in version 26.2.1.9`

_Type_: **[DebitCreditIndicator](Finance.Saft.ProfileAccountByProducts.md#debitcreditindicator)**  
_Category_: **System**  
Allowed values for the `DebitCreditIndicator`(Finance.Saft.ProfileAccountByProducts.md#debitcreditindicator) data attribute  
_Allowed Values (Finance.Saft.ProfileAccountByProductsRepository.DebitCreditIndicator Enum Members)_  

| Value | Description |
| ---- | --- |
| Debit | Debit value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Debit' |
| Credit | Credit value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Credit' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Debit**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityKind

Specifies whether the product type to SAF-T account mapping applies to sales invoices or purchase invoices. `Required` `Default("S")` `Filter(eq)` `Introduced in version 26.2.1.9`

_Type_: **[EntityKind](Finance.Saft.ProfileAccountByProducts.md#entitykind)**  
_Category_: **System**  
Allowed values for the `EntityKind`(Finance.Saft.ProfileAccountByProducts.md#entitykind) data attribute  
_Allowed Values (Finance.Saft.ProfileAccountByProductsRepository.EntityKind Enum Members)_  

| Value | Description |
| ---- | --- |
| Sales | Sales value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Sales' |
| Purchases | Purchases value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Purchases' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Sales**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Additional information or comments about the mapping. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### AccountCodeEntry

The SAF-T account used during SAF-T generation for the selected product type. `Required` `Filter(multi eq)`

_Type_: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

The ERP.net document type under which this mapping rule should be applied. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductType

The ERP.net product type for which the SAF-T account is defined. `Required` `Filter(multi eq)`

_Type_: **[ProductTypes](General.Products.ProductTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Profile

The SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Profiles](Finance.Saft.Profiles.md)**  
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

[!list limit=1000 erp.entity=Finance.Saft.ProfileAccountByProducts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Saft.ProfileAccountByProducts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Saft_ProfileAccountByProducts

Domain API Entity Type: 
Finance_Saft_ProfileAccountByProduct

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Saft_ProfileAccountByProducts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Saft_ProfileAccountByProducts?$top=10>

