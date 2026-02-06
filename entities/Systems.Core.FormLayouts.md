---
uid: Systems.Core.FormLayouts
---
# Systems.Core.FormLayouts


Contains user layouts of the screen forms.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.FormLayouts  
Base Table: Sys_Form_Layouts  
API access:  ReadWrite  

## Renames

Old name: Systems.UI.FormLayouts  
New name: Systems.Core.FormLayouts  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ApplicationName}  
Search Members: ApplicationName  
Name Member: ApplicationName  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.FormLayouts](Systems.Core.FormLayouts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Core.FormLayouts.md#applicationname) | string (64) | The application, which consumes the layout.[Required] [Filter(eq)] [ORD] 
| [Category](Systems.Core.FormLayouts.md#category) | string (36) __nullable__ | The object category for which the layout is applied. Object category is usually user-defined and further divides the objects of a given object type.[Filter(eq)] [Introduced in version 23.1.1.25] 
| [FormName](Systems.Core.FormLayouts.md#formname) | string (128) | The form, for which the layout is applied.[Required] [Filter(eq;like)] 
| [Layout](Systems.Core.FormLayouts.md#layout) | byte[] __nullable__ | The byte storage of the layout. 
| [LayoutFormat](Systems.Core.FormLayouts.md#layoutformat) | [LayoutFormat](Systems.Core.FormLayouts.md#layoutformat) | The format of the data in the Layout column. Values can be: 'U' - uncompressed; 'L' - LZO compressed; 'D' - Deflate compressed.[Required] [Default(&quot;U&quot;)] 
| [LayoutName](Systems.Core.FormLayouts.md#layoutname) | string (64) | The name of a named layout. Standard layouts have empty string names.[Required] [Filter(eq;like)] 
| [<s>LayoutXml</s>](Systems.Core.FormLayouts.md#layoutxml) | string (max) __nullable__ | **OBSOLETE! Do not use!** Layout xml - not used.[Obsolete] [Obsoleted in version 22.1.6.61] 
| [<s>MachineName</s>](Systems.Core.FormLayouts.md#machinename) | string (128) __nullable__ | **OBSOLETE! Do not use!** The machine name - not used.[Obsolete] [Filter(eq;like)] [Obsoleted in version 22.1.6.61] 
| [PanelName](Systems.Core.FormLayouts.md#panelname) | string (64) | The visual panel, for which the layout is applied.[Required] [Default(&quot;Form&quot;)] [Filter(eq)] 
| [UserName](Systems.Core.FormLayouts.md#username) | string (64) __nullable__ | The user for which the layout is applied. NULL means that the layout is applied for all users.[Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Core.FormLayouts.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The security access key which controls the access to the layout view |
| [InheritFormLayout](Systems.Core.FormLayouts.md#inheritformlayout) | [FormLayouts](Systems.Core.FormLayouts.md) (nullable) | Specified when the current layout inherits from another layout |
| [Role](Systems.Core.FormLayouts.md#role) | [Roles](Systems.Security.Roles.md) (nullable) | The role, for which the layout is applied. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.FormLayouts.md#id) | guid |  
| [ObjectVersion](Systems.Core.FormLayouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.FormLayouts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.FormLayouts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.FormLayouts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.FormLayouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplicationName

The application, which consumes the layout.[Required] [Filter(eq)] [ORD]

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Category

The object category for which the layout is applied. Object category is usually user-defined and further divides the objects of a given object type.[Filter(eq)] [Introduced in version 23.1.1.25]

Type: **string (36) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **36**  
Show in UI: **ShownByDefault**  

### FormName

The form, for which the layout is applied.[Required] [Filter(eq;like)]

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Layout

The byte storage of the layout.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LayoutFormat

The format of the data in the Layout column. Values can be: 'U' - uncompressed; 'L' - LZO compressed; 'D' - Deflate compressed.[Required] [Default(&quot;U&quot;)]

Type: **[LayoutFormat](Systems.Core.FormLayouts.md#layoutformat)**  
Category: **System**  
Allowed values for the `LayoutFormat`(Systems.Core.FormLayouts.md#layoutformat) data attribute  
Allowed Values (Systems.Core.FormLayoutsRepository.LayoutFormat Enum Members)  

| Value | Description |
| ---- | --- |
| CompressedDeflate | CompressedDeflate value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'CompressedDeflate' |
| CompressedLZO | CompressedLZO value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'CompressedLZO' |
| Uncompressed | Uncompressed value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 2 <br /> Domain API Value: 'Uncompressed' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Uncompressed**  
Show in UI: **ShownByDefault**  

### LayoutName

The name of a named layout. Standard layouts have empty string names.[Required] [Filter(eq;like)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### LayoutXml

**OBSOLETE! Do not use!** Layout xml - not used.[Obsolete] [Obsoleted in version 22.1.6.61]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### MachineName

**OBSOLETE! Do not use!** The machine name - not used.[Obsolete] [Filter(eq;like)] [Obsoleted in version 22.1.6.61]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### PanelName

The visual panel, for which the layout is applied.[Required] [Default(&quot;Form&quot;)] [Filter(eq)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Default Value: **Form**  
Show in UI: **ShownByDefault**  

### UserName

The user for which the layout is applied. NULL means that the layout is applied for all users.[Filter(eq;like)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### AccessKey

The security access key which controls the access to the layout view

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### InheritFormLayout

Specified when the current layout inherits from another layout

Type: **[FormLayouts](Systems.Core.FormLayouts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Role

The role, for which the layout is applied.

Type: **[Roles](Systems.Security.Roles.md) (nullable)**  
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

