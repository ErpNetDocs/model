---
uid: General.Products.ProductPictures
---
# General.Products.ProductPictures


Pictures of products.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductPictures  
Base Table: Gen_Product_Pictures  
API access:  ReadWrite  

## Visualization
Display Format: {Product.Name:T}  
Search Members: Product.Name  
Name Member: Product.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Comments](General.Products.ProductPictures.md#comments) | string (254) __nullable__ | Comments for this ProductPicture. 
| [IsDefault](General.Products.ProductPictures.md#isdefault) | boolean | 1=This is the default picture for the product and the size class; 0=otherwise`Required` `Default(false)` `Filter(eq)` 
| [LastUpdateTime](General.Products.ProductPictures.md#lastupdatetime) | datetime __nullable__ | The exact server time, when the picture was last updated. Set automatically.`Filter(ge;le)` `ReadOnly` 
| [Picture](General.Products.ProductPictures.md#picture) | byte[] __nullable__ | The actual product picture. Can be NULL if we insert only some comments 
| [PictureNo](General.Products.ProductPictures.md#pictureno) | int32 | Unique picture number within the product. Also used for sorting`Required` `Filter(eq;like)` 
| [PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) | [PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) __nullable__ | Specifies the relative picture size and usage. S=Small picture (thumbnail), L=Large picture (full size), NULL=unspecified. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](General.Products.ProductPictures.md#product) | [Products](General.Products.Products.md) | The <see cref="Product"/> to which this ProductPicture belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductPictures.md#id) | guid |  
| [ObjectVersion](General.Products.ProductPictures.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductPictures.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Comments

Comments for this ProductPicture.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsDefault

1=This is the default picture for the product and the size class; 0=otherwise`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`( obj.Product.Pictures.Take( 2).Count( ) == 1)`
### LastUpdateTime

The exact server time, when the picture was last updated. Set automatically.`Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Picture

The actual product picture. Can be NULL if we insert only some comments

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PictureNo

Unique picture number within the product. Also used for sorting`Required` `Filter(eq;like)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Product.Pictures.Select( c => c.PictureNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Product.Pictures.Select( c => c.PictureNo).DefaultIfEmpty( 0).Max( ) + 1)`
### PictureSizeClass

Specifies the relative picture size and usage. S=Small picture (thumbnail), L=Large picture (full size), NULL=unspecified.

Type: **[PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) __nullable__**  
Category: **System**  
Allowed values for the `PictureSizeClass`(General.Products.ProductPictures.md#picturesizeclass) data attribute  
Allowed Values (General.Products.ProductPicturesRepository.PictureSizeClass Enum Members)  

| Value | Description |
| ---- | --- |
| SmallPictureThumbnail | SmallPictureThumbnail value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'SmallPictureThumbnail' |
| LargePictureFullSize | LargePictureFullSize value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'LargePictureFullSize' |

Supported Filters: **NotFilterable**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Product

The <see cref="Product"/> to which this ProductPicture belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=General.Products.ProductPictures erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductPictures erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductPictures

Domain API Entity Type: 
General_Products_ProductPicture

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductPictures?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductPictures?$top=10>

