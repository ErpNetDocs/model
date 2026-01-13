---
uid: Systems.Core.ObjectFiles
---
# Systems.Core.ObjectFiles Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains files attached to objects. Entity: Sys_Object_Files

## Default Visualization
Default Display Text Format:  
_{FileName}_  
Default Search Members:  
_FileName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.ObjectFiles](Systems.Core.ObjectFiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessPermission](Systems.Core.ObjectFiles.md#accesspermission) | [AccessPermission](Systems.Core.ObjectFiles.md#accesspermission) | Indicates who has permission to access this file. `Required` `Default("IN")` `Filter(multi eq)` `Introduced in version 24.1.4.56` 
| [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link. `Required` `Default("EMB")` `Filter(multi eq)` `Introduced in version 20.1` 
| [CreationTimeUtc](Systems.Core.ObjectFiles.md#creationtimeutc) | datetime | Time (in UTC), when the file was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Introduced in version 20.1` 
| [DisplayText](Systems.Core.ObjectFiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EmbeddedFileContents](Systems.Core.ObjectFiles.md#embeddedfilecontents) | byte[] __nullable__ | Contains the contents of the file, when it is embedded in the database. null for linked files. 
| [EmbeddedThumbnailContents](Systems.Core.ObjectFiles.md#embeddedthumbnailcontents) | byte[] __nullable__ | Contains the compressed and/or resized contents of the file if applicable. `ReadOnly` `Introduced in version 24.1.1.85` 
| [ExternalId](Systems.Core.ObjectFiles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.ObjectFiles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FileName](Systems.Core.ObjectFiles.md#filename) | string (254) | The file name of the linked or embedded file. `Required` `Filter(eq;like)` 
| [FileSizeBytes](Systems.Core.ObjectFiles.md#filesizebytes) | int32 __nullable__ | The file size in bytes. If empty the file size is unknown. `Introduced in version 22.1.5.46` 
| [Id](Systems.Core.ObjectFiles.md#id) | guid |  
| [LastUpdateTimeUtc](Systems.Core.ObjectFiles.md#lastupdatetimeutc) | datetime | Time (in UTC), when the file was last updated. `Required` `Default(NowUtc)` `Filter(ge;le)` `Introduced in version 20.1` 
| [LinkedFilePath](Systems.Core.ObjectFiles.md#linkedfilepath) | string (1024) __nullable__ | When the file is linked, contains the full path (including the file name) to the linked file. null for embedded files. `Filter(eq;like)` 
| [MediaHeight](Systems.Core.ObjectFiles.md#mediaheight) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1` 
| [MediaType](Systems.Core.ObjectFiles.md#mediatype) | string (128) __nullable__ | For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). null for non-media files. `Introduced in version 20.1` 
| [MediaWidth](Systems.Core.ObjectFiles.md#mediawidth) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1` 
| [Notes](Systems.Core.ObjectFiles.md#notes) | string (max) __nullable__ | User notes for the file attachment. 
| [ObjectVersion](Systems.Core.ObjectFiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PurposeCode](Systems.Core.ObjectFiles.md#purposecode) | string (32) __nullable__ | Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects. `Filter(eq)` 
| [Section](Systems.Core.ObjectFiles.md#section) | string (64) __nullable__ | A section name used to group files. `Introduced in version 21.1.1.84` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Systems.Core.ObjectFiles.md#creationuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who created the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1` |
| [LastUpdateUser](Systems.Core.ObjectFiles.md#lastupdateuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who performed the last update to the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1` |
| [Object](Systems.Core.ObjectFiles.md#object) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object to which the file is attached. `Required` `Filter(multi eq)` |


## Attribute Details

### AccessPermission

Indicates who has permission to access this file. `Required` `Default("IN")` `Filter(multi eq)` `Introduced in version 24.1.4.56`

_Type_: **[AccessPermission](Systems.Core.ObjectFiles.md#accesspermission)**  
_Category_: **System**  
Allowed values for the `AccessPermission`(Systems.Core.ObjectFiles.md#accesspermission) data attribute  
_Allowed Values (Systems.Core.ObjectFilesRepository.AccessPermission Enum Members)_  

| Value | Description |
| ---- | --- |
| Creator | Creator value. Stored as 'CU'. <br /> _Database Value:_ 'CU' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Creator' |
| Internal | Only internal users have access.. Stored as 'IN'. <br /> _Database Value:_ 'IN' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Internal' |
| External | External and internal users have access.. Stored as 'EX'. <br /> _Database Value:_ 'EX' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'External' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Internal**  
_Show in UI_: **ShownByDefault**  

### ContentLocation

The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link. `Required` `Default("EMB")` `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[ContentLocation](Systems.Core.ObjectFiles.md#contentlocation)**  
_Category_: **System**  
Allowed values for the `ContentLocation`(Systems.Core.ObjectFiles.md#contentlocation) data attribute  
_Allowed Values (Systems.Core.ObjectFilesRepository.ContentLocation Enum Members)_  

| Value | Description |
| ---- | --- |
| Embedded | The content is stored in the database. Stored as 'EMB'. <br /> _Database Value:_ 'EMB' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Embedded' |
| InternetUrl | Internet resource location. Stored as 'URL'. <br /> _Database Value:_ 'URL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InternetUrl' |
| FileSystemLink | Path to the file in the local file system. Stored as 'FSL'. <br /> _Database Value:_ 'FSL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FileSystemLink' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Embedded**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

Time (in UTC), when the file was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `Introduced in version 20.1`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EmbeddedFileContents

Contains the contents of the file, when it is embedded in the database. null for linked files.

_Type_: **byte[] __nullable__**  
_Category_: **Delay Loaded Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### EmbeddedThumbnailContents

Contains the compressed and/or resized contents of the file if applicable. `ReadOnly` `Introduced in version 24.1.1.85`

_Type_: **byte[] __nullable__**  
_Category_: **Delay Loaded Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
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

### FileName

The file name of the linked or embedded file. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### FileSizeBytes

The file size in bytes. If empty the file size is unknown. `Introduced in version 22.1.5.46`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LastUpdateTimeUtc

Time (in UTC), when the file was last updated. `Required` `Default(NowUtc)` `Filter(ge;le)` `Introduced in version 20.1`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### LinkedFilePath

When the file is linked, contains the full path (including the file name) to the linked file. null for embedded files. `Filter(eq;like)`

_Type_: **string (1024) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **1024**  
_Show in UI_: **ShownByDefault**  

### MediaHeight

Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MediaType

For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). null for non-media files. `Introduced in version 20.1`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### MediaWidth

Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

User notes for the file attachment.

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

### PurposeCode

Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects. `Filter(eq)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### Section

A section name used to group files. `Introduced in version 21.1.1.84`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreationUser

The user, who created the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LastUpdateUser

The user, who performed the last update to the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Object

The object to which the file is attached. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Systems.Core.ObjectFiles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ObjectFiles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_ObjectFiles

Domain API Entity Type: 
Systems_Core_ObjectFile

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_ObjectFiles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_ObjectFiles?$top=10>

