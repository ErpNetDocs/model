---
uid: General.Products.ProductGroupRequiredProperties
---
# General.Products.ProductGroupRequiredProperties


Contains the properties, that are required to be set, when creating new products in the category and its sub-categories

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductGroupRequiredProperties  
Base Table: Gen_Product_Group_Required_Properties  
API access:  ReadWrite  

## Visualization
Display Format: {ProductGroup.Name:T}  
Search Members: ProductGroup.Name  
Name Member: ProductGroup.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

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
| [PropertyNo](General.Products.ProductGroupRequiredProperties.md#propertyno) | int32 | The consecutive number (position) of the property within the product group and its subgroups. The parent groups of each leaf group should contain only unique property numbers.[Required] [Default(0)] 
| [Required](General.Products.ProductGroupRequiredProperties.md#required) | boolean | Specifies whether the property is required (or only suggested) to be set for new products. Suggested properties are used by product configuration and other product creation services. 1=Required, 0=Suggested.[Required] [Default(false)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProductGroup](General.Products.ProductGroupRequiredProperties.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The <see cref="ProductGroup"/> to which this ProductGroupRequired<br />Property belongs. `Required` `Filter(multi eq)` `Owner` |
| [Property](General.Products.ProductGroupRequiredProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The property, that is required when creating new products in the group. The property is automatically added to new products, created in the group. The property should be with Entity Type = 'Product'. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductGroupRequiredProperties.md#id) | guid |  
| [ObjectVersion](General.Products.ProductGroupRequiredProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductGroupRequiredProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DefaultPropertyValue

When not null, specifies the default value of the property, for new products in the group.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### DefaultPropertyValueDescription

When not null, specifies the default description value of the property, for new products in the group.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### DefaultValueId

When not null, specifies the default internal Id value of the property, for new products in the group. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PropertyNo

The consecutive number (position) of the property within the product group and its subgroups. The parent groups of each leaf group should contain only unique property numbers.[Required] [Default(0)]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ProductGroup.RequiredProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.ProductGroup.RequiredProperties.Select( c => c.PropertyNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Required

Specifies whether the property is required (or only suggested) to be set for new products. Suggested properties are used by product configuration and other product creation services. 1=Required, 0=Suggested.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### ProductGroup

The <see cref="ProductGroup"/> to which this ProductGroupRequiredProperty belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Property

The property, that is required when creating new products in the group. The property is automatically added to new products, created in the group. The property should be with Entity Type = 'Product'.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

