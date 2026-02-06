---
uid: General.Products.ProductCatalogs
---
# General.Products.ProductCatalogs


Product catalogs serve to organize the products for display primarily in web pages.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductCatalogs  
Base Table: Gen_Product_Catalogs  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Products.ProductCatalogs](General.Products.ProductCatalogs.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BackgroundColor](General.Products.ProductCatalogs.md#backgroundcolor) | int32 __nullable__ | When not NULL, specifies the background color to use for visualization of the catalog. The color is in RGBA color format. 
| [BackgroundImage](General.Products.ProductCatalogs.md#backgroundimage) | byte[] __nullable__ | The background image to be used for web visualization of the catalog. NULL means that background image won't be displayed. 
| [BackgroundPosition<br />Horizontal](General.Products.ProductCatalogs.md#backgroundpositionhorizontal) | [BackgroundPosition<br />Horizontal](General.Products.ProductCatalogs.md#backgroundpositionhorizontal) | Horizontal position of the Background Image. L=Left, C=Center, R=Right.[Required] [Default(&quot;L&quot;)] 
| [BackgroundPositionVertical](General.Products.ProductCatalogs.md#backgroundpositionvertical) | [BackgroundPositionVertical](General.Products.ProductCatalogs.md#backgroundpositionvertical) | Vertical position of the Background Image. T=Top, C=Center, B=Bottom.[Required] [Default(&quot;T&quot;)] 
| [BackgroundRepeat](General.Products.ProductCatalogs.md#backgroundrepeat) | [BackgroundRepeat](General.Products.ProductCatalogs.md#backgroundrepeat) | Specifies if and how the background image will be repeated. R=Repeat both vertically and horizontally; X=Repeat only horizontally; Y=Repeat only vertically; N=No repeat.[Required] [Default(&quot;R&quot;)] 
| [Code](General.Products.ProductCatalogs.md#code) | string (16) | Unique catalog code.[Required] 
| [FooterHtml](General.Products.ProductCatalogs.md#footerhtml) | string (max) __nullable__ | The footer of the catalog in HTML format. Primarily used for web visualizations of the catalog. NULL means that there shouldn't be any user-defined footer. 
| [HeaderHtml](General.Products.ProductCatalogs.md#headerhtml) | string (max) __nullable__ | The header of the catalog in HTML format. Primarily used for web visualizations of the catalog. NULL specifies that there shouldn't be any user-defined header. 
| [Logo](General.Products.ProductCatalogs.md#logo) | byte[] __nullable__ | The logo of the product catalog. Used for web and other visualization of the catalog. 
| [Name](General.Products.ProductCatalogs.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Product catalog name (multilanguage).[Required] 
| [Notes](General.Products.ProductCatalogs.md#notes) | string (max) __nullable__ | Notes for this ProductCatalog. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [RootProductGroup](General.Products.ProductCatalogs.md#rootproductgroup) | [ProductGroups](General.Products.ProductGroups.md) | The root (starting) product group of the catalog. Each catalog starts from a root product group and includes the products in the sub-groups. |
| [WebSite](General.Products.ProductCatalogs.md#website) | [WebSites](Systems.Config.WebSites.md) (nullable) | The ECommerce web site, which will be used to host the product catalog. When NULL, the product catalog would not be hosted with internal ECommerce site. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductCatalogs.md#id) | guid |  
| [ObjectVersion](General.Products.ProductCatalogs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Products.ProductCatalogs.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.ProductCatalogs.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Products.ProductCatalogs.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Products.ProductCatalogs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BackgroundColor

When not NULL, specifies the background color to use for visualization of the catalog. The color is in RGBA color format.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BackgroundImage

The background image to be used for web visualization of the catalog. NULL means that background image won't be displayed.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BackgroundPositionHorizontal

Horizontal position of the Background Image. L=Left, C=Center, R=Right.[Required] [Default(&quot;L&quot;)]

Type: **[BackgroundPosition<br />Horizontal](General.Products.ProductCatalogs.md#backgroundpositionhorizontal)**  
Category: **System**  
Allowed values for the `BackgroundPositionHorizontal`(General.Products.ProductCatalogs.md#backgroundpositionhorizontal) data attribute  
Allowed Values (General.Products.ProductCatalogsRepository.BackgroundPositionHorizontal Enum Members)  

| Value | Description |
| ---- | --- |
| Left | Left value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 0 <br /> Domain API Value: 'Left' |
| Center | Center value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Center' |
| Right | Right value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 2 <br /> Domain API Value: 'Right' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Left**  
Show in UI: **ShownByDefault**  

### BackgroundPositionVertical

Vertical position of the Background Image. T=Top, C=Center, B=Bottom.[Required] [Default(&quot;T&quot;)]

Type: **[BackgroundPositionVertical](General.Products.ProductCatalogs.md#backgroundpositionvertical)**  
Category: **System**  
Allowed values for the `BackgroundPositionVertical`(General.Products.ProductCatalogs.md#backgroundpositionvertical) data attribute  
Allowed Values (General.Products.ProductCatalogsRepository.BackgroundPositionVertical Enum Members)  

| Value | Description |
| ---- | --- |
| Top | Top value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 0 <br /> Domain API Value: 'Top' |
| Center | Center value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Center' |
| Bottom | Bottom value. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 2 <br /> Domain API Value: 'Bottom' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Top**  
Show in UI: **ShownByDefault**  

### BackgroundRepeat

Specifies if and how the background image will be repeated. R=Repeat both vertically and horizontally; X=Repeat only horizontally; Y=Repeat only vertically; N=No repeat.[Required] [Default(&quot;R&quot;)]

Type: **[BackgroundRepeat](General.Products.ProductCatalogs.md#backgroundrepeat)**  
Category: **System**  
Allowed values for the `BackgroundRepeat`(General.Products.ProductCatalogs.md#backgroundrepeat) data attribute  
Allowed Values (General.Products.ProductCatalogsRepository.BackgroundRepeat Enum Members)  

| Value | Description |
| ---- | --- |
| RepeatBothVertically<br />AndHorizontally | RepeatBothVertically<br />AndHorizontally value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 0 <br /> Domain API Value: 'RepeatBothVertically<br />AndHorizontally' |
| RepeatOnlyHorizontally | RepeatOnlyHorizontally value. Stored as 'X'. <br /> Database Value: 'X' <br /> Model Value: 1 <br /> Domain API Value: 'RepeatOnlyHorizontally' |
| RepeatOnlyVertically | RepeatOnlyVertically value. Stored as 'Y'. <br /> Database Value: 'Y' <br /> Model Value: 2 <br /> Domain API Value: 'RepeatOnlyVertically' |
| NoRepeat | NoRepeat value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 3 <br /> Domain API Value: 'NoRepeat' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **RepeatBothVerticallyAndHorizontally**  
Show in UI: **ShownByDefault**  

### Code

Unique catalog code.[Required]

Type: **string (16)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### FooterHtml

The footer of the catalog in HTML format. Primarily used for web visualizations of the catalog. NULL means that there shouldn't be any user-defined footer.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### HeaderHtml

The header of the catalog in HTML format. Primarily used for web visualizations of the catalog. NULL specifies that there shouldn't be any user-defined header.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### Logo

The logo of the product catalog. Used for web and other visualization of the catalog.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

Product catalog name (multilanguage).[Required]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ProductCatalog.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### RootProductGroup

The root (starting) product group of the catalog. Each catalog starts from a root product group and includes the products in the sub-groups.

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WebSite

The ECommerce web site, which will be used to host the product catalog. When NULL, the product catalog would not be hosted with internal ECommerce site.

Type: **[WebSites](Systems.Config.WebSites.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Products.ProductCatalogs erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductCatalogs erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductCatalogs

Domain API Entity Type: 
General_Products_ProductCatalog

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductCatalogs?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductCatalogs?$top=10>

