---
uid: Systems.Core.FormLayouts
---
# Systems.Core.FormLayouts Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains user layouts of the screen forms. Entity: Sys_Form_Layouts

## Renames

Old name: **Systems.UI.FormLayouts**  
New name: **Systems.Core.FormLayouts**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{ApplicationName}_  
Default Search Members:  
_ApplicationName_  
Name Data Member:  
_ApplicationName_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.FormLayouts](Systems.Core.FormLayouts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Core.FormLayouts.md#applicationname) | string (64) | The application, which consumes the layout. `Required` `Filter(eq)` `ORD` 
| [Category](Systems.Core.FormLayouts.md#category) | string (36) __nullable__ | The object category for which the layout is applied. Object category is usually user-defined and further divides the objects of a given object type. `Filter(eq)` `Introduced in version 23.1.1.25` 
| [DisplayText](Systems.Core.FormLayouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Core.FormLayouts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.FormLayouts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FormName](Systems.Core.FormLayouts.md#formname) | string (128) | The form, for which the layout is applied. `Required` `Filter(eq;like)` 
| [Id](Systems.Core.FormLayouts.md#id) | guid |  
| [Layout](Systems.Core.FormLayouts.md#layout) | byte[] __nullable__ | The byte storage of the layout. 
| [LayoutFormat](Systems.Core.FormLayouts.md#layoutformat) | [LayoutFormat](Systems.Core.FormLayouts.md#layoutformat) | The format of the data in the Layout column. Values can be: 'U' - uncompressed; 'L' - LZO compressed; 'D' - Deflate compressed. `Required` `Default("U")` 
| [LayoutName](Systems.Core.FormLayouts.md#layoutname) | string (64) | The name of a named layout. Standard layouts have empty string names. `Required` `Filter(eq;like)` 
| [<s>LayoutXml</s>](Systems.Core.FormLayouts.md#layoutxml) | string (max) __nullable__ | **OBSOLETE! Do not use!** Layout xml - not used. `Obsolete` `Obsoleted in version 22.1.6.61` 
| [<s>MachineName</s>](Systems.Core.FormLayouts.md#machinename) | string (128) __nullable__ | **OBSOLETE! Do not use!** The machine name - not used. `Obsolete` `Filter(eq;like)` `Obsoleted in version 22.1.6.61` 
| [ObjectVersion](Systems.Core.FormLayouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PanelName](Systems.Core.FormLayouts.md#panelname) | string (64) | The visual panel, for which the layout is applied. `Required` `Default("Form")` `Filter(eq)` 
| [UserName](Systems.Core.FormLayouts.md#username) | string (64) __nullable__ | The user for which the layout is applied. null means that the layout is applied for all users. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Core.FormLayouts.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The security access key which controls the access to the layout view. `Filter(multi eq)` |
| [InheritFormLayout](Systems.Core.FormLayouts.md#inheritformlayout) | [FormLayouts](Systems.Core.FormLayouts.md) (nullable) | Specified when the current layout inherits from another layout. `Filter(multi eq)` `Introduced in version 25.1.1.56` |
| [Role](Systems.Core.FormLayouts.md#role) | [Roles](Systems.Security.Roles.md) (nullable) | The role, for which the layout is applied. `Filter(multi eq)` |


## Attribute Details

### ApplicationName

The application, which consumes the layout. `Required` `Filter(eq)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Category

The object category for which the layout is applied. Object category is usually user-defined and further divides the objects of a given object type. `Filter(eq)` `Introduced in version 23.1.1.25`

_Type_: **string (36) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **36**  
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

### FormName

The form, for which the layout is applied. `Required` `Filter(eq;like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Layout

The byte storage of the layout.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LayoutFormat

The format of the data in the Layout column. Values can be: 'U' - uncompressed; 'L' - LZO compressed; 'D' - Deflate compressed. `Required` `Default("U")`

_Type_: **[LayoutFormat](Systems.Core.FormLayouts.md#layoutformat)**  
_Category_: **System**  
Allowed values for the `LayoutFormat`(Systems.Core.FormLayouts.md#layoutformat) data attribute  
_Allowed Values (Systems.Core.FormLayoutsRepository.LayoutFormat Enum Members)_  

| Value | Description |
| ---- | --- |
| CompressedDeflate | CompressedDeflate value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'CompressedDeflate' |
| CompressedLZO | CompressedLZO value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CompressedLZO' |
| Uncompressed | Uncompressed value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Uncompressed' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Uncompressed**  
_Show in UI_: **ShownByDefault**  

### LayoutName

The name of a named layout. Standard layouts have empty string names. `Required` `Filter(eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### LayoutXml

**OBSOLETE! Do not use!** Layout xml - not used. `Obsolete` `Obsoleted in version 22.1.6.61`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### MachineName

**OBSOLETE! Do not use!** The machine name - not used. `Obsolete` `Filter(eq;like)` `Obsoleted in version 22.1.6.61`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PanelName

The visual panel, for which the layout is applied. `Required` `Default("Form")` `Filter(eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: **Form**  
_Show in UI_: **ShownByDefault**  

### UserName

The user for which the layout is applied. null means that the layout is applied for all users. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

The security access key which controls the access to the layout view. `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### InheritFormLayout

Specified when the current layout inherits from another layout. `Filter(multi eq)` `Introduced in version 25.1.1.56`

_Type_: **[FormLayouts](Systems.Core.FormLayouts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Role

The role, for which the layout is applied. `Filter(multi eq)`

_Type_: **[Roles](Systems.Security.Roles.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Core.FormLayouts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.FormLayouts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_FormLayouts

Domain API Entity Type: 
Systems_Core_FormLayout

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_FormLayouts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_FormLayouts?$top=10>

