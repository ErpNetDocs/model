---
uid: Crm.SalesForce.SalesPersons
---
# Crm.SalesForce.SalesPersons Entity

**Namespace:** [Crm.SalesForce](Crm.SalesForce.md)  

Sales persons (or representatives) are sellers inside the enterprise company who sell the products to customers. Entity: Crm_Sales_Persons

## Renames

Old name: **Crm.SalesPersons**  
New name: **Crm.SalesForce.SalesPersons**  
Version: **25.1.1.36**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{Person.PartyName:T}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.SalesForce.SalesPersons](Crm.SalesForce.SalesPersons.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CommissionPercent](Crm.SalesForce.SalesPersons.md#commissionpercent) | decimal (7, 6) __nullable__ | The percentage (0..1) of commission percent. null means that there is no commission percent. 
| [CommissionPolicyId](Crm.SalesForce.SalesPersons.md#commissionpolicyid) | guid __nullable__ | Current commission policy for the sales person. null means there is no commission policy. `Filter(multi eq)` 
| [ContractEndDate](Crm.SalesForce.SalesPersons.md#contractenddate) | datetime __nullable__ | The ending date of the contract with the sales person. null when the sales person is still active. `Filter(ge;le)` 
| [ContractStartDate](Crm.SalesForce.SalesPersons.md#contractstartdate) | datetime __nullable__ | The starting date of the contract with the sales person. null when it is unknown. `Filter(ge;le)` 
| [DisplayText](Crm.SalesForce.SalesPersons.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.SalesForce.SalesPersons.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.SalesForce.SalesPersons.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.SalesForce.SalesPersons.md#id) | guid |  
| [IsActive](Crm.SalesForce.SalesPersons.md#isactive) | boolean | Specifies whether the sales person is active and should be included in the list when choosing sales person through drop-downs, lists, etc. `Required` `Default(true)` `Filter(eq)` 
| [ObjectVersion](Crm.SalesForce.SalesPersons.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.SalesForce.SalesPersons.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this SalesPerson applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Crm.SalesForce.SalesPersons.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location, to which the sales person is assigned. The sales person is allowed to sell to other locations, but this is the default location. null means that the sales person is not assigned to any enterprise location. `Filter(multi eq)` |
| [Person](Crm.SalesForce.SalesPersons.md#person) | [Persons](General.Contacts.Persons.md) | Base personal record. `Required` `Filter(multi eq)` `FilterableReference` |
| [SalesPersonGroup](Crm.SalesForce.SalesPersons.md#salespersongroup) | [SalesPersonGroups](Crm.SalesForce.SalesPersonGroups.md) | The sales person group to which this sales person is assigned. `Required` `Filter(multi eq)` |


## Attribute Details

### CommissionPercent

The percentage (0..1) of commission percent. null means that there is no commission percent.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CommissionPolicyId

Current commission policy for the sales person. null means there is no commission policy. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### ContractEndDate

The ending date of the contract with the sales person. null when the sales person is still active. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ContractStartDate

The starting date of the contract with the sales person. null when it is unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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

### IsActive

Specifies whether the sales person is active and should be included in the list when choosing sales person through drop-downs, lists, etc. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### EnterpriseCompany

The Enterprise Company to which this SalesPerson applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### EnterpriseCompanyLocation

The enterprise company location, to which the sales person is assigned. The sales person is allowed to sell to other locations, but this is the default location. null means that the sales person is not assigned to any enterprise location. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

Base personal record. `Required` `Filter(multi eq)` `FilterableReference`

_Type_: **[Persons](General.Contacts.Persons.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SalesPersonGroup

The sales person group to which this sales person is assigned. `Required` `Filter(multi eq)`

_Type_: **[SalesPersonGroups](Crm.SalesForce.SalesPersonGroups.md)**  
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

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersons erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersons erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_SalesForce_SalesPersons

Domain API Entity Type: 
Crm_SalesForce_SalesPerson

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_SalesForce_SalesPersons?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_SalesForce_SalesPersons?$top=10>

