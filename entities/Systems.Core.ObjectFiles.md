---
uid: Systems.Core.ObjectFiles
---
# Systems.Core.ObjectFiles


Contains files attached to objects

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.ObjectFiles  
Base Table: Sys_Object_Files  
API access:  ReadWrite  

## Visualization
Display Format: {FileName}  
Search Members: FileName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.ObjectFiles](Systems.Core.ObjectFiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessPermission](Systems.Core.ObjectFiles.md#accesspermission) | [AccessPermission](Systems.Core.ObjectFiles.md#accesspermission) | Indicates who has permission to access this file.[Required] [Default(&quot;IN&quot;)] [Filter(multi eq)] [Introduced in version 24.1.4.56] 
| [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link.[Required] [Default(&quot;EMB&quot;)] [Filter(multi eq)] [Introduced in version 20.1] 
| [CreationTimeUtc](Systems.Core.ObjectFiles.md#creationtimeutc) | datetime | Time (in UTC), when the file was created.[Required] [Default(NowUtc)] [Filter(ge;le)] [Introduced in version 20.1] 
| [EmbeddedFileContents](Systems.Core.ObjectFiles.md#embeddedfilecontents) | byte[] __nullable__ | Contains the contents of the file, when it is embedded in the database. NULL for linked files 
| [EmbeddedThumbnailContents](Systems.Core.ObjectFiles.md#embeddedthumbnailcontents) | byte[] __nullable__ | Contains the compressed and/or resized contents of the file if applicable.[ReadOnly] [Introduced in version 24.1.1.85] 
| [FileName](Systems.Core.ObjectFiles.md#filename) | string (254) | The file name of the linked or embedded file[Required] [Filter(eq;like)] 
| [FileSizeBytes](Systems.Core.ObjectFiles.md#filesizebytes) | int32 __nullable__ | The file size in bytes. If empty the file size is unknown.[Introduced in version 22.1.5.46] 
| [LastUpdateTimeUtc](Systems.Core.ObjectFiles.md#lastupdatetimeutc) | datetime | Time (in UTC), when the file was last updated.[Required] [Default(NowUtc)] [Filter(ge;le)] [Introduced in version 20.1] 
| [LinkedFilePath](Systems.Core.ObjectFiles.md#linkedfilepath) | string (1024) __nullable__ | When the file is linked, contains the full path (including the file name) to the linked file. NULL for embedded files[Filter(eq;like)] 
| [MediaHeight](Systems.Core.ObjectFiles.md#mediaheight) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media.[Introduced in version 20.1] 
| [MediaType](Systems.Core.ObjectFiles.md#mediatype) | string (128) __nullable__ | For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). NULL for non-media files.[Introduced in version 20.1] 
| [MediaWidth](Systems.Core.ObjectFiles.md#mediawidth) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media.[Introduced in version 20.1] 
| [Notes](Systems.Core.ObjectFiles.md#notes) | string (max) __nullable__ | User notes for the file attachment 
| [PurposeCode](Systems.Core.ObjectFiles.md#purposecode) | string (32) __nullable__ | Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects.[Filter(eq)] 
| [Section](Systems.Core.ObjectFiles.md#section) | string (64) __nullable__ | A section name used to group files[Introduced in version 21.1.1.84] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Systems.Core.ObjectFiles.md#creationuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who created the file record. NULL if it is unknown. |
| [LastUpdateUser](Systems.Core.ObjectFiles.md#lastupdateuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who performed the last update to the file record. NULL if it is unknown. |
| [Object](Systems.Core.ObjectFiles.md#object) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object to which the file is attached |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ObjectFiles.md#id) | guid |  
| [ObjectVersion](Systems.Core.ObjectFiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.ObjectFiles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.ObjectFiles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.ObjectFiles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.ObjectFiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AccessPermission

Indicates who has permission to access this file.[Required] [Default(&quot;IN&quot;)] [Filter(multi eq)] [Introduced in version 24.1.4.56]

Type: **[AccessPermission](Systems.Core.ObjectFiles.md#accesspermission)**  
Category: **System**  
Allowed values for the `AccessPermission`(Systems.Core.ObjectFiles.md#accesspermission) data attribute  
Allowed Values (Systems.Core.ObjectFilesRepository.AccessPermission Enum Members)  

| Value | Description |
| ---- | --- |
| Creator | Creator value. Stored as 'CU'. <br /> Database Value: 'CU' <br /> Model Value: 0 <br /> Domain API Value: 'Creator' |
| Internal | Only internal users have access.. Stored as 'IN'. <br /> Database Value: 'IN' <br /> Model Value: 1 <br /> Domain API Value: 'Internal' |
| External | External and internal users have access.. Stored as 'EX'. <br /> Database Value: 'EX' <br /> Model Value: 2 <br /> Domain API Value: 'External' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Internal**  
Show in UI: **ShownByDefault**  

### ContentLocation

The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link.[Required] [Default(&quot;EMB&quot;)] [Filter(multi eq)] [Introduced in version 20.1]

Type: **[ContentLocation](Systems.Core.ObjectFiles.md#contentlocation)**  
Category: **System**  
Allowed values for the `ContentLocation`(Systems.Core.ObjectFiles.md#contentlocation) data attribute  
Allowed Values (Systems.Core.ObjectFilesRepository.ContentLocation Enum Members)  

| Value | Description |
| ---- | --- |
| Embedded | The content is stored in the database. Stored as 'EMB'. <br /> Database Value: 'EMB' <br /> Model Value: 0 <br /> Domain API Value: 'Embedded' |
| InternetUrl | Internet resource location. Stored as 'URL'. <br /> Database Value: 'URL' <br /> Model Value: 1 <br /> Domain API Value: 'InternetUrl' |
| FileSystemLink | Path to the file in the local file system. Stored as 'FSL'. <br /> Database Value: 'FSL' <br /> Model Value: 2 <br /> Domain API Value: 'FileSystemLink' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Embedded**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

Time (in UTC), when the file was created.[Required] [Default(NowUtc)] [Filter(ge;le)] [Introduced in version 20.1]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### EmbeddedFileContents

Contains the contents of the file, when it is embedded in the database. NULL for linked files

Type: **byte[] __nullable__**  
Category: **Delay Loaded Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EmbeddedThumbnailContents

Contains the compressed and/or resized contents of the file if applicable.[ReadOnly] [Introduced in version 24.1.1.85]

Type: **byte[] __nullable__**  
Category: **Delay Loaded Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### FileName

The file name of the linked or embedded file[Required] [Filter(eq;like)]

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### FileSizeBytes

The file size in bytes. If empty the file size is unknown.[Introduced in version 22.1.5.46]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LastUpdateTimeUtc

Time (in UTC), when the file was last updated.[Required] [Default(NowUtc)] [Filter(ge;le)] [Introduced in version 20.1]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### LinkedFilePath

When the file is linked, contains the full path (including the file name) to the linked file. NULL for embedded files[Filter(eq;like)]

Type: **string (1024) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **1024**  
Show in UI: **ShownByDefault**  

### MediaHeight

Used (non-null) only for media files. Specifies the width for displaying the media.[Introduced in version 20.1]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MediaType

For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). NULL for non-media files.[Introduced in version 20.1]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### MediaWidth

Used (non-null) only for media files. Specifies the width for displaying the media.[Introduced in version 20.1]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

User notes for the file attachment

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PurposeCode

Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects.[Filter(eq)]

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Section

A section name used to group files[Introduced in version 21.1.1.84]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### CreationUser

The user, who created the file record. NULL if it is unknown.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LastUpdateUser

The user, who performed the last update to the file record. NULL if it is unknown.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Object

The object to which the file is attached

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
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

