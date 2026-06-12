---
uid: Crm.Pricing.DocumentAmountTypes
---
# Crm.Pricing.DocumentAmountTypes Entity

**Namespace:** [Crm.Pricing](Crm.Pricing.md)  

Represents the different types of additional amounts which are calculated for the documents. Entity: Gen_Document_Amount_Types

## Renames

Old name: **General.DocumentAmountTypes**  
New name: **Systems.Documents.DocumentAmountTypes**  
Version: **24.1.5.35**  
Case: **35911**  

Old name: **Systems.Documents.DocumentAmountTypes**  
New name: **Crm.Pricing.DocumentAmountTypes**  
Version: **25.1.1.36**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{AmountTypeName:T}_  
Default Search Members:  
_AmountTypeCode; AmountTypeName_  
Code Data Member:  
_AmountTypeCode_  
Name Data Member:  
_AmountTypeName_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.DocumentAmountTypes](Crm.Pricing.DocumentAmountTypes.md)  
  * [Crm.Pricing.DocumentAmountTypeDependencies](Crm.Pricing.DocumentAmountTypeDependencies.md)  
  * [Finance.Intrastat.DocumentAmountTypeSettings](Finance.Intrastat.DocumentAmountTypeSettings.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AddToCustomer](Crm.Pricing.DocumentAmountTypes.md#addtocustomer) | boolean | True means that the amount will be charged to the primary customer of the document. `Required` `Default(true)` 
| [AddToLine](Crm.Pricing.DocumentAmountTypes.md#addtoline) | boolean | True means that the resulting amount will be added to the amount of each respective line. `Required` `Default(true)` 
| [AllowedDirections](Crm.Pricing.DocumentAmountTypes.md#alloweddirections) | [AllowedDirections](Crm.Pricing.DocumentAmountTypes.md#alloweddirections) __nullable__ | Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents. `Default(0)` 
| [AmountInputAllowed](Crm.Pricing.DocumentAmountTypes.md#amountinputallowed) | boolean | True when the user is allowed to input fixed amount for distribution. `Required` `Default(false)` `Filter(eq)` 
| [AmountTypeCode](Crm.Pricing.DocumentAmountTypes.md#amounttypecode) | string (16) | A code that can be used to uniquely identify the additional amount. Can also be used for sorting purposes. `Required` `Filter(multi eq;like)` `ORD` 
| [AmountTypeName](Crm.Pricing.DocumentAmountTypes.md#amounttypename) | [MultilanguageString (128)](../data-types.md#multilanguagestring) | The name of the amount type. `Required` `Filter(like)` 
| [BaseOnLines](Crm.Pricing.DocumentAmountTypes.md#baseonlines) | boolean | True means that the percentages will be applied over lines plus dependant amounts; false means only dependant amounts. `Required` `Default(true)` 
| [DefaultPercent](Crm.Pricing.DocumentAmountTypes.md#defaultpercent) | decimal (7, 6) __nullable__ | Default percent for amounts for which percent input is allowed; null otherwise. 
| [Description](Crm.Pricing.DocumentAmountTypes.md#description) | string (254) __nullable__ | The description of this DocumentAmountType. 
| [DisplayText](Crm.Pricing.DocumentAmountTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DistributeBy](Crm.Pricing.DocumentAmountTypes.md#distributeby) | [DistributeBy](Crm.Pricing.DocumentAmountTypes.md#distributeby) | Specifies how the amount will be distributed among the document lines. Valid values are: ('AMOUNT','MEASUREMENT','PRODUCT DEFINITION','DEAL TYPE','LINE DISCOUNT'). `Required` `Default("AMOUNT")` `Filter(eq)` 
| [Id](Crm.Pricing.DocumentAmountTypes.md#id) | guid |  
| [IsActive](Crm.Pricing.DocumentAmountTypes.md#isactive) | boolean | True when the amount type is active for new records; false - otherwise. `Required` `Default(true)` `Filter(eq)` 
| [ObjectVersion](Crm.Pricing.DocumentAmountTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PercentInputAllowed](Crm.Pricing.DocumentAmountTypes.md#percentinputallowed) | boolean | True when the user is allowed to input percent of total for distribution. `Required` `Default(true)` `Filter(eq)` 
| [RoundScale](Crm.Pricing.DocumentAmountTypes.md#roundscale) | int32 __nullable__ | The amounts should be rounded with the specified number of digits after the decimal point. null means to use the currency default. 
| [UnitAmountInputAllowed](Crm.Pricing.DocumentAmountTypes.md#unitamountinputallowed) | boolean | Specifies whether the user is allowed to input fixed unit amount for the calculation of the amount. `Required` `Default(false)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Crm.Pricing.DocumentAmountTypes.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the user permissions for this DocumentAmountType. Null means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24` |
| [DistributeByMeasurement<br />Category](Crm.Pricing.DocumentAmountTypes.md#distributebymeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) (nullable) | Specifies the measurement category to be used for distribution, when the Distribute_By = 'MEASUREMENT'. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Dependencies | [DocumentAmountTypeDependencies](Crm.Pricing.DocumentAmountTypeDependencies.md) | List of `DocumentAmount<br />TypeDependency`(Crm.Pricing.DocumentAmount<br />TypeDependencies.md) child objects, based on the `Crm.Pricing.DocumentAmount<br />TypeDependency.DocumentAmountType`(Crm.Pricing.DocumentAmount<br />TypeDependencies.md#documentamounttype) back reference 
| Settings | [DocumentAmountTypeSettings](Finance.Intrastat.DocumentAmountTypeSettings.md) | List of `DocumentAmount<br />TypeSetting`(Finance.Intrastat.DocumentAmountTypeSettings.md) child objects, based on the `Finance.Intrastat.DocumentAmountTypeSetting.DocumentAmountType`(Finance.Intrastat.DocumentAmountTypeSettings.md#documentamounttype) back reference 


## Attribute Details

### AddToCustomer

True means that the amount will be charged to the primary customer of the document. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AddToLine

True means that the resulting amount will be added to the amount of each respective line. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AllowedDirections

Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents. `Default(0)`

_Type_: **[AllowedDirections](Crm.Pricing.DocumentAmountTypes.md#alloweddirections) __nullable__**  
_Category_: **System**  
Allowed values for the `AllowedDirections`(Crm.Pricing.DocumentAmountTypes.md#alloweddirections) data attribute  
_Allowed Values (Crm.Pricing.DocumentAmountTypesRepository.AllowedDirections Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as (-1). <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'AllowOnlyNegative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### AmountInputAllowed

True when the user is allowed to input fixed amount for distribution. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### AmountTypeCode

A code that can be used to uniquely identify the additional amount. Can also be used for sorting purposes. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.AmountTypeCode, null, "000")`

### AmountTypeName

The name of the amount type. `Required` `Filter(like)`

_Type_: **[MultilanguageString (128)](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BaseOnLines

True means that the percentages will be applied over lines plus dependant amounts; false means only dependant amounts. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### DefaultPercent

Default percent for amounts for which percent input is allowed; null otherwise.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( Not( obj.PercentInputAllowed), null, obj.DefaultPercent)`
### Description

The description of this DocumentAmountType.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DistributeBy

Specifies how the amount will be distributed among the document lines. Valid values are: ('AMOUNT','MEASUREMENT','PRODUCT DEFINITION','DEAL TYPE','LINE DISCOUNT'). `Required` `Default("AMOUNT")` `Filter(eq)`

_Type_: **[DistributeBy](Crm.Pricing.DocumentAmountTypes.md#distributeby)**  
_Category_: **System**  
Allowed values for the `DistributeBy`(Crm.Pricing.DocumentAmountTypes.md#distributeby) data attribute  
_Allowed Values (Crm.Pricing.DocumentAmountTypesRepository.DistributeBy Enum Members)_  

| Value | Description |
| ---- | --- |
| Amount | Amount value. Stored as 'AMOUNT'. <br /> _Database Value:_ 'AMOUNT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Amount' |
| Measurement | Measurement value. Stored as 'MEASUREMENT'. <br /> _Database Value:_ 'MEASUREMENT' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Measurement' |
| ProductDefinition | ProductDefinition value. Stored as 'PRODUCT DEFINITION'. <br /> _Database Value:_ 'PRODUCT DEFINITION' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ProductDefinition' |
| DealType | DealType value. Stored as 'DEAL TYPE'. <br /> _Database Value:_ 'DEAL TYPE' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'DealType' |
| LineDiscount | LineDiscount value. Stored as 'LINE DISCOUNT'. <br /> _Database Value:_ 'LINE DISCOUNT' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'LineDiscount' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Amount**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

True when the amount type is active for new records; false - otherwise. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PercentInputAllowed

True when the user is allowed to input percent of total for distribution. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### RoundScale

The amounts should be rounded with the specified number of digits after the decimal point. null means to use the currency default.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UnitAmountInputAllowed

Specifies whether the user is allowed to input fixed unit amount for the calculation of the amount. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

The access key, containing the user permissions for this DocumentAmountType. Null means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### DistributeByMeasurementCategory

Specifies the measurement category to be used for distribution, when the Distribute_By = 'MEASUREMENT'. `Filter(multi eq)`

_Type_: **[MeasurementCategories](General.Products.MeasurementCategories.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( Convert( obj.DistributeBy, Int32) != 1), null, obj.DistributeByMeasurementCategory)`

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


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.DocumentAmountTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.DocumentAmountTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Pricing_DocumentAmountTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Pricing_DocumentAmountTypes?$top=10>

