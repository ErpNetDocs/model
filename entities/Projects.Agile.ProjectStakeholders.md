---
uid: Projects.Agile.ProjectStakeholders
---
# Projects.Agile.ProjectStakeholders


Contains the stakeholders associated with projects and their project-management characteristics.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.ProjectStakeholders  
Base Table: Apm_Project_Stakeholders  
Introduced In Version: 27.1.1.54  
API access:  ReadWrite  

## Visualization
Display Format: {Project.Name:T}  
Search Members: Project.Name  
Name Member: Project.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Agile.Projects](Projects.Agile.Projects.md)  
Aggregate Root:  
[Projects.Agile.Projects](Projects.Agile.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Attitude](Projects.Agile.ProjectStakeholders.md#attitude) | [Attitude](Projects.Agile.ProjectStakeholders.md#attitude) __nullable__ | Indicates the stakeholder’s current attitude toward the project.`Filter(eq)` |
| [InfluenceLevel](Projects.Agile.ProjectStakeholders.md#influencelevel) | [InfluenceLevel](Projects.Agile.ProjectStakeholders.md#influencelevel) | Indicates the stakeholder’s ability to influence project decisions, execution or outcomes.`Required` `Default(2)` `Filter(eq)` |
| [InterestLevel](Projects.Agile.ProjectStakeholders.md#interestlevel) | [InterestLevel](Projects.Agile.ProjectStakeholders.md#interestlevel) | Indicates how strongly the stakeholder is interested in or affected by the project outcomes.`Required` `Default(2)` `Filter(eq)` |
| [IsActive](Projects.Agile.ProjectStakeholders.md#isactive) | boolean | Indicates whether the stakeholder is currently relevant to the project.`Required` `Default(true)` `Filter(eq)` |
| [Notes](Projects.Agile.ProjectStakeholders.md#notes) | string (max) __nullable__ | Additional information or comments.`Filter(like)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Project](Projects.Agile.ProjectStakeholders.md#project) | [Projects](Projects.Agile.Projects.md) | The project for which the party is identified as a stakeholder. |
| [ProjectArea](Projects.Agile.ProjectStakeholders.md#projectarea) | [ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable) | The project area for which the party is identified as a stakeholder. When not specified, the party is a stakeholder for the entire project. |
| [StakeholderParty](Projects.Agile.ProjectStakeholders.md#stakeholderparty) | [Parties](General.Contacts.Parties.md) | The person or organization that is a stakeholder in the project. |
| [StakeholderRole](Projects.Agile.ProjectStakeholders.md#stakeholderrole) | [StakeholderRoles](Projects.Agile.StakeholderRoles.md) | The role of the stakeholder in the project or in the specified project area. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.ProjectStakeholders.md#id) | guid |  |
| [ObjectVersion](Projects.Agile.ProjectStakeholders.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [DisplayText](Projects.Agile.ProjectStakeholders.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Attitude

Indicates the stakeholder’s current attitude toward the project.`Filter(eq)`

Type: **[Attitude](Projects.Agile.ProjectStakeholders.md#attitude) __nullable__**  
Category: **System**  
Allowed values for the `Attitude`(Projects.Agile.ProjectStakeholders.md#attitude) data attribute  
Allowed Values (Projects.Agile.ProjectStakeholdersRepository.Attitude Enum Members)  

| Value | Description |
| ---- | --- |
| HighlyResistant | Highly Resistant. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'HighlyResistant' |
| Resistant | Resistant. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Resistant' |
| Neutral | Neutral. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Neutral' |
| Supportive | Supportive. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'Supportive' |
| HighlySupportive | Highly Supportive. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'HighlySupportive' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InfluenceLevel

Indicates the stakeholder’s ability to influence project decisions, execution or outcomes.`Required` `Default(2)` `Filter(eq)`

Type: **[InfluenceLevel](Projects.Agile.ProjectStakeholders.md#influencelevel)**  
Category: **System**  
Allowed values for the `InfluenceLevel`(Projects.Agile.ProjectStakeholders.md#influencelevel) data attribute  
Allowed Values (Projects.Agile.ProjectStakeholdersRepository.InfluenceLevel Enum Members)  

| Value | Description |
| ---- | --- |
| Low | Low. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Low' |
| Medium | Medium. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Medium' |
| High | High. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'High' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **2**  
Show in UI: **ShownByDefault**  

### InterestLevel

Indicates how strongly the stakeholder is interested in or affected by the project outcomes.`Required` `Default(2)` `Filter(eq)`

Type: **[InterestLevel](Projects.Agile.ProjectStakeholders.md#interestlevel)**  
Category: **System**  
Allowed values for the `InterestLevel`(Projects.Agile.ProjectStakeholders.md#interestlevel) data attribute  
Allowed Values (Projects.Agile.ProjectStakeholdersRepository.InterestLevel Enum Members)  

| Value | Description |
| ---- | --- |
| Low | Low. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Low' |
| Medium | Medium. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Medium' |
| High | High. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'High' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **2**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the stakeholder is currently relevant to the project.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### Project

The project for which the party is identified as a stakeholder.

Type: **[Projects](Projects.Agile.Projects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ProjectArea

The project area for which the party is identified as a stakeholder. When not specified, the party is a stakeholder for the entire project.

Type: **[ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StakeholderParty

The person or organization that is a stakeholder in the project.

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StakeholderRole

The role of the stakeholder in the project or in the specified project area.

Type: **[StakeholderRoles](Projects.Agile.StakeholderRoles.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Projects.Agile.ProjectStakeholders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.ProjectStakeholders erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_ProjectStakeholders

Domain API Entity Type: 
Projects_Agile_ProjectStakeholder

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_ProjectStakeholders?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_ProjectStakeholders?$top=10>

