---
uid: Systems.Documents.DocumentAmountTypes
---
# Systems.Documents.DocumentAmountTypes


Represents the different types of additional amounts which are calculated for the documents.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DocumentAmountTypes  
Base Table: Gen_Document_Amount_Types  
API access:  ReadWrite  

## Renames

Old name: General.DocumentAmountTypes  
New name: Systems.Documents.DocumentAmountTypes  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {AmountTypeName:T}  
Search Members: AmountTypeCode; AmountTypeName  
Code Member: AmountTypeCode  
Name Member: AmountTypeName  
Category:  Settings  
Show in UI:  ShownByDefault  
Layout category By:  DistributeBy  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Documents.DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)  
  * [Regulatory.Intrastat.DocumentAmountTypeSettings](Regulatory.Intrastat.DocumentAmountTypeSettings.md)  
  * [Systems.Documents.DocumentAmountTypeDependencies](Systems.Documents.DocumentAmountTypeDependencies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AddToCustomer](Systems.Documents.DocumentAmountTypes.md#addtocustomer) | boolean | 1 means that the amount will be charged to the primary customer of the document 
| [AddToLine](Systems.Documents.DocumentAmountTypes.md#addtoline) | boolean | 1 means that the resulting amount will be added to the amount of each respective line 
| [AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) | [AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) __nullable__ | Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents. 
| [AmountInputAllowed](Systems.Documents.DocumentAmountTypes.md#amountinputallowed) | boolean | 1 when the user is allowed to input fixed amount for distribution 
| [AmountTypeCode](Systems.Documents.DocumentAmountTypes.md#amounttypecode) | string (16) | A code that can be used to uniquely identify the additional amount. Can also be used for sorting purposes 
| [AmountTypeName](Systems.Documents.DocumentAmountTypes.md#amounttypename) | [MultilanguageString (128)](../data-types.md#multilanguagestring) | The name of the amount type. 
| [BaseOnLines](Systems.Documents.DocumentAmountTypes.md#baseonlines) | boolean | 1 means that the percentages will be applied over lines plus dependant amounts; 0 means only dependant amounts 
| [DefaultPercent](Systems.Documents.DocumentAmountTypes.md#defaultpercent) | decimal (7, 6) __nullable__ | Default percent for amounts for which percent input is allowed; NULL otherwise 
| [Description](Systems.Documents.DocumentAmountTypes.md#description) | string (254) __nullable__ | The description of this DocumentAmountType. 
| [DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby) | [DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby) | Determines how the amount will be distributed among the document lines. 
| [IsActive](Systems.Documents.DocumentAmountTypes.md#isactive) | boolean | 1 when the amount type is active for new records; 0 - otherwise 
| [PercentInputAllowed](Systems.Documents.DocumentAmountTypes.md#percentinputallowed) | boolean | 1 when the user is allowed to input percent of total for distribution 
| [RoundScale](Systems.Documents.DocumentAmountTypes.md#roundscale) | int32 __nullable__ | The amounts should be rounded with the specified number of digits after the decimal point. NULL means to use the currency default 
| [UnitAmountInputAllowed](Systems.Documents.DocumentAmountTypes.md#unitamountinputallowed) | boolean | Specifies whether the user is allowed to input fixed unit amount for the calculation of the amount. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Documents.DocumentAmountTypes.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this DocumentAmountType. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24` |
| [DistributeByMeasurement<br />Category](Systems.Documents.DocumentAmountTypes.md#distributebymeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) (nullable) | Specifies the measurement category to be used for distribution, when the Distribute_By = 'MEASUREMENT' |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DocumentAmountTypes.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentAmountTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Documents.DocumentAmountTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Documents.DocumentAmountTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Documents.DocumentAmountTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Documents.DocumentAmountTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Dependencies | [DocumentAmountTypeDependencies](Systems.Documents.DocumentAmountTypeDependencies.md) | List of `DocumentAmount<br />TypeDependency`(Systems.Documents.DocumentAmount<br />TypeDependencies.md) child objects, based on the `Systems.Documents.DocumentAmount<br />TypeDependency.DocumentAmountType`(Systems.Documents.DocumentAmount<br />TypeDependencies.md#documentamounttype) back reference 
| Settings | [DocumentAmountTypeSettings](Regulatory.Intrastat.DocumentAmountTypeSettings.md) | List of `DocumentAmount<br />TypeSetting`(Regulatory.Intrastat.DocumentAmountTypeSettings.md) child objects, based on the `Regulatory.Intrastat.DocumentAmountTypeSetting.DocumentAmountType`(Regulatory.Intrastat.DocumentAmountTypeSettings.md#documentamounttype) back reference 


## Attribute Details

### AddToCustomer

1 means that the amount will be charged to the primary customer of the document

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AddToLine

1 means that the resulting amount will be added to the amount of each respective line

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AllowedDirections

Specifies condition for the sign of the allowed values for input percent or amount ​​that can be set in the documents.

Type: **[AllowedDirections](Systems.Documents.DocumentAmountTypes.md#alloweddirections) __nullable__**  
Category: **System**  
Allowed values for the `AllowedDirections`(Systems.Documents.DocumentAmountTypes.md#alloweddirections) data attribute  
Allowed Values (Systems.Documents.DocumentAmountTypesRepository.AllowedDirections Enum Members)  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as (-1). <br /> Database Value: -1 <br /> Model Value: -1 <br /> Domain API Value: 'AllowOnlyNegative' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### AmountInputAllowed

1 when the user is allowed to input fixed amount for distribution

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AmountTypeCode

A code that can be used to uniquely identify the additional amount. Can also be used for sorting purposes

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.AmountTypeCode, null, "000")`

### AmountTypeName

The name of the amount type.

Type: **[MultilanguageString (128)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BaseOnLines

1 means that the percentages will be applied over lines plus dependant amounts; 0 means only dependant amounts

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### DefaultPercent

Default percent for amounts for which percent input is allowed; NULL otherwise

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( Not( obj.PercentInputAllowed), null, obj.DefaultPercent)`
### Description

The description of this DocumentAmountType.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### DistributeBy

Determines how the amount will be distributed among the document lines.

Type: **[DistributeBy](Systems.Documents.DocumentAmountTypes.md#distributeby)**  
Category: **System**  
Allowed values for the `DistributeBy`(Systems.Documents.DocumentAmountTypes.md#distributeby) data attribute  
Allowed Values (Systems.Documents.DocumentAmountTypesRepository.DistributeBy Enum Members)  

| Value | Description |
| ---- | --- |
| Amount | Amount value. Stored as 'AMOUNT'. <br /> Database Value: 'AMOUNT' <br /> Model Value: 0 <br /> Domain API Value: 'Amount' |
| Measurement | Measurement value. Stored as 'MEASUREMENT'. <br /> Database Value: 'MEASUREMENT' <br /> Model Value: 1 <br /> Domain API Value: 'Measurement' |
| ProductDefinition | ProductDefinition value. Stored as 'PRODUCT DEFINITION'. <br /> Database Value: 'PRODUCT DEFINITION' <br /> Model Value: 2 <br /> Domain API Value: 'ProductDefinition' |
| DealType | DealType value. Stored as 'DEAL TYPE'. <br /> Database Value: 'DEAL TYPE' <br /> Model Value: 3 <br /> Domain API Value: 'DealType' |
| LineDiscount | Distributes the amount of the applied line discounts from this category to the corresponding line.. Stored as 'LINE DISCOUNT'. <br /> Database Value: 'LINE DISCOUNT' <br /> Model Value: 4 <br /> Domain API Value: 'LineDiscount' |
| BonusProgram | Distributes the discount amount of the bonus programs from this category to the corresponding line.. Stored as 'BONUS PROGRAM'. <br /> Database Value: 'BONUS PROGRAM' <br /> Model Value: 5 <br /> Domain API Value: 'BonusProgram' |
| PromotionalPackage | Distributes the discount amount of the promotional package from this category to the corresponding line.. Stored as 'PROMOTIONAL PACKAGE'. <br /> Database Value: 'PROMOTIONAL PACKAGE' <br /> Model Value: 6 <br /> Domain API Value: 'PromotionalPackage' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Amount**  
Show in UI: **ShownByDefault**  

### IsActive

1 when the amount type is active for new records; 0 - otherwise

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### PercentInputAllowed

1 when the user is allowed to input percent of total for distribution

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### RoundScale

The amounts should be rounded with the specified number of digits after the decimal point. NULL means to use the currency default

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UnitAmountInputAllowed

Specifies whether the user is allowed to input fixed unit amount for the calculation of the amount.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
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

### AccessKey

The access key, containing the permissions for this DocumentAmountType. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.1.24`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### DistributeByMeasurementCategory

Specifies the measurement category to be used for distribution, when the Distribute_By = 'MEASUREMENT'

Type: **[MeasurementCategories](General.Products.MeasurementCategories.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( Convert( obj.DistributeBy, Int32) != 1), null, obj.DistributeByMeasurementCategory)`

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

