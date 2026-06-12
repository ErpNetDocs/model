---
uid: Systems.Internal.Reports
---
# Systems.Internal.Reports Entity

**Namespace:** [Systems.Internal](Systems.Internal.md)  

User-defined reports. Reports retrieve data from data sources and present it in a user-defined layout. Entity: Sys_Reports

## Renames

Old name: **Systems.Reporting.Reports**  
New name: **Systems.Internal.Reports**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Internal.Reports](Systems.Internal.Reports.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Internal.Reports.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Internal.Reports.md#id) | guid |  
| [LayoutFormat](Systems.Internal.Reports.md#layoutformat) | string (32) __nullable__ | Format specifier of the layout. Recognized by the application. `Filter(multi eq)` 
| [Name](Systems.Internal.Reports.md#name) | string (254) | Multi-language report name. `Required` `Filter(eq;like)` 
| [Notes](Systems.Internal.Reports.md#notes) | string (512) __nullable__ | Notes for this Report. 
| [ObjectVersion](Systems.Internal.Reports.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OneRow](Systems.Internal.Reports.md#onerow) | boolean | True means that report can be used for one-row forms only. False means that the report can be used for navigators only. `Required` `Default(false)` `Filter(eq)` 
| [QueryName](Systems.Internal.Reports.md#queryname) | string (128) | The query on which the report is based. `Required` `Filter(eq)` 
| [ReportBinaryLayout](Systems.Internal.Reports.md#reportbinarylayout) | byte[] __nullable__ | The printout layout, when the format requires binary storage. Alternative to Report_Layout. 
| [ReportLayout](Systems.Internal.Reports.md#reportlayout) | string (max) __nullable__ | The textual representation of the printout layout, when the format requires text representation. Alternative to Report_Binary_Layout. 
| [TemplateFilterXml](Systems.Internal.Reports.md#templatefilterxml) | string (max) __nullable__ | Specifies the filter condition, which must be satisfied in order for this report to be prioritized for printing as a template sub-report. null when the current report cannot be used as template sub-report. 
| [TemplatePriority](Systems.Internal.Reports.md#templatepriority) | int32 __nullable__ | Specifies the priority of the current report, relative to other reports. Used only when choosing which report to show as a template subreport, null otherwise. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataSource](Systems.Internal.Reports.md#datasource) | [DataSources](Systems.Documents.DataSources.md) (nullable) | Report data source. If specified should be based on the query in Query_Name. null means that the report is based directly on the query. `Filter(multi eq)` |


## Attribute Details

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

### LayoutFormat

Format specifier of the layout. Recognized by the application. `Filter(multi eq)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **CannotBeShown**  

### Name

Multi-language report name. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Report.

_Type_: **string (512) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **512**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OneRow

True means that report can be used for one-row forms only. False means that the report can be used for navigators only. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### QueryName

The query on which the report is based. `Required` `Filter(eq)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### ReportBinaryLayout

The printout layout, when the format requires binary storage. Alternative to Report_Layout.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### ReportLayout

The textual representation of the printout layout, when the format requires text representation. Alternative to Report_Binary_Layout.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### TemplateFilterXml

Specifies the filter condition, which must be satisfied in order for this report to be prioritized for printing as a template sub-report. null when the current report cannot be used as template sub-report.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### TemplatePriority

Specifies the priority of the current report, relative to other reports. Used only when choosing which report to show as a template subreport, null otherwise.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataSource

Report data source. If specified should be based on the query in Query_Name. null means that the report is based directly on the query. `Filter(multi eq)`

_Type_: **[DataSources](Systems.Documents.DataSources.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Internal.Reports erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Internal.Reports erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Internal_Reports?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Internal_Reports?$top=10>

