---
uid: General.DocumentTypeAmounts
---
# General.DocumentTypeAmounts Entity

**Namespace:** [General](General.md)  

Specifies amount types, that should be automatically added to documents of a given type. Entity: Gen_Document_Type_Amounts
## Renamed
**New name:** [Systems.Documents.DocumentTypeAmounts](Systems.Documents.DocumentTypeAmounts.md)  



## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.DocumentTypes](General.DocumentTypes.md)  
Aggregate Root:  
[General.DocumentTypes](General.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultPercent](General.DocumentTypeAmounts.md#defaultpercent) | decimal (7, 6) __nullable__ | Default input percent. Valid only for amount types, supporting percent and takes precedence over Default_Percent in the definition of the amount type. 
| [DisplayText](General.DocumentTypeAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.DocumentTypeAmounts.md#id) | guid |  
| [ObjectVersion](General.DocumentTypeAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RequiredFromDate](General.DocumentTypeAmounts.md#requiredfromdate) | date __nullable__ | When not null, specifies a date, after which the amount becomes required for the current document type. The date is compared against the document date. `Filter(ge;le)` 
| [RequiredThruDate](General.DocumentTypeAmounts.md#requiredthrudate) | date __nullable__ | When not null, specifies a date, up to which the amount is required for the current document type. The date is compared against the document date. `Filter(ge;le)` 
| [UserCanChangeInput](General.DocumentTypeAmounts.md#usercanchangeinput) | boolean | True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentAmountType](General.DocumentTypeAmounts.md#documentamounttype) | [DocumentAmountTypes](General.DocumentAmountTypes.md) | The amount type that should be automatically added to the documents of the specified type. `Required` `Filter(multi eq)` |
| [DocumentType](General.DocumentTypeAmounts.md#documenttype) | [DocumentTypes](General.DocumentTypes.md) | The document type for which the amount type is specified. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DefaultPercent

Default input percent. Valid only for amount types, supporting percent and takes precedence over Default_Percent in the definition of the amount type.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RequiredFromDate

When not null, specifies a date, after which the amount becomes required for the current document type. The date is compared against the document date. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RequiredThruDate

When not null, specifies a date, up to which the amount is required for the current document type. The date is compared against the document date. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UserCanChangeInput

True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentAmountType

The amount type that should be automatically added to the documents of the specified type. `Required` `Filter(multi eq)`

_Type_: **[DocumentAmountTypes](General.DocumentAmountTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

The document type for which the amount type is specified. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](General.DocumentTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=General.DocumentTypeAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.DocumentTypeAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_DocumentTypeAmounts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_DocumentTypeAmounts?$top=10>

