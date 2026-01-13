---
uid: Systems.Bpm.CustomProperties
---
# Systems.Bpm.CustomProperties Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

User-defined properties, which can supplement the system properties of almost all entities in the system. Entity: Gen_Properties

## Renames

Old name: **General.CustomProperties**  
New name: **Systems.Bpm.CustomProperties**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _4 - Track object attribute and blob changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  
  * [Systems.Bpm.CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md)  
  * [Systems.Bpm.PropertyEnterpriseCompanyFilters](Systems.Bpm.PropertyEnterpriseCompanyFilters.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowedValuesEntityName](Systems.Bpm.CustomProperties.md#allowedvaluesentityname) | string (64) __nullable__ | When not null, specifies that the allowed values are retrieved from the specified entity. `Filter(eq)` 
| [AllowedValuesFilterXML](Systems.Bpm.CustomProperties.md#allowedvaluesfilterxml) | dataaccessfilter __nullable__ | When not null specifies the filter to apply when extracting allowed values from entity. `Unit: obj.AllowedValuesEntityName` 
| [Code](Systems.Bpm.CustomProperties.md#code) | string (40) | Unique property code. `Required` `Filter(multi eq;like)` `ORD` 
| [DisplayText](Systems.Bpm.CustomProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityName](Systems.Bpm.CustomProperties.md#entityname) | string (64) | The entity for which the property is applicable. `Required` `Filter(eq)` `ORD` 
| [ExternalId](Systems.Bpm.CustomProperties.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Bpm.CustomProperties.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Hint](Systems.Bpm.CustomProperties.md#hint) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The hint, which is displayed alongside the property. `Filter(multi eq;like)` `Introduced in version 20.1` 
| [Id](Systems.Bpm.CustomProperties.md#id) | guid |  
| [IsActive](Systems.Bpm.CustomProperties.md#isactive) | boolean | Indicates whether this custom property is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.3.19` 
| [KeyOrder](Systems.Bpm.CustomProperties.md#keyorder) | byte __nullable__ | When not null, indicates, that the property is a key property and contains the property consequtive position withing the entity. Used for BI and other analysis. 
| [LimitToAllowedValues](Systems.Bpm.CustomProperties.md#limittoallowedvalues) | boolean | When true, allows the property to be set only to allowed value. When false, the property can have any value. `Required` `Default(false)` `Filter(eq)` 
| [MaskLength](Systems.Bpm.CustomProperties.md#masklength) | int16 __nullable__ | Limits te length of the property value to the specified number of characters. Null means no limitation. 
| [Name](Systems.Bpm.CustomProperties.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this CustomProperty. `Required` `Filter(like)` 
| [Notes](Systems.Bpm.CustomProperties.md#notes) | string (max) __nullable__ | Notes for this CustomProperty. `Introduced in version 20.1` 
| [ObjectVersion](Systems.Bpm.CustomProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PropertyType](Systems.Bpm.CustomProperties.md#propertytype) | [PropertyType](Systems.Bpm.CustomProperties.md#propertytype) | Type of property values. 'T' - text; 'P' - picture; 'N' - number; 'D' - date. `Required` `Default("T")` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowedValuesParent<br />Property](Systems.Bpm.CustomProperties.md#allowedvaluesparentproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Specifies the user defined property, which is used for filtering the allowed values by value of the parent property. `Filter(multi eq)` |
| [AllowedValuesProperty](Systems.Bpm.CustomProperties.md#allowedvaluesproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not null, specifies that the current property can have the same allowed values as the specified property. Also, this makes the current and the specified property copy-compatible. `Filter(multi eq)` |
| [PropertiesCategory](Systems.Bpm.CustomProperties.md#propertiescategory) | [PropertiesCategories](Systems.Bpm.PropertiesCategories.md) (nullable) | When not null, categorizes the property under a category. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AllowedValues | [CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) | List of `CustomProperty<br />AllowedValue`(Systems.Bpm.CustomProperty<br />AllowedValues.md) child objects, based on the `Systems.Bpm.CustomPropertyAllowedValue.Property`(Systems.Bpm.CustomProperty<br />AllowedValues.md#property) back reference 
| EnterpriseCompanyFilters | [PropertyEnterpriseCompanyFilters](Systems.Bpm.PropertyEnterpriseCompanyFilters.md) | List of `PropertyEnterprise<br />CompanyFilter`(Systems.Bpm.PropertyEnterprise<br />CompanyFilters.md) child objects, based on the `Systems.Bpm.PropertyEnterprise<br />CompanyFilter.Property`(Systems.Bpm.PropertyEnterprise<br />CompanyFilters.md#property) back reference 


## Attribute Details

### AllowedValuesEntityName

When not null, specifies that the allowed values are retrieved from the specified entity. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### AllowedValuesFilterXML

When not null specifies the filter to apply when extracting allowed values from entity. `Unit: obj.AllowedValuesEntityName`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Code

Unique property code. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (40)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.Code, null, "00000")`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityName

The entity for which the property is applicable. `Required` `Filter(eq)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
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

### Hint

The hint, which is displayed alongside the property. `Filter(multi eq;like)` `Introduced in version 20.1`

_Type_: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
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

Indicates whether this custom property is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.3.19`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### KeyOrder

When not null, indicates, that the property is a key property and contains the property consequtive position withing the entity. Used for BI and other analysis.

_Type_: **byte __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LimitToAllowedValues

When true, allows the property to be set only to allowed value. When false, the property can have any value. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### MaskLength

Limits te length of the property value to the specified number of characters. Null means no limitation.

_Type_: **int16 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this CustomProperty. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this CustomProperty. `Introduced in version 20.1`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### PropertyType

Type of property values. 'T' - text; 'P' - picture; 'N' - number; 'D' - date. `Required` `Default("T")`

_Type_: **[PropertyType](Systems.Bpm.CustomProperties.md#propertytype)**  
_Category_: **System**  
Allowed values for the `PropertyType`(Systems.Bpm.CustomProperties.md#propertytype) data attribute  
_Allowed Values (Systems.Bpm.CustomPropertiesRepository.PropertyType Enum Members)_  

| Value | Description |
| ---- | --- |
| Text | Text value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Text' |
| Number | Number value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Number' |
| Picture | Picture value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Picture' |
| Date | Date value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Date' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Text**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AllowedValuesParentProperty

Specifies the user defined property, which is used for filtering the allowed values by value of the parent property. `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AllowedValuesProperty

When not null, specifies that the current property can have the same allowed values as the specified property. Also, this makes the current and the specified property copy-compatible. `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PropertiesCategory

When not null, categorizes the property under a category. `Filter(multi eq)`

_Type_: **[PropertiesCategories](Systems.Bpm.PropertiesCategories.md) (nullable)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Systems.Bpm.CustomProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.CustomProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_CustomProperties

Domain API Entity Type: 
Systems_Bpm_CustomProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_CustomProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_CustomProperties?$top=10>

