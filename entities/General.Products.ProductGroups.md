---
uid: General.Products.ProductGroups
---
# General.Products.ProductGroups Entity

**Namespace:** [General.Products](General.Products.md)  

Hierarchical categorization of the products. Entity: Gen_Product_Groups

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [Active](General.Products.ProductGroups.md#active) | boolean | True if the product group is active, false - not to list in combo boxes for choosing in new documents. `Required` `Default(true)` `Filter(eq)` 
| [AggregateLastUpdateTimeUtc](General.Products.ProductGroups.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](General.Products.ProductGroups.md#code) | string (16) | The unique code of the ProductGroup. `Required` `Filter(eq;like)` `ORD` 
| [ConfiguratorCreatesRecipe](General.Products.ProductGroups.md#configuratorcreatesrecipe) | boolean | Whether the product configurator should create one default recipe. true=yes;false=no. `Required` `Default(false)` 
| [ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus) | [ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus) | Usage of product configurator for new products. 0=Product configurator cannot be used to create products in this group;1=The configurator can be used;2=The configurator should be used and products cannot be created directly. `Required` `Default(0)` 
| [DisplayText](General.Products.ProductGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](General.Products.ProductGroups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.ProductGroups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FullPath](General.Products.ProductGroups.md#fullpath) | string (254) | Full tree path in the form /parent/.../leaf/. Contains the group codes. `Required` `Default("")` `Filter(eq;like)` `ORD` 
| [Id](General.Products.ProductGroups.md#id) | guid |  
| [Name](General.Products.ProductGroups.md#name) | [MultilanguageString (180)](../data-types.md#multilanguagestring) | Group name should be unique among the other groups within the same parent. `Required` `Filter(eq;like)` 
| [NextPartNumber](General.Products.ProductGroups.md#nextpartnumber) | string (16) __nullable__ | Contains the next part number to be auto-assigned to parts, created in the group or sub-groups. 
| [NextSerialNumber](General.Products.ProductGroups.md#nextserialnumber) | string (40) __nullable__ | When not null, specifies the next serial number, that should be assigned to new produced items. `Filter(eq;like)` 
| [Notes](General.Products.ProductGroups.md#notes) | string (254) __nullable__ | User notes for the item group. 
| [ObjectVersion](General.Products.ProductGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [<s>Parent</s>](General.Products.ProductGroups.md#parent) | string (254) | **OBSOLETE! Do not use!** Full tree path of the parent group in the form /parent/.../leaf/. Contains the group codes. `Obsolete` `Required` `Default("/")` `Filter(eq)` `Obsoleted in version 22.1.6.92` 
| [Picture](General.Products.ProductGroups.md#picture) | byte[] __nullable__ | The picture of the product group. 
| [PictureLastUpdateTime](General.Products.ProductGroups.md#picturelastupdatetime) | datetime __nullable__ | Last update time of the Picture. `Filter(ge;le)` `ReadOnly` 
| [ProductDescriptionMask](General.Products.ProductGroups.md#productdescriptionmask) | [MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__ | When not null specifies mask for new product descriptions for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes. 
| [ProductNameMask](General.Products.ProductGroups.md#productnamemask) | [MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__ | When not null specifies mask for new product names for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes. 
| [UseLots](General.Products.ProductGroups.md#uselots) | [UseLots](General.Products.ProductGroups.md#uselots) __nullable__ | Specifies whether for the products from this group and its sub-groups the use of lots in store documents is required or is unallowed or is allowed while not required. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultMeasurementUnit](General.Products.ProductGroups.md#defaultmeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | When not null, specifies default measurement unit, which should be assigned to new products in the group. `Filter(multi eq)` |
| [DefaultProductType](General.Products.ProductGroups.md#defaultproducttype) | [ProductTypes](General.Products.ProductTypes.md) (nullable) | When not null, specifies default product type, which should be assigned to new products in the group. `Filter(multi eq)` |
| [EnterpriseCompany](General.Products.ProductGroups.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, specifies that the product group, its sub-groups and products are specific to a given enterprise company and may be used only in documents from this enterprise company. `Filter(multi eq)` |
| [ParentGroup](General.Products.ProductGroups.md#parentgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Parent product group. null if this is root group. `Filter(multi eq)` `Introduced in version 22.1.5.98` |
| [PricingModel](General.Products.ProductGroups.md#pricingmodel) | [PricingModels](Crm.Pricing.PricingModels.md) (nullable) | When not null, specifies the pricing model, for the products in this product group. The model is by default valid also for sub-groups, unless they have other models. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| PrincipalRecipes | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | List of `PrincipalRecipe`(Production.Technologies.PrincipalRecipes.md) child objects, based on the `Production.Technologies.PrincipalRecipe.ProductGroup`(Production.Technologies.PrincipalRecipes.md#productgroup) back reference 
| RangeProperties | [ProductGroupRangeProperties](General.Products.ProductGroupRangeProperties.md) | List of `ProductGroupRange<br />Property`(General.Products.ProductGroupRange<br />Properties.md) child objects, based on the `General.Products.ProductGroupRangeProperty.ProductGroup`(General.Products.ProductGroupRange<br />Properties.md#productgroup) back reference 
| RequiredProperties | [ProductGroupRequiredProperties](General.Products.ProductGroupRequiredProperties.md) | List of `ProductGroupRequired<br />Property`(General.Products.ProductGroupRequired<br />Properties.md) child objects, based on the `General.Products.ProductGroupRequired<br />Property.ProductGroup`(General.Products.ProductGroupRequired<br />Properties.md#productgroup) back reference 


## Attribute Details

### Active

True if the product group is active, false - not to list in combo boxes for choosing in new documents. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
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

### Code

The unique code of the ProductGroup. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.Code, o => ( o.ParentGroup == obj.ParentGroup), IIF( ( obj.ParentGroup == null), "000", ( obj.ParentGroup.Code + "00")))`

### ConfiguratorCreatesRecipe

Whether the product configurator should create one default recipe. true=yes;false=no. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ConfiguratorStatus

Usage of product configurator for new products. 0=Product configurator cannot be used to create products in this group;1=The configurator can be used;2=The configurator should be used and products cannot be created directly. `Required` `Default(0)`

_Type_: **[ConfiguratorStatus](General.Products.ProductGroups.md#configuratorstatus)**  
_Category_: **System**  
Allowed values for the `ConfiguratorStatus`(General.Products.ProductGroups.md#configuratorstatus) data attribute  
_Allowed Values (General.Products.ProductGroupsRepository.ConfiguratorStatus Enum Members)_  

| Value | Description |
| ---- | --- |
| NotAllowed | NotAllowed value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NotAllowed' |
| Allowed | Allowed value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Allowed' |
| Obligatory | Obligatory value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Obligatory' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
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

### FullPath

Full tree path in the form /parent/.../leaf/. Contains the group codes. `Required` `Default("")` `Filter(eq;like)` `ORD`

_Type_: **string (254)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Default Value_: ****  
_Show in UI_: **CannotBeShown**  

_Front-End Recalc Expressions:_  
`Format( "{0}{1}/", IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/"), obj.Code)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

Group name should be unique among the other groups within the same parent. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (180)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### NextPartNumber

Contains the next part number to be auto-assigned to parts, created in the group or sub-groups.

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### NextSerialNumber

When not null, specifies the next serial number, that should be assigned to new produced items. `Filter(eq;like)`

_Type_: **string (40) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### Notes

User notes for the item group.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Parent

**OBSOLETE! Do not use!** Full tree path of the parent group in the form /parent/.../leaf/. Contains the group codes. `Obsolete` `Required` `Default("/")` `Filter(eq)` `Obsoleted in version 22.1.6.92`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Default Value_: **/**  
_Show in UI_: **CannotBeShown**  

_Back-End Default Expression:_  
`IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/")`

_Front-End Recalc Expressions:_  
`IIF( ( obj.ParentGroup != null), obj.ParentGroup.FullPath, "/")`
### Picture

The picture of the product group.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PictureLastUpdateTime

Last update time of the Picture. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProductDescriptionMask

When not null specifies mask for new product descriptions for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes.

_Type_: **[MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProductNameMask

When not null specifies mask for new product names for this group and its sub-groups. The mask substitutes {0}..{n} with the appropriate custom attributes.

_Type_: **[MultilanguageString (1000)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UseLots

Specifies whether for the products from this group and its sub-groups the use of lots in store documents is required or is unallowed or is allowed while not required.

_Type_: **[UseLots](General.Products.ProductGroups.md#uselots) __nullable__**  
_Category_: **System**  
Allowed values for the `UseLots`(General.Products.ProductGroups.md#uselots) data attribute  
_Allowed Values (General.Products.ProductGroupsRepository.UseLots Enum Members)_  

| Value | Description |
| ---- | --- |
| Allowed | Allowed value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Allowed' |
| NotAllowed | NotAllowed value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'NotAllowed' |
| Required | Required value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Required' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DefaultMeasurementUnit

When not null, specifies default measurement unit, which should be assigned to new products in the group. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DefaultProductType

When not null, specifies default product type, which should be assigned to new products in the group. `Filter(multi eq)`

_Type_: **[ProductTypes](General.Products.ProductTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

When not null, specifies that the product group, its sub-groups and products are specific to a given enterprise company and may be used only in documents from this enterprise company. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentGroup

Parent product group. null if this is root group. `Filter(multi eq)` `Introduced in version 22.1.5.98`

_Type_: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.Transaction.Query( ).Where( pg => ( pg.FullPath == obj.Parent)).FirstOrDefault( )`

### PricingModel

When not null, specifies the pricing model, for the products in this product group. The model is by default valid also for sub-groups, unless they have other models. `Filter(multi eq)`

_Type_: **[PricingModels](Crm.Pricing.PricingModels.md) (nullable)**  
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

