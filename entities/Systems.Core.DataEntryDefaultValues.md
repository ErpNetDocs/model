---
uid: Systems.Core.DataEntryDefaultValues
---
# Systems.Core.DataEntryDefaultValues Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains user-specified default values for columns in data entry forms. Entity: Sys_Default_Values

## Default Visualization
Default Display Text Format:  
_{ColumnName}_  
Default Search Members:  
_ColumnName_  
Name Data Member:  
_ColumnName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.DataEntryDefaultValues](Systems.Core.DataEntryDefaultValues.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Systems.Core.DataEntryDefaultValues.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [ColumnName](Systems.Core.DataEntryDefaultValues.md#columnname) | string (64) | The column for which the default is specified. `Required` `Filter(eq)` 
| [ConditionFormName](Systems.Core.DataEntryDefaultValues.md#conditionformname) | string (64) __nullable__ | If not null specifies that the default should be applied only if Form_Name equals the specified value. `Filter(eq)` `ORD` 
| [ConditionUserLogin](Systems.Core.DataEntryDefaultValues.md#conditionuserlogin) | string (64) __nullable__ | If not null specifies that the default should be applied only if User_Login equals this value. `Filter(eq)` 
| [ConditionUserMachine](Systems.Core.DataEntryDefaultValues.md#conditionusermachine) | string (64) __nullable__ | If not null specifies that the default should be applied only if User_Machine equals this value. `Filter(eq)` 
| [DefaultValueField](Systems.Core.DataEntryDefaultValues.md#defaultvaluefield) | string (254) __nullable__ | The default value for Column_Name. Should be applied only if the other conditions are met. null specifies null default. 
| [DisplayText](Systems.Core.DataEntryDefaultValues.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Core.DataEntryDefaultValues.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.DataEntryDefaultValues.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Core.DataEntryDefaultValues.md#id) | guid |  
| [ObjectVersion](Systems.Core.DataEntryDefaultValues.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PanelName](Systems.Core.DataEntryDefaultValues.md#panelname) | string (64) __nullable__ | When not null, specifies the panel for which the default value applies. `Filter(eq;like)` 
| [TableName](Systems.Core.DataEntryDefaultValues.md#tablename) | string (64) __nullable__ | The table, containing the column for which the default value is specified. `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionDocumentType](Systems.Core.DataEntryDefaultValues.md#conditiondocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | If not null specifies that the default should be applied only if Document_Type_Id equals this value. `Filter(multi eq)` |
| [ConditionEnterpriseCompany](Systems.Core.DataEntryDefaultValues.md#conditionenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | If not null specifies that the default should be applied only if Enterprise_Company_Id equals this value. `Filter(multi eq)` |
| [ConditionRole](Systems.Core.DataEntryDefaultValues.md#conditionrole) | [Roles](Systems.Security.Roles.md) (nullable) | When not null, specifies that the default value should be applied only when the user plays the specified role. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ColumnName

The column for which the default is specified. `Required` `Filter(eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ConditionFormName

If not null specifies that the default should be applied only if Form_Name equals the specified value. `Filter(eq)` `ORD`

_Type_: **string (64) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ConditionUserLogin

If not null specifies that the default should be applied only if User_Login equals this value. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ConditionUserMachine

If not null specifies that the default should be applied only if User_Machine equals this value. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### DefaultValueField

The default value for Column_Name. Should be applied only if the other conditions are met. null specifies null default.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PanelName

When not null, specifies the panel for which the default value applies. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### TableName

The table, containing the column for which the default value is specified. `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ConditionDocumentType

If not null specifies that the default should be applied only if Document_Type_Id equals this value. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ConditionEnterpriseCompany

If not null specifies that the default should be applied only if Enterprise_Company_Id equals this value. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ConditionRole

When not null, specifies that the default value should be applied only when the user plays the specified role. `Filter(multi eq)`

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

