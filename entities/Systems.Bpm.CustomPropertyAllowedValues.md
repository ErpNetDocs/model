---
uid: Systems.Bpm.CustomPropertyAllowedValues
---
# Systems.Bpm.CustomPropertyAllowedValues Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

User-defined properties allowed values. Can be specified only for properties with unbound allowed values (e.g. for which Allowed Values Entity is not set). Entity: Gen_Property_Allowed_Values

## Renames

Old name: **General.CustomPropertyAllowedValues**  
New name: **Systems.Bpm.CustomPropertyAllowedValues**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Description:T}_  
Default Search Members:  
_PropertyAllowedValueField; Description_  
Code Data Member:  
_PropertyAllowedValueField_  
Name Data Member:  
_Description_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  
Aggregate Root:  
[Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Systems.Bpm.CustomPropertyAllowedValues.md#active) | boolean | Specifies whether the allowed value is active and can be used when selecting property values. `Required` `Default(true)` `Filter(eq)` 
| [Description](Systems.Bpm.CustomPropertyAllowedValues.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The description of the property allowed value. Used to fill the Description column of the Property_Value in Gen_Property_Values_Table. `Filter(eq;like)` 
| [DisplayText](Systems.Bpm.CustomPropertyAllowedValues.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Bpm.CustomPropertyAllowedValues.md#id) | guid |  
| [LongDescription](Systems.Bpm.CustomPropertyAllowedValues.md#longdescription) | string (max) __nullable__ | When not null, specifies a long description of the allowed value. This long description is only used as helper information when selecting values, it is not copied in the property value. 
| [ObjectVersion](Systems.Bpm.CustomPropertyAllowedValues.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentAllowedValueId](Systems.Bpm.CustomPropertyAllowedValues.md#parentallowedvalueid) | guid __nullable__ | The value of the parent property, for which this allowed value is valid. `Filter(multi eq)` 
| [Picture](Systems.Bpm.CustomPropertyAllowedValues.md#picture) | byte[] __nullable__ | When not null, specifies a picture representation of the allowed value. 
| [PropertyAllowedValueField](Systems.Bpm.CustomPropertyAllowedValues.md#propertyallowedvaluefield) | string (254) | The actual allowed value. `Required` `Filter(eq;like)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Bpm.CustomPropertyAllowedValues.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this CustomPropertyAllowedValue applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [Property](Systems.Bpm.CustomPropertyAllowedValues.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The <see cref="CustomProperty"/> to which this CustomPropertyAllowedValue belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Active

Specifies whether the allowed value is active and can be used when selecting property values. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Description

The description of the property allowed value. Used to fill the Description column of the Property_Value in Gen_Property_Values_Table. `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LongDescription

When not null, specifies a long description of the allowed value. This long description is only used as helper information when selecting values, it is not copied in the property value.

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

### ParentAllowedValueId

The value of the parent property, for which this allowed value is valid. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Picture

When not null, specifies a picture representation of the allowed value.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PropertyAllowedValueField

The actual allowed value. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The Enterprise Company to which this CustomPropertyAllowedValue applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Property

The <see cref="CustomProperty"/> to which this CustomPropertyAllowedValue belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=Systems.Bpm.CustomPropertyAllowedValues erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.CustomPropertyAllowedValues erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_CustomPropertyAllowedValues

Domain API Entity Type: 
Systems_Bpm_CustomPropertyAllowedValue

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_CustomPropertyAllowedValues?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_CustomPropertyAllowedValues?$top=10>

