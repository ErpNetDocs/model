---
uid: Systems.Documents.Routes
---
# Systems.Documents.Routes


Contains document routes, which specify which document generation procedures will be run upon document events.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.Routes  
Base Table: Wf_Routes  
API access:  ReadWrite  

## Renames

Old name: Systems.Workflow.Routes  
New name: Systems.Documents.Routes  
Version: 24.1.101.1  
Case: 36967  



## Visualization
Display Format: {ProcedureName}  
Search Members: ProcedureName  
Name Member: ProcedureName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActivationDate](Systems.Documents.Routes.md#activationdate) | date | The date from which (including) the route is active. The date is matched against the document date of the generating document. 
| [Active](Systems.Documents.Routes.md#active) | boolean | 1 if the route is active, otherwise 0. 
| [AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes) | [AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes) | Determines the possible types of the generation of the destination document - automatic generation, manually trigerred generation or both. 
| [AllowObsoleteGeneration](Systems.Documents.Routes.md#allowobsoletegeneration) | boolean | Allows the usage of unsupported generation procedures (marked as obsolete) 
| [ConditionFilterXML](Systems.Documents.Routes.md#conditionfilterxml) | dataaccessfilter __nullable__ | Contains filter condition, which the document must match in order to execute the route. 
| [ConditionStatesBitMask](Systems.Documents.Routes.md#conditionstatesbitmask) | [DocumentStateFlags](Systems.Documents.Routes.md#conditionstatesbitmask) | The system states for which to execute the specified route. 
| [ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition) | [ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition) | A - any party; C - connected party: to_party is enterprise company; U - unconnected party - not enterprise company; 
| [DeactivationDate](Systems.Documents.Routes.md#deactivationdate) | date __nullable__ | The date until (including) the route is active. The date is matched against the document date of the generating document. Null means the route does not have a deactivation date. 
| [DestinationState](Systems.Documents.Routes.md#destinationstate) | [DocumentState](Systems.Documents.Routes.md#destinationstate) | 0=New;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed 
| [NegativeConditionFilterXml](Systems.Documents.Routes.md#negativeconditionfilterxml) | dataaccessfilter __nullable__ | The negative condition should NOT be matched by the document in order to execute the route. 
| [Notes](Systems.Documents.Routes.md#notes) | string (254) __nullable__ | Notes for this Route. 
| [ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype) | [ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype) | Determines the default relationship type between the generated document and the parent document. 
| [ProcedureName](Systems.Documents.Routes.md#procedurename) | string (254) | The system code of the generation procedure, which must be executed by the route. 
| [ProcessEvent](Systems.Documents.Routes.md#processevent) | string (254) | Event which triggers the route. Usually the event is change of state. Every document entity may define own custom events as well. 
| [ReadOnly](Systems.Documents.Routes.md#readonly) | boolean | Indicates wheather the destination document shoul be read only. 1 - the destination document is read only 
| [<s>SchemaXML</s>](Systems.Documents.Routes.md#schemaxml) | string (max) __nullable__ | **OBSOLETE! Do not use!** Not used. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionEnterpriseCompany](Systems.Documents.Routes.md#conditionenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company for which this route is activated. |
| [ConditionUserStatus](Systems.Documents.Routes.md#conditionuserstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user-defined status, for which the document route is activated. |
| [DestinationDocumentType](Systems.Documents.Routes.md#destinationdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The type of the document, that will be generated by executing the route. |
| [DestinationEnterprise<br />Company](Systems.Documents.Routes.md#destinationenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company in which to generate the target document. |
| [DestinationEnterprise<br />CompanyLocation](Systems.Documents.Routes.md#destinationenterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location in which to generate the target document. |
| [DestinationUserStatus](Systems.Documents.Routes.md#destinationuserstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user defined status to set to the generated document. |
| [DocumentType](Systems.Documents.Routes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type from which this route originates. Documents from this type generate sub-documents using this route. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.Routes.md#id) | guid |  
| [ObjectVersion](Systems.Documents.Routes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.Routes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| PaymentSlipPayment<br />TransactionsTemplates | [PaymentSlipPaymentTransactionsTemplates](Finance.Payments.PaymentSlipPaymentTransactionsTemplates.md) | List of `PaymentSlipPayment<br />TransactionsTemplate`(Finance.Payments.PaymentSlipPayment<br />TransactionsTemplates.md) child objects, based on the `Finance.Payments.PaymentSlipPayment<br />TransactionsTemplate.Route`(Finance.Payments.PaymentSlipPayment<br />TransactionsTemplates.md#route) back reference 
| SalesOrderPayment<br />OrdersTemplates | [SalesOrderPaymentOrdersTemplates](Crm.Sales.SalesOrderPaymentOrdersTemplates.md) | List of `SalesOrderPayment<br />OrdersTemplate`(Crm.Sales.SalesOrderPayment<br />OrdersTemplates.md) child objects, based on the `Crm.Sales.SalesOrderPayment<br />OrdersTemplate.Route`(Crm.Sales.SalesOrderPayment<br />OrdersTemplates.md#route) back reference 
| TemplateRouteLinks | [TemplateRouteLinks](Finance.Accounting.TemplateRouteLinks.md) | List of `TemplateRouteLink`(Finance.Accounting.TemplateRouteLinks.md) child objects, based on the `Finance.Accounting.TemplateRouteLink.Route`(Finance.Accounting.TemplateRouteLinks.md#route) back reference 
| Templates | [Templates](Finance.Accounting.Templates.md) | List of `Template`(Finance.Accounting.Templates.md) child objects, based on the `Finance.Accounting.Template.Route`(Finance.Accounting.Templates.md#route) back reference 
| TransactionTemplates | [TransactionTemplates](Applications.Rental.TransactionTemplates.md) | List of `TransactionTemplate`(Applications.Rental.TransactionTemplates.md) child objects, based on the `Applications.Rental.TransactionTemplate.Route`(Applications.Rental.TransactionTemplates.md#route) back reference 


## Attribute Details

### ActivationDate

The date from which (including) the route is active. The date is matched against the document date of the generating document.

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### Active

1 if the route is active, otherwise 0.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AllowedGenerationTypes

Determines the possible types of the generation of the destination document - automatic generation, manually trigerred generation or both.

Type: **[AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes)**  
Category: **System**  
Allowed values for the `AllowedGenerationTypes`(Systems.Documents.Routes.md#allowedgenerationtypes) data attribute  
Allowed Values (Systems.Documents.RoutesRepository.AllowedGenerationTypes Enum Members)  

| Value | Description |
| ---- | --- |
| Auto | Auto value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Auto' |
| BothAutoAndManually | BothAutoAndManually value. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 1 <br /> Domain API Value: 'BothAutoAndManually' |
| Manually | Manually value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'Manually' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **BothAutoAndManually**  
Show in UI: **ShownByDefault**  

### AllowObsoleteGeneration

Allows the usage of unsupported generation procedures (marked as obsolete)

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ConditionFilterXML

Contains filter condition, which the document must match in order to execute the route.

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionStatesBitMask

The system states for which to execute the specified route.

Type: **[DocumentStateFlags](Systems.Documents.Routes.md#conditionstatesbitmask)**  
Category: **System**  
Enumeration of document system states that can be combined in bit mask  
Allowed Values (General.Documents.DocumentStateFlags Enum Members)  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 1). <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'New' |
| Planned | Planned by the system for future releasing. (Stored as 2). <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 4). <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 8). <br /> Database Value: 8 <br /> Model Value: 8 <br /> Domain API Value: 'Released' |
| Completed | Work has completed. (Stored as 16). <br /> Database Value: 16 <br /> Model Value: 16 <br /> Domain API Value: 'Completed' |
| Adjustment | Document which adjusts other released documents. (Stored as 32). <br /> Database Value: 32 <br /> Model Value: 32 <br /> Domain API Value: 'Adjustment' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 64). <br /> Database Value: 64 <br /> Model Value: 64 <br /> Domain API Value: 'Closed' |

Supported Filters: **Like**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ConnectedPartyCondition

A - any party; C - connected party: to_party is enterprise company; U - unconnected party - not enterprise company;

Type: **[ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition)**  
Category: **System**  
Allowed values for the `ConnectedPartyCondition`(Systems.Documents.Routes.md#connectedpartycondition) data attribute  
Allowed Values (Systems.Documents.RoutesRepository.ConnectedPartyCondition Enum Members)  

| Value | Description |
| ---- | --- |
| AnyParty | AnyParty value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'AnyParty' |
| ConnectedParty | ConnectedParty value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'ConnectedParty' |
| UnconnectedParty | UnconnectedParty value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 2 <br /> Domain API Value: 'UnconnectedParty' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **AnyParty**  
Show in UI: **ShownByDefault**  

### DeactivationDate

The date until (including) the route is active. The date is matched against the document date of the generating document. Null means the route does not have a deactivation date.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DestinationState

0=New;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed

Type: **[DocumentState](Systems.Documents.Routes.md#destinationstate)**  
Category: **System**  
Enumeration of document system states  
Allowed Values (General.Documents.DocumentState Enum Members)  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NegativeConditionFilterXml

The negative condition should NOT be matched by the document in order to execute the route.

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Route.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ParentDocumentRelationshipType

Determines the default relationship type between the generated document and the parent document.

Type: **[ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype)**  
Category: **System**  
Relationship between parent and child documents  
Allowed Values (General.Documents.ParentDocumentRelationshipType Enum Members)  

| Value | Description |
| ---- | --- |
| Subtask | The child document is a sub-task of the parent document. (Complete child to complete parent) <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'Subtask' |
| NextTask | The child document is next task of the parent document. (Complete parent to complete child) <br /> Database Value: 'N' <br /> Model Value: 1 <br /> Domain API Value: 'NextTask' |
| IndependentTask | The document is not dependent of neither child nor parent document. <br /> Database Value: 'I' <br /> Model Value: 2 <br /> Domain API Value: 'IndependentTask' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Subtask**  
Show in UI: **ShownByDefault**  

### ProcedureName

The system code of the generation procedure, which must be executed by the route.

Type: **string (254)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ProcessEvent

Event which triggers the route. Usually the event is change of state. Every document entity may define own custom events as well.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ReadOnly

Indicates wheather the destination document shoul be read only. 1 - the destination document is read only

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### SchemaXML

**OBSOLETE! Do not use!** Not used.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

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

### ConditionEnterpriseCompany

The enterprise company for which this route is activated.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionUserStatus

The user-defined status, for which the document route is activated.

Type: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DestinationDocumentType

The type of the document, that will be generated by executing the route.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DestinationEnterpriseCompany

The enterprise company in which to generate the target document.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DestinationEnterpriseCompanyLocation

The enterprise company location in which to generate the target document.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DestinationUserStatus

The user defined status to set to the generated document.

Type: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

The document type from which this route originates. Documents from this type generate sub-documents using this route.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
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

[!list limit=1000 erp.entity=Systems.Documents.Routes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.Routes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_Routes

Domain API Entity Type: 
Systems_Documents_Route

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_Routes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_Routes?$top=10>

