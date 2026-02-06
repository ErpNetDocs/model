---
uid: Systems.Core.DataEntryDefaultValues
---
# Systems.Core.DataEntryDefaultValues


Contains user-specified default values for columns in data entry forms.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.DataEntryDefaultValues  
Base Table: Sys_Default_Values  
API access:  ReadWrite  

## Visualization
Display Format: {ColumnName}  
Search Members: ColumnName  
Name Member: ColumnName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.DataEntryDefaultValues](Systems.Core.DataEntryDefaultValues.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ColumnName](Systems.Core.DataEntryDefaultValues.md#columnname) | string (64) | The column for which the default is specified[Required] [Filter(eq)] 
| [ConditionFormName](Systems.Core.DataEntryDefaultValues.md#conditionformname) | string (64) __nullable__ | If not NULL specifies that the default should be applied only if Form_Name equals the specified value[Filter(eq)] [ORD] 
| [ConditionUserLogin](Systems.Core.DataEntryDefaultValues.md#conditionuserlogin) | string (64) __nullable__ | If not NULL specifies that the default should be applied only if User_Login equals this value[Filter(eq)] 
| [ConditionUserMachine](Systems.Core.DataEntryDefaultValues.md#conditionusermachine) | string (64) __nullable__ | If not NULL specifies that the default should be applied only if User_Machine equals this value[Filter(eq)] 
| [DefaultValueField](Systems.Core.DataEntryDefaultValues.md#defaultvaluefield) | string (254) __nullable__ | The default value for Column_Name. Should be applied only if the other conditions are met. NULL specifies NULL default 
| [PanelName](Systems.Core.DataEntryDefaultValues.md#panelname) | string (64) __nullable__ | When not null, specifies the panel for which the default value applies.[Filter(eq;like)] 
| [TableName](Systems.Core.DataEntryDefaultValues.md#tablename) | string (64) __nullable__ | The table, containing the column for which the default value is specified.[Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionDocumentType](Systems.Core.DataEntryDefaultValues.md#conditiondocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | If not NULL specifies that the default should be applied only if Document_Type_Id equals this value |
| [ConditionEnterpriseCompany](Systems.Core.DataEntryDefaultValues.md#conditionenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | If not NULL specifies that the default should be applied only if Enterprise_Company_Id equals this value |
| [ConditionRole](Systems.Core.DataEntryDefaultValues.md#conditionrole) | [Roles](Systems.Security.Roles.md) (nullable) | When not null, specifies that the default value should be applied only when the user plays the specified role. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.DataEntryDefaultValues.md#id) | guid |  
| [ObjectVersion](Systems.Core.DataEntryDefaultValues.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.DataEntryDefaultValues.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.DataEntryDefaultValues.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.DataEntryDefaultValues.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.DataEntryDefaultValues.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ColumnName

The column for which the default is specified[Required] [Filter(eq)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ConditionFormName

If not NULL specifies that the default should be applied only if Form_Name equals the specified value[Filter(eq)] [ORD]

Type: **string (64) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ConditionUserLogin

If not NULL specifies that the default should be applied only if User_Login equals this value[Filter(eq)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ConditionUserMachine

If not NULL specifies that the default should be applied only if User_Machine equals this value[Filter(eq)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### DefaultValueField

The default value for Column_Name. Should be applied only if the other conditions are met. NULL specifies NULL default

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PanelName

When not null, specifies the panel for which the default value applies.[Filter(eq;like)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### TableName

The table, containing the column for which the default value is specified.[Filter(eq)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
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

### ConditionDocumentType

If not NULL specifies that the default should be applied only if Document_Type_Id equals this value

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionEnterpriseCompany

If not NULL specifies that the default should be applied only if Enterprise_Company_Id equals this value

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionRole

When not null, specifies that the default value should be applied only when the user plays the specified role.

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

[!list limit=1000 erp.entity=Systems.Core.DataEntryDefaultValues erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.DataEntryDefaultValues erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_DataEntryDefaultValues

Domain API Entity Type: 
Systems_Core_DataEntryDefaultValue

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_DataEntryDefaultValues?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_DataEntryDefaultValues?$top=10>

