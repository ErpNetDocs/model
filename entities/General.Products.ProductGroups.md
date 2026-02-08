---
uid: General.Products.ProductGroups
---
# General.Products.ProductGroups


Hierarchical categorization of the products.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductGroups  
Base Table: Gen_Product_Groups  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Products.ProductGroups](General.Products.ProductGroups.md)  
  * [General.Products.ProductGroupRangeProperties](General.Products.ProductGroupRangeProperties.md)  
  * [General.Products.ProductGroupRequiredProperties](General.Products.ProductGroupRequiredProperties.md)  
  * [Production.Technologies.PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)  
    * [Production.Technologies.PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md)  
    * [Production.Technologies.PrincipalRecipeOperations](Production.Technologies.PrincipalRecipeOperations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](General.Products.ProductGroups.md#active) | boolean | 1 if the product group is active, 0 - not to list in combo boxes for choosing in new documents`Required` `Default(true)` `Filter(eq)` 
| [Code](General.Products.ProductGroups.md#code) | string (16) | The unique code of the ProductGroup. `Required` `Filter(eq;like)` `ORD` 
| [ConfiguratorCreatesRecipe](General.Products.ProductGroups.md#configuratorcreatesrecipe) | boolean | Whether the product configurator should create one default recipe. 1=yes;0=no`Required` `Default(false)` 
| [ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus) | [ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus) | Usage of product configurator for new products. 0=Product configurator cannot be used to create products in this group;1=The configurator can be used;2=The configurator should be used and products cannot be created directly`Required` `Default(0)` 
| [FullPath](General.Products.ProductGroups.md#fullpath) | string (254) | Full tree path in the form /parent/.../leaf/. Contains the group codes.`Required` `Default(&quot;&quot;)` `Filter(eq;like)` `ORD` 
| [Name](General.Products.ProductGroups.md#name) | [MultilanguageString (180)](../data-types.md#multilanguagestring) | Group name should be unique among the other groups within the same parent`Required` `Filter(eq;like)` 
| [NextPartNumber](General.Products.ProductGroups.md#nextpartnumber) | string (16) __nullable__ | Contains the next part number to be auto-assigned to parts, created in the group or sub-groups 
| [NextSerialNumber](General.Products.ProductGroups.md#nextserialnumber) | string (40) __nullable__ | Next serial number, that should be assigned to new produced items from this group or its subgroups.`Filter(eq;like)` 
| [Notes](General.Products.ProductGroups.md#notes) | string (254) __nullable__ | User notes for the item group 
| [<s>Parent</s>](General.Products.ProductGroups.md#parent) | string (254) | **OBSOLETE! Do not use!** Full tree path of the parent group in the form /parent/.../leaf/. Contains the group codes.`Obsolete` `Required` `Default(&quot;/&quot;)` `Filter(eq)` `Obsoleted in version 22.1.6.92` 
| [Picture](General.Products.ProductGroups.md#picture) | byte[] __nullable__ | The picture of the product group 
| [PictureLastUpdateTime](General.Products.ProductGroups.md#picturelastupdatetime) | datetime __nullable__ | Last update time of the Picture`Filter(ge;le)` `ReadOnly` 
| [ProductDescriptionMask](General.Products.ProductGroups.md#productdescriptionmask) | [MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__ | When not NULL specifies mask for new product descriptions for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes 
| [ProductNameMask](General.Products.ProductGroups.md#productnamemask) | [MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__ | When not NULL specifies mask for new product names for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes 
| [UseLots](General.Products.ProductGroups.md#uselots) | [UseLots](General.Products.ProductGroups.md#uselots) __nullable__ | Specifies whether for the products from this group and its sub-groups the use of lots in store documents is required or is unallowed or is allowed while not required. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultMeasurementUnit](General.Products.ProductGroups.md#defaultmeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | When not null, specifies default measurement unit, which should be assigned to new products in the group. |
| [DefaultProductType](General.Products.ProductGroups.md#defaultproducttype) | [ProductTypes](General.Products.ProductTypes.md) (nullable) | A product type that is used when creating new products in this product group |
| [EnterpriseCompany](General.Products.ProductGroups.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Specifies if the product group, its sub-groups and products are specific to a given enterprise company and may be used only in documents from this enterprise company. |
| [ParentGroup](General.Products.ProductGroups.md#parentgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Parent product group. NULL if this is root group |
| [PricingModel](General.Products.ProductGroups.md#pricingmodel) | [PricingModels](Crm.Pricing.PricingModels.md) (nullable) | The pricing model, for the products in this product group. The model is by default valid also for sub-groups, unless they have other models |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductGroups.md#id) | guid | Unique Id of the item group 
| [ObjectVersion](General.Products.ProductGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Products.ProductGroups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.ProductGroups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Products.ProductGroups.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Products.ProductGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| PrincipalRecipes | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | List of `PrincipalRecipe`(Production.Technologies.PrincipalRecipes.md) child objects, based on the `Production.Technologies.PrincipalRecipe.ProductGroup`(Production.Technologies.PrincipalRecipes.md#productgroup) back reference 
| RangeProperties | [ProductGroupRangeProperties](General.Products.ProductGroupRangeProperties.md) | List of `ProductGroupRange<br />Property`(General.Products.ProductGroupRange<br />Properties.md) child objects, based on the `General.Products.ProductGroupRangeProperty.ProductGroup`(General.Products.ProductGroupRange<br />Properties.md#productgroup) back reference 
| RequiredProperties | [ProductGroupRequiredProperties](General.Products.ProductGroupRequiredProperties.md) | List of `ProductGroupRequired<br />Property`(General.Products.ProductGroupRequired<br />Properties.md) child objects, based on the `General.Products.ProductGroupRequired<br />Property.ProductGroup`(General.Products.ProductGroupRequired<br />Properties.md#productgroup) back reference 


## Attribute Details

### Active

1 if the product group is active, 0 - not to list in combo boxes for choosing in new documents`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Code

The unique code of the ProductGroup. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, o => ( o.ParentGroup == obj.ParentGroup), IIF( ( obj.ParentGroup == null), "000", ( obj.ParentGroup.Code + "00")))`

### ConfiguratorCreatesRecipe

Whether the product configurator should create one default recipe. 1=yes;0=no`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ConfiguratorStatus

Usage of product configurator for new products. 0=Product configurator cannot be used to create products in this group;1=The configurator can be used;2=The configurator should be used and products cannot be created directly`Required` `Default(0)`

Type: **[ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus)**  
Category: **System**  
Allowed values for the `ConfiguratorStatus`(General.Products.ProductGroups.md#configuratorstatus) data attribute  
Allowed Values (General.Products.ProductGroupsRepository.ConfiguratorStatus Enum Members)  

| Value | Description |
| ---- | --- |
| NotAllowed | NotAllowed value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'NotAllowed' |
| Allowed | Allowed value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Allowed' |
| Obligatory | Obligatory value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Obligatory' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### FullPath

Full tree path in the form /parent/.../leaf/. Contains the group codes.`Required` `Default(&quot;&quot;)` `Filter(eq;like)` `ORD`

Type: **string (254)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **254**  
Default Value: ****  
Show in UI: **CannotBeShown**  

Front-End Recalc Expressions:  
`Format( "{0}{1}/", IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/"), obj.Code)`
### Name

Group name should be unique among the other groups within the same parent`Required` `Filter(eq;like)`

Type: **[MultilanguageString (180)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NextPartNumber

Contains the next part number to be auto-assigned to parts, created in the group or sub-groups

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### NextSerialNumber

Next serial number, that should be assigned to new produced items from this group or its subgroups.`Filter(eq;like)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### Notes

User notes for the item group

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Parent

**OBSOLETE! Do not use!** Full tree path of the parent group in the form /parent/.../leaf/. Contains the group codes.`Obsolete` `Required` `Default(&quot;/&quot;)` `Filter(eq)` `Obsoleted in version 22.1.6.92`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Default Value: **/**  
Show in UI: **CannotBeShown**  

Back-End Default Expression:  
`IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/")`

Front-End Recalc Expressions:  
`IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/")`
### Picture

The picture of the product group

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PictureLastUpdateTime

Last update time of the Picture`Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProductDescriptionMask

When not NULL specifies mask for new product descriptions for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes

Type: **[MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProductNameMask

When not NULL specifies mask for new product names for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes

Type: **[MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UseLots

Specifies whether for the products from this group and its sub-groups the use of lots in store documents is required or is unallowed or is allowed while not required.

Type: **[UseLots](General.Products.ProductGroups.md#uselots) __nullable__**  
Category: **System**  
Allowed values for the `UseLots`(General.Products.ProductGroups.md#uselots) data attribute  
Allowed Values (General.Products.ProductGroupsRepository.UseLots Enum Members)  

| Value | Description |
| ---- | --- |
| Allowed | Allowed value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Allowed' |
| NotAllowed | NotAllowed value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 1 <br /> Domain API Value: 'NotAllowed' |
| Required | Required value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 2 <br /> Domain API Value: 'Required' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Unique Id of the item group

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

### DefaultMeasurementUnit

When not null, specifies default measurement unit, which should be assigned to new products in the group.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultProductType

A product type that is used when creating new products in this product group

Type: **[ProductTypes](General.Products.ProductTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Specifies if the product group, its sub-groups and products are specific to a given enterprise company and may be used only in documents from this enterprise company.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentGroup

Parent product group. NULL if this is root group

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.Transaction.Query( ).Where( pg => ( pg.FullPath == obj.Parent)).FirstOrDefault( )`

### PricingModel

The pricing model, for the products in this product group. The model is by default valid also for sub-groups, unless they have other models

Type: **[PricingModels](Crm.Pricing.PricingModels.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Products.ProductGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductGroups

Domain API Entity Type: 
General_Products_ProductGroup

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductGroups?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductGroups?$top=10>

