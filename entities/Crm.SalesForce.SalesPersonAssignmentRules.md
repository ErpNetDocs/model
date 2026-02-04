---
uid: Crm.SalesForce.SalesPersonAssignmentRules
---
# Crm.SalesForce.SalesPersonAssignmentRules


Contains rules for automated assignment of sales persons for customers, sales orders, leads, etc.

## General
Namespace: [Crm.SalesForce](Crm.SalesForce.md)  
Repository: Crm.SalesForce.SalesPersonAssignmentRules  
Base Table: Crm_Sales_Person_Assignment_Rules  
Introduced In Version: 25.1.0.17  
API access:  ReadWrite  

## Renames

Old name: Crm.SalesPersonAssignmentRules  
New name: Crm.SalesForce.SalesPersonAssignmentRules  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {EnterpriseCompany} : {RuleNo} - {SalesPerson}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.SalesForce.SalesPersonAssignmentRules](Crm.SalesForce.SalesPersonAssignmentRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplyTo](Crm.SalesForce.SalesPersonAssignmentRules.md#applyto) | [ApplyTo](Crm.SalesForce.SalesPersonAssignmentRules.md#applyto) | Determines whether the rule is applied to customers' definitions (customers and leads) or to documents. `Required` `Default("C")` `Filter(eq)` 
| [FromDate](Crm.SalesForce.SalesPersonAssignmentRules.md#fromdate) | datetime __nullable__ | Starting date of rule validity. null means no from date restriction. `Filter(eq;ge;le)` 
| [IsActive](Crm.SalesForce.SalesPersonAssignmentRules.md#isactive) | boolean | Indicates whether the current rule is active. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Crm.SalesForce.SalesPersonAssignmentRules.md#notes) | string (max) __nullable__ | Additional information or comments related to the rule. `Filter(like)` 
| [Priority](Crm.SalesForce.SalesPersonAssignmentRules.md#priority) | [Priority](Crm.SalesForce.SalesPersonAssignmentRules.md#priority) | Priority when multiple rules match the criteria. `Required` `Default("3")` `Filter(eq)` `Introduced in version 25.1.0.23` 
| [RuleNo](Crm.SalesForce.SalesPersonAssignmentRules.md#ruleno) | int32 | Consecutive number of the rule within the selected enterprise company. `Required` `Filter(eq)` `ORD` 
| [ToDate](Crm.SalesForce.SalesPersonAssignmentRules.md#todate) | datetime __nullable__ | Ending date (inclusive) of rule validity. null means that the rule is valid forever. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyDivision](Crm.SalesForce.SalesPersonAssignmentRules.md#companydivision) | [CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable) | Our division, which is in charge of the deal. `Filter(multi eq)` |
| [CustomerType](Crm.SalesForce.SalesPersonAssignmentRules.md#customertype) | [CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable) | The type of the customer. `Filter(multi eq)` |
| [EnterpriseCompany](Crm.SalesForce.SalesPersonAssignmentRules.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the rule applies. `Required` `Filter(multi eq)` |
| [SalesArea](Crm.SalesForce.SalesPersonAssignmentRules.md#salesarea) | [Areas](General.Geography.Areas.md) (nullable) | The sales area, where the customer is located. `Filter(multi eq)` |
| [SalesPerson](Crm.SalesForce.SalesPersonAssignmentRules.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) | The sales person to be assigned by the rule. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.SalesForce.SalesPersonAssignmentRules.md#id) | guid |  
| [ObjectVersion](Crm.SalesForce.SalesPersonAssignmentRules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.SalesForce.SalesPersonAssignmentRules.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.SalesForce.SalesPersonAssignmentRules.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.SalesForce.SalesPersonAssignmentRules.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.SalesForce.SalesPersonAssignmentRules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplyTo

Determines whether the rule is applied to customers' definitions (customers and leads) or to documents. `Required` `Default("C")` `Filter(eq)`

Type: **[ApplyTo](Crm.SalesForce.SalesPersonAssignmentRules.md#applyto)**  
Category: **System**  
Allowed values for the `ApplyTo`(Crm.SalesForce.SalesPersonAssignmentRules.md#applyto) data attribute  
Allowed Values (Crm.SalesForce.SalesPersonAssignmentRulesRepository.ApplyTo Enum Members)  

| Value | Description |
| ---- | --- |
| Customers | Customers . Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Customers' |
| Documents | Documents . Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 1 <br /> Domain API Value: 'Documents' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Customers**  
Show in UI: **ShownByDefault**  

### FromDate

Starting date of rule validity. null means no from date restriction. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current rule is active. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments related to the rule. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Priority

Priority when multiple rules match the criteria. `Required` `Default("3")` `Filter(eq)` `Introduced in version 25.1.0.23`

Type: **[Priority](Crm.SalesForce.SalesPersonAssignmentRules.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Crm.SalesForce.SalesPersonAssignmentRules.md#priority) data attribute  
Allowed Values (Crm.SalesForce.SalesPersonAssignmentRulesRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Highest | Highest. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'Highest' |
| High | High. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'High' |
| Medium | Medium. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'Medium' |
| Low | Low. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'Low' |
| Lowest | Lowest. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'Lowest' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Medium**  
Show in UI: **ShownByDefault**  

### RuleNo

Consecutive number of the rule within the selected enterprise company. `Required` `Filter(eq)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetRuleNo( obj.EnterpriseCompany)`

Front-End Recalc Expressions:  
`obj.SetRuleNo( obj.EnterpriseCompany)`
### ToDate

Ending date (inclusive) of rule validity. null means that the rule is valid forever. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### CompanyDivision

Our division, which is in charge of the deal. `Filter(multi eq)`

Type: **[CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CustomerType

The type of the customer. `Filter(multi eq)`

Type: **[CustomerTypes](Crm.Sales.CustomerTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company for which the rule applies. `Required` `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SalesArea

The sales area, where the customer is located. `Filter(multi eq)`

Type: **[Areas](General.Geography.Areas.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesPerson

The sales person to be assigned by the rule. `Required` `Filter(multi eq)`

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md)**  
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

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersonAssignmentRules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersonAssignmentRules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_SalesForce_SalesPersonAssignmentRules

Domain API Entity Type: 
Crm_SalesForce_SalesPersonAssignmentRule

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_SalesForce_SalesPersonAssignmentRules?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_SalesForce_SalesPersonAssignmentRules?$top=10>

