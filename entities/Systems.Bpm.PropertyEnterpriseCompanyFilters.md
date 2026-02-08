---
uid: Systems.Bpm.PropertyEnterpriseCompanyFilters
---
# Systems.Bpm.PropertyEnterpriseCompanyFilters


Provides a way to apply different filtering of the property allowed values for the different enterprise companies.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.PropertyEnterpriseCompanyFilters  
Base Table: Gen_Property_Enterprise_Company_Filters  
API access:  ReadWrite  

## Renames

Old name: General.PropertyEnterpriseCompanyFilters  
New name: Systems.Bpm.PropertyEnterpriseCompanyFilters  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Property.Name:T}  
Search Members: Property.Name  
Name Member: Property.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  
Aggregate Root:  
[Systems.Bpm.CustomProperties](Systems.Bpm.CustomProperties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FilterXml](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#filterxml) | dataaccessfilter __nullable__ | When not null, specifies a filter for the allowed values of the property for the specified enterprise company.`Unit: obj.Property.AllowedValuesEntityName.IfNullThen(CustomProperty<br />AllowedValuesRepository.TableName)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the current filter is specifed. |
| [Property](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The <see cref="CustomProperty"/> to which this PropertyEnterprise<br />CompanyFilter belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Bpm.PropertyEnterpriseCompanyFilters.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FilterXml

When not null, specifies a filter for the allowed values of the property for the specified enterprise company.`Unit: obj.Property.AllowedValuesEntityName.IfNullThen(CustomPropertyAllowedValuesRepository.TableName)`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
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

### EnterpriseCompany

The enterprise company for which the current filter is specifed.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Property

The <see cref="CustomProperty"/> to which this PropertyEnterpriseCompanyFilter belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=Systems.Bpm.PropertyEnterpriseCompanyFilters erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.PropertyEnterpriseCompanyFilters erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_PropertyEnterpriseCompanyFilters

Domain API Entity Type: 
Systems_Bpm_PropertyEnterpriseCompanyFilter

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_PropertyEnterpriseCompanyFilters?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_PropertyEnterpriseCompanyFilters?$top=10>

