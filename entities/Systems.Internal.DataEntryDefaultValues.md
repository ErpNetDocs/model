---
uid: Systems.Internal.DataEntryDefaultValues
---
# Systems.Internal.DataEntryDefaultValues Entity

**Namespace:** [Systems.Internal](Systems.Internal.md)  

Contains user-specified default values for columns in data entry forms. Entity: Sys_Default_Values

## Renames

Old name: **Systems.Core.DataEntryDefaultValues**  
New name: **Systems.Internal.DataEntryDefaultValues**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{ColumnName}_  
Default Search Members:  
_ColumnName_  
Name Data Member:  
_ColumnName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Internal.DataEntryDefaultValues](Systems.Internal.DataEntryDefaultValues.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ColumnName](Systems.Internal.DataEntryDefaultValues.md#columnname) | string (64) | The column for which the default is specified. `Required` `Filter(eq)` 
| [ConditionFormName](Systems.Internal.DataEntryDefaultValues.md#conditionformname) | string (64) __nullable__ | If not null specifies that the default should be applied only if Form_Name equals the specified value. `Filter(eq)` `ORD` 
| [ConditionUserLogin](Systems.Internal.DataEntryDefaultValues.md#conditionuserlogin) | string (64) __nullable__ | If not null specifies that the default should be applied only if User_Login equals this value. `Filter(eq)` 
| [ConditionUserMachine](Systems.Internal.DataEntryDefaultValues.md#conditionusermachine) | string (64) __nullable__ | If not null specifies that the default should be applied only if User_Machine equals this value. `Filter(eq)` 
| [DefaultValueField](Systems.Internal.DataEntryDefaultValues.md#defaultvaluefield) | string (254) __nullable__ | The default value for Column_Name. Should be applied only if the other conditions are met. null specifies null default. 
| [DisplayText](Systems.Internal.DataEntryDefaultValues.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Internal.DataEntryDefaultValues.md#id) | guid |  
| [ObjectVersion](Systems.Internal.DataEntryDefaultValues.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PanelName](Systems.Internal.DataEntryDefaultValues.md#panelname) | string (64) __nullable__ | When not null, specifies the panel for which the default value applies. `Filter(eq;like)` 
| [TableName](Systems.Internal.DataEntryDefaultValues.md#tablename) | string (64) __nullable__ | The table, containing the column for which the default value is specified. `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionDocumentType](Systems.Internal.DataEntryDefaultValues.md#conditiondocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | If not null specifies that the default should be applied only if Document_Type_Id equals this value. `Filter(multi eq)` |
| [ConditionEnterpriseCompany](Systems.Internal.DataEntryDefaultValues.md#conditionenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | If not null specifies that the default should be applied only if Enterprise_Company_Id equals this value. `Filter(multi eq)` |
| [ConditionRole](Systems.Internal.DataEntryDefaultValues.md#conditionrole) | [Roles](Systems.Security.Roles.md) (nullable) | When not null, specifies that the default value should be applied only when the user plays the specified role. `Filter(multi eq)` |


## Attribute Details

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Internal.DataEntryDefaultValues erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Internal.DataEntryDefaultValues erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Internal_DataEntryDefaultValues?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Internal_DataEntryDefaultValues?$top=10>

