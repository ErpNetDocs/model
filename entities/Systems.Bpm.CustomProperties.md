---
uid: Systems.Bpm.CustomProperties
---
# Systems.Bpm.CustomProperties


Stored attributes allow the users to extend the data model for their specific needs. They persist a value for each record in the database.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.CustomProperties  
Base Table: Gen_Properties  
API access:  ReadWrite  

## Renames

Old name: General.CustomProperties  
New name: Systems.Bpm.CustomProperties  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  4 - Track object attribute and blob changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  
  * [Systems.Bpm.CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md)  
  * [Systems.Bpm.PropertyEnterpriseCompanyFilters](Systems.Bpm.PropertyEnterpriseCompanyFilters.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowedValuesEntityName](Systems.Bpm.CustomProperties.md#allowedvaluesentityname) | string (64) __nullable__ | When not NULL, specifies that the allowed values are retrieved from the specified entity`Filter(eq)` 
| [AllowedValuesFilterXML](Systems.Bpm.CustomProperties.md#allowedvaluesfilterxml) | dataaccessfilter __nullable__ | When not NULL specifies the filter to apply when extracting allowed values from entity`Unit: obj.AllowedValuesEntityName` 
| [Code](Systems.Bpm.CustomProperties.md#code) | string (40) | Unique property code.`Required` `Filter(multi eq;like)` `ORD` 
| [EntityName](Systems.Bpm.CustomProperties.md#entityname) | string (64) | The entity for which the property is applicable.`Required` `Filter(eq)` `ORD` 
| [Hint](Systems.Bpm.CustomProperties.md#hint) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The hint, which is displayed alongside the property.`Filter(multi eq;like)` `Introduced in version 20.1` 
| [IsActive](Systems.Bpm.CustomProperties.md#isactive) | boolean | Indicates whether this custom property is active`Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.3.19` 
| [KeyOrder](Systems.Bpm.CustomProperties.md#keyorder) | byte __nullable__ | When not null, indicates, that the property is a key property and contains the property consequtive position withing the entity. Used for BI and other analysis 
| [LimitToAllowedValues](Systems.Bpm.CustomProperties.md#limittoallowedvalues) | boolean | When true, allows the property to be set only to allowed value. When false, the property can have any value.`Required` `Default(false)` `Filter(eq)` 
| [MaskLength](Systems.Bpm.CustomProperties.md#masklength) | int16 __nullable__ | Limits te length of the property value to the specified number of characters. Null means no limitation 
| [Name](Systems.Bpm.CustomProperties.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this CustomProperty. `Required` `Filter(like)` 
| [Notes](Systems.Bpm.CustomProperties.md#notes) | string (max) __nullable__ | Notes for this CustomProperty. `Introduced in version 20.1` 
| [PropertyType](Systems.Bpm.CustomProperties.md#propertytype) | [PropertyType](Systems.Bpm.CustomProperties.md#propertytype) | Type of property values. 'T' - text; 'P' - picture; 'N' - number; 'D' - date.`Required` `Default(&quot;T&quot;)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowedValuesParent<br />Property](Systems.Bpm.CustomProperties.md#allowedvaluesparentproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Specifies the user defined property, which is used for filtering the allowed values by value of the parent property |
| [AllowedValuesProperty](Systems.Bpm.CustomProperties.md#allowedvaluesproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not null, specifies that the current property can have the same allowed values as the specified property. Also, this makes the current and the specified property copy-compatible. |
| [PropertiesCategory](Systems.Bpm.CustomProperties.md#propertiescategory) | [PropertiesCategories](Systems.Bpm.PropertiesCategories.md) (nullable) | When not null, categorizes the property under a category. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.CustomProperties.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.CustomProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Bpm.CustomProperties.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Bpm.CustomProperties.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Bpm.CustomProperties.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Bpm.CustomProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AllowedValues | [CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) | List of `CustomProperty<br />AllowedValue`(Systems.Bpm.CustomProperty<br />AllowedValues.md) child objects, based on the `Systems.Bpm.CustomPropertyAllowedValue.Property`(Systems.Bpm.CustomProperty<br />AllowedValues.md#property) back reference 
| EnterpriseCompanyFilters | [PropertyEnterpriseCompanyFilters](Systems.Bpm.PropertyEnterpriseCompanyFilters.md) | List of `PropertyEnterprise<br />CompanyFilter`(Systems.Bpm.PropertyEnterprise<br />CompanyFilters.md) child objects, based on the `Systems.Bpm.PropertyEnterprise<br />CompanyFilter.Property`(Systems.Bpm.PropertyEnterprise<br />CompanyFilters.md#property) back reference 


## Attribute Details

### AllowedValuesEntityName

When not NULL, specifies that the allowed values are retrieved from the specified entity`Filter(eq)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### AllowedValuesFilterXML

When not NULL specifies the filter to apply when extracting allowed values from entity`Unit: obj.AllowedValuesEntityName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Code

Unique property code.`Required` `Filter(multi eq;like)` `ORD`

Type: **string (40)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, null, "00000")`

### EntityName

The entity for which the property is applicable.`Required` `Filter(eq)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### Hint

The hint, which is displayed alongside the property.`Filter(multi eq;like)` `Introduced in version 20.1`

Type: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether this custom property is active`Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.3.19`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### KeyOrder

When not null, indicates, that the property is a key property and contains the property consequtive position withing the entity. Used for BI and other analysis

Type: **byte __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LimitToAllowedValues

When true, allows the property to be set only to allowed value. When false, the property can have any value.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### MaskLength

Limits te length of the property value to the specified number of characters. Null means no limitation

Type: **int16 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of this CustomProperty. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this CustomProperty. `Introduced in version 20.1`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PropertyType

Type of property values. 'T' - text; 'P' - picture; 'N' - number; 'D' - date.`Required` `Default(&quot;T&quot;)`

Type: **[PropertyType](Systems.Bpm.CustomProperties.md#propertytype)**  
Category: **System**  
Allowed values for the `PropertyType`(Systems.Bpm.CustomProperties.md#propertytype) data attribute  
Allowed Values (Systems.Bpm.CustomPropertiesRepository.PropertyType Enum Members)  

| Value | Description |
| ---- | --- |
| Text | Text value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 0 <br /> Domain API Value: 'Text' |
| Number | Number value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 1 <br /> Domain API Value: 'Number' |
| Picture | Picture value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 2 <br /> Domain API Value: 'Picture' |
| Date | Date value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 3 <br /> Domain API Value: 'Date' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Text**  
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

### AllowedValuesParentProperty

Specifies the user defined property, which is used for filtering the allowed values by value of the parent property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AllowedValuesProperty

When not null, specifies that the current property can have the same allowed values as the specified property. Also, this makes the current and the specified property copy-compatible.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PropertiesCategory

When not null, categorizes the property under a category.

Type: **[PropertiesCategories](Systems.Bpm.PropertiesCategories.md) (nullable)**  
Indexed: **True**  
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

