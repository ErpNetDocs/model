---
uid: Systems.Documents.DocumentAmountTypes
---
# Systems.Documents.DocumentAmountTypes Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Represents the different types of additional amounts which are calculated for the documents. Entity: Gen_Document_Amount_Types

## Renames

Old name: **General.DocumentAmountTypes**  
New name: **Systems.Documents.DocumentAmountTypes**  
Version: **24.1.5.35**  
Case: **35911**  



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
API access:  _ReadWrite_  
Layout category attribute:  _DistributeBy_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Documents.DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)  
  * [Regulatory.Intrastat.DocumentAmountTypeSettings](Regulatory.Intrastat.DocumentAmountTypeSettings.md)  
  * [Systems.Documents.DocumentAmountTypeDependencies](Systems.Documents.DocumentAmountTypeDependencies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AddToCustomer](Systems.Documents.DocumentAmountTypes.md#addtocustomer) | boolean | True means that the amount will be charged to the primary customer of the document. `Required` `Default(true)` 
| [AddToLine](Systems.Documents.DocumentAmountTypes.md#addtoline) | boolean | True means that the resulting amount will be added to the amount of each respective line. `Required` `Default(true)` 
| [AggregateLastUpdateTimeUtc](Systems.Documents.DocumentAmountTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) | [AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) __nullable__ | Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents. `Default(0)` 
| [AmountInputAllowed](Systems.Documents.DocumentAmountTypes.md#amountinputallowed) | boolean | True when the user is allowed to input fixed amount for distribution. `Required` `Default(false)` `Filter(eq)` 
| [AmountTypeCode](Systems.Documents.DocumentAmountTypes.md#amounttypecode) | string (16) | A code that can be used to uniquely identify the additional amount. Can also be used for sorting purposes. `Required` `Filter(multi eq;like)` `ORD` 
| [AmountTypeName](Systems.Documents.DocumentAmountTypes.md#amounttypename) | [MultilanguageString (128)](../data-types.md#multilanguagestring) | The name of the amount type. `Required` `Filter(like)` 
| [BaseOnLines](Systems.Documents.DocumentAmountTypes.md#baseonlines) | boolean | True means that the percentages will be applied over lines plus dependant amounts; false means only dependant amounts. `Required` `Default(true)` 
| [DefaultPercent](Systems.Documents.DocumentAmountTypes.md#defaultpercent) | decimal (7, 6) __nullable__ | Default percent for amounts for which percent input is allowed; null otherwise. 
| [Description](Systems.Documents.DocumentAmountTypes.md#description) | string (254) __nullable__ | The description of this DocumentAmountType. 
| [DisplayText](Systems.Documents.DocumentAmountTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby) | [DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby) | Determines how the amount will be distributed among the document lines. `Required` `Default("AMOUNT")` `Filter(eq)` 
| [ExternalId](Systems.Documents.DocumentAmountTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Documents.DocumentAmountTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Documents.DocumentAmountTypes.md#id) | guid |  
| [IsActive](Systems.Documents.DocumentAmountTypes.md#isactive) | boolean | True when the amount type is active for new records; false - otherwise. `Required` `Default(true)` `Filter(eq)` 
| [ObjectVersion](Systems.Documents.DocumentAmountTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PercentInputAllowed](Systems.Documents.DocumentAmountTypes.md#percentinputallowed) | boolean | True when the user is allowed to input percent of total for distribution. `Required` `Default(true)` `Filter(eq)` 
| [RoundScale](Systems.Documents.DocumentAmountTypes.md#roundscale) | int32 __nullable__ | The amounts should be rounded with the specified number of digits after the decimal point. null means to use the currency default. 
| [UnitAmountInputAllowed](Systems.Documents.DocumentAmountTypes.md#unitamountinputallowed) | boolean | Specifies whether the user is allowed to input fixed unit amount for the calculation of the amount. `Required` `Default(false)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Documents.DocumentAmountTypes.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this DocumentAmountType. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24` |
| [DistributeByMeasurement<br />Category](Systems.Documents.DocumentAmountTypes.md#distributebymeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) (nullable) | Specifies the measurement category to be used for distribution, when the Distribute_By = 'MEASUREMENT'. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Dependencies | [DocumentAmountTypeDependencies](Systems.Documents.DocumentAmountTypeDependencies.md) | List of `DocumentAmount<br />TypeDependency`(Systems.Documents.DocumentAmount<br />TypeDependencies.md) child objects, based on the `Systems.Documents.DocumentAmount<br />TypeDependency.DocumentAmountType`(Systems.Documents.DocumentAmount<br />TypeDependencies.md#documentamounttype) back reference 
| Settings | [DocumentAmountTypeSettings](Regulatory.Intrastat.DocumentAmountTypeSettings.md) | List of `DocumentAmount<br />TypeSetting`(Regulatory.Intrastat.DocumentAmountTypeSettings.md) child objects, based on the `Regulatory.Intrastat.DocumentAmountTypeSetting.DocumentAmountType`(Regulatory.Intrastat.DocumentAmountTypeSettings.md#documentamounttype) back reference 


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

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### AllowedDirections

Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents. `Default(0)`

_Type_: **[AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) __nullable__**  
_Category_: **System**  
Allowed values for the `AllowedDirections`(Systems.Documents.DocumentAmountTypes.md#alloweddirections) data attribute  
_Allowed Values (Systems.Documents.DocumentAmountTypesRepository.AllowedDirections Enum Members)_  

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

Determines how the amount will be distributed among the document lines. `Required` `Default("AMOUNT")` `Filter(eq)`

_Type_: **[DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby)**  
_Category_: **System**  
Allowed values for the `DistributeBy`(Systems.Documents.DocumentAmountTypes.md#distributeby) data attribute  
_Allowed Values (Systems.Documents.DocumentAmountTypesRepository.DistributeBy Enum Members)_  

| Value | Description |
| ---- | --- |
| Amount | Amount value. Stored as 'AMOUNT'. <br /> _Database Value:_ 'AMOUNT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Amount' |
| Measurement | Measurement value. Stored as 'MEASUREMENT'. <br /> _Database Value:_ 'MEASUREMENT' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Measurement' |
| ProductDefinition | ProductDefinition value. Stored as 'PRODUCT DEFINITION'. <br /> _Database Value:_ 'PRODUCT DEFINITION' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ProductDefinition' |
| DealType | DealType value. Stored as 'DEAL TYPE'. <br /> _Database Value:_ 'DEAL TYPE' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'DealType' |
| LineDiscount | Distributes the amount of the applied line discounts from this category to the corresponding line.. Stored as 'LINE DISCOUNT'. <br /> _Database Value:_ 'LINE DISCOUNT' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'LineDiscount' |
| BonusProgram | Distributes the discount amount of the bonus programs from this category to the corresponding line.. Stored as 'BONUS PROGRAM'. <br /> _Database Value:_ 'BONUS PROGRAM' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'BonusProgram' |
| PromotionalPackage | Distributes the discount amount of the promotional package from this category to the corresponding line.. Stored as 'PROMOTIONAL PACKAGE'. <br /> _Database Value:_ 'PROMOTIONAL PACKAGE' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'PromotionalPackage' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Amount**  
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

The access key, containing the permissions for this DocumentAmountType. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24`

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

[!list limit=1000 erp.entity=Systems.Documents.DocumentAmountTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentAmountTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentAmountTypes

Domain API Entity Type: 
Systems_Documents_DocumentAmountType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentAmountTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentAmountTypes?$top=10>

