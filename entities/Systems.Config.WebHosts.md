---
uid: Systems.Config.WebHosts
---
# Systems.Config.WebHosts


Contains the names and https certificates of the different host names used to host sites.

## General
Namespace: [Systems.Config](Systems.Config.md)  
Repository: Systems.Config.WebHosts  
Base Table: Sys_Web_Hosts  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.WebHosts  
New name: Systems.Config.WebHosts  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.WebHosts](Systems.Config.WebHosts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CertificateContents](Systems.Config.WebHosts.md#certificatecontents) | byte[] __nullable__ | The contents of the web host certificate. NULL means to use the server system certificate. 
| [CertificateExpiryDate](Systems.Config.WebHosts.md#certificateexpirydate) | date __nullable__ | The expiry date of the certificate. Can be used to track the expiration of the web host certificates. When NULL, the expiry date was not provided by the user, when uploading the certificate.[Filter(multi eq;ge;le)] 
| [CertificateOriginal<br />Filename](Systems.Config.WebHosts.md#certificateoriginalfilename) | string (254) __nullable__ | The original name of the file, used to upload the certificate. Used only for reference purposes. When NULL, means that the user did not provide that information when uploading the certificate.[Filter(eq;like)] 
| [CertificatePassword](Systems.Config.WebHosts.md#certificatepassword) | string (max) __nullable__ | The password, which should be used to decrypt the certificate. NULL when the certificate has no password or the system certificate is used. 
| [CertificateType](Systems.Config.WebHosts.md#certificatetype) | string (3) | The type of certificate uploaded. Currently, only PFX is supported.[Required] [Default(&quot;PFX&quot;)] [Filter(multi eq)] 
| [Name](Systems.Config.WebHosts.md#name) | string (max) | The unique Internet name of the host. Should NOT include protocol name and should NOT include any forward slashes. This is just the dot-separated host name.[Required] [Filter(multi eq;like)] 
| [Notes](Systems.Config.WebHosts.md#notes) | string (max) __nullable__ | Notes for this WebHost. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Config.WebHosts.md#id) | guid |  
| [ObjectVersion](Systems.Config.WebHosts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Config.WebHosts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.WebHosts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Config.WebHosts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.WebHosts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CertificateContents

The contents of the web host certificate. NULL means to use the server system certificate.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CertificateExpiryDate

The expiry date of the certificate. Can be used to track the expiration of the web host certificates. When NULL, the expiry date was not provided by the user, when uploading the certificate.[Filter(multi eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CertificateOriginalFilename

The original name of the file, used to upload the certificate. Used only for reference purposes. When NULL, means that the user did not provide that information when uploading the certificate.[Filter(eq;like)]

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### CertificatePassword

The password, which should be used to decrypt the certificate. NULL when the certificate has no password or the system certificate is used.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### CertificateType

The type of certificate uploaded. Currently, only PFX is supported.[Required] [Default(&quot;PFX&quot;)] [Filter(multi eq)]

Type: **string (3)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **3**  
Default Value: **PFX**  
Show in UI: **ShownByDefault**  

### Name

The unique Internet name of the host. Should NOT include protocol name and should NOT include any forward slashes. This is just the dot-separated host name.[Required] [Filter(multi eq;like)]

Type: **string (max)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WebHost.

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

[!list limit=1000 erp.entity=Systems.Config.WebHosts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Config.WebHosts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Config_WebHosts

Domain API Entity Type: 
Systems_Config_WebHost

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Config_WebHosts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Config_WebHosts?$top=10>

