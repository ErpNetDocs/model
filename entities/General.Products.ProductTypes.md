---
uid: General.Products.ProductTypes
---
# General.Products.ProductTypes


Categorization of the products by their nature.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductTypes  
Base Table: Gen_Product_Types  
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
* [General.Products.ProductTypes](General.Products.ProductTypes.md)  
  * [General.Products.ProductTypePurchaseInvoiceLineProperties](General.Products.ProductTypePurchaseInvoiceLineProperties.md)  
  * [Crm.Pos.ProductTypeTaxGroups](Crm.Pos.ProductTypeTaxGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.Products.ProductTypes.md#code) | string (16) | The unique code of the ProductType. `Required` `Filter(eq;like)` `ORD` 
| [IsDefault](General.Products.ProductTypes.md#isdefault) | boolean | When checked specifies that this type is set by default for new products unless another type is specified in the product groups.[Required] [Default(false)] [Filter(eq)] 
| [IsFixedAsset](General.Products.ProductTypes.md#isfixedasset) | boolean | Determines whether assets are acquired or retired when products from this type are purchased or sold.[Required] [Default(false)] [Filter(eq)] 
| [IsServiceActivityService](General.Products.ProductTypes.md#isserviceactivityservice) | boolean | 1 when the product corresponds to service used in service documents (like service activities)[Required] [Default(false)] [Filter(eq)] 
| [IsServiced](General.Products.ProductTypes.md#isserviced) | boolean | Determines whether for the products of this type can be created service agreements.[Required] [Default(false)] [Filter(eq)] 
| [IsShipped](General.Products.ProductTypes.md#isshipped) | boolean | Determines whether the products from this type are shipped after sales.[Required] [Default(false)] [Filter(eq)] 
| [IsStocked](General.Products.ProductTypes.md#isstocked) | boolean | 1=The products of this type are stocked in a warehouse; 0=otherwise (services)[Required] [Default(true)] [Filter(eq)] 
| [LotAutoCreation](General.Products.ProductTypes.md#lotautocreation) | boolean | If checked specifies that lots are automatically created by the receiving orders with which the products are received.[Required] [Default(false)] 
| [Name](General.Products.ProductTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this ProductType. `Required` `Filter(eq;like)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductTypes.md#id) | guid |  
| [ObjectVersion](General.Products.ProductTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Products.ProductTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.ProductTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Products.ProductTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Products.ProductTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| PurchaseInvoice<br />LineProperties | [ProductTypePurchaseInvoiceLineProperties](General.Products.ProductTypePurchaseInvoiceLineProperties.md) | List of `ProductTypePurchase<br />InvoiceLineProperty`(General.Products.ProductTypePurchase<br />InvoiceLineProperties.md) child objects, based on the `General.Products.ProductTypePurchase<br />InvoiceLineProperty.ProductType`(General.Products.ProductTypePurchase<br />InvoiceLineProperties.md#producttype) back reference 
| TaxGroups | [ProductTypeTaxGroups](Crm.Pos.ProductTypeTaxGroups.md) | List of `ProductTypeTaxGroup`(Crm.Pos.ProductTypeTaxGroups.md) child objects, based on the `Crm.Pos.ProductTypeTaxGroup.ProductType`(Crm.Pos.ProductTypeTaxGroups.md#producttype) back reference 


## Attribute Details

### Code

The unique code of the ProductType. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, null, "00000")`

### IsDefault

When checked specifies that this type is set by default for new products unless another type is specified in the product groups.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsFixedAsset

Determines whether assets are acquired or retired when products from this type are purchased or sold.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsServiceActivityService

1 when the product corresponds to service used in service documents (like service activities)[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsServiced

Determines whether for the products of this type can be created service agreements.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsShipped

Determines whether the products from this type are shipped after sales.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsStocked

1=The products of this type are stocked in a warehouse; 0=otherwise (services)[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### LotAutoCreation

If checked specifies that lots are automatically created by the receiving orders with which the products are received.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of this ProductType. `Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
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

[!list limit=1000 erp.entity=General.Products.ProductTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductTypes

Domain API Entity Type: 
General_Products_ProductType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductTypes?$top=10>

