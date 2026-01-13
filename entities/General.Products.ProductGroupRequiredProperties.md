---
uid: General.Products.ProductGroupRequiredProperties
---
# General.Products.ProductGroupRequiredProperties Entity

**Namespace:** [General.Products](General.Products.md)  

Contains the properties, that are required to be set, when creating new products in the category and its sub-categories. Entity: Gen_Product_Group_Required_Properties

## Default Visualization
Default Display Text Format:  
_{ProductGroup.Name:T}_  
Default Search Members:  
_ProductGroup.Name_  
Name Data Member:  
_ProductGroup.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultPropertyValue](General.Products.ProductGroupRequiredProperties.md#defaultpropertyvalue) | string (254) __nullable__ | When not null, specifies the default value of the property, for new products in the group. 
| [DefaultProperty<br />ValueDescription](General.Products.ProductGroupRequiredProperties.md#defaultpropertyvaluedescription) | string (254) __nullable__ | When not null, specifies the default description value of the property, for new products in the group. 
| [DefaultValueId](General.Products.ProductGroupRequiredProperties.md#defaultvalueid) | guid __nullable__ | When not null, specifies the default internal Id value of the property, for new products in the group. `Filter(multi eq)` 
| [DisplayText](General.Products.ProductGroupRequiredProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Products.ProductGroupRequiredProperties.md#id) | guid |  
| [ObjectVersion](General.Products.ProductGroupRequiredProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PropertyNo](General.Products.ProductGroupRequiredProperties.md#propertyno) | int32 | The consecutive number (position) of the property within the product group and its subgroups. The parent groups of each leaf group should contain only unique property numbers. `Required` `Default(0)` 
| [Required](General.Products.ProductGroupRequiredProperties.md#required) | boolean | Specifies whether the property is required (or only suggested) to be set for new products. Suggested properties are used by product configuration and other product creation services. true=Required, false=Suggested. `Required` `Default(false)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProductGroup](General.Products.ProductGroupRequiredProperties.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The <see cref="ProductGroup"/> to which this ProductGroupRequired<br />Property belongs. `Required` `Filter(multi eq)` `Owner` |
| [Property](General.Products.ProductGroupRequiredProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The property, that is required when creating new products in the group. The property is automatically added to new products, created in the group. The property should be with Entity Type = 'Product'. `Required` `Filter(multi eq)` |


## Attribute Details

### DefaultPropertyValue

When not null, specifies the default value of the property, for new products in the group.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### DefaultPropertyValueDescription

When not null, specifies the default description value of the property, for new products in the group.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### DefaultValueId

When not null, specifies the default internal Id value of the property, for new products in the group. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PropertyNo

The consecutive number (position) of the property within the product group and its subgroups. The parent groups of each leaf group should contain only unique property numbers. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ProductGroup.RequiredProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.ProductGroup.RequiredProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Required

Specifies whether the property is required (or only suggested) to be set for new products. Suggested properties are used by product configuration and other product creation services. true=Required, false=Suggested. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ProductGroup

The <see cref="ProductGroup"/> to which this ProductGroupRequiredProperty belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProductGroups](General.Products.ProductGroups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Property

The property, that is required when creating new products in the group. The property is automatically added to new products, created in the group. The property should be with Entity Type = 'Product'. `Required` `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=General.Products.ProductGroupRequiredProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductGroupRequiredProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductGroupRequiredProperties

Domain API Entity Type: 
General_Products_ProductGroupRequiredProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductGroupRequiredProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductGroupRequiredProperties?$top=10>

