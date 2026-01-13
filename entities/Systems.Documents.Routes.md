---
uid: Systems.Documents.Routes
---
# Systems.Documents.Routes Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Contains document routes, which specify which document generation procedures will be run upon document events. Entity: Wf_Routes

## Renames

Old name: **Systems.Workflow.Routes**  
New name: **Systems.Documents.Routes**  
Version: **24.1.101.1**  
Case: **36967**  



## Default Visualization
Default Display Text Format:  
_{ProcedureName}_  
Default Search Members:  
_ProcedureName_  
Name Data Member:  
_ProcedureName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActivationDate](Systems.Documents.Routes.md#activationdate) | date | The date from which (including) the route is active. The date is matched against the document date of the generating document. `Required` `Default(Today)` `Filter(ge;le)` 
| [Active](Systems.Documents.Routes.md#active) | boolean | True if the route is active, otherwise 0. `Required` `Default(true)` `Filter(eq)` 
| [AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes) | [AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes) | Determines the possible types of the generation of the destination document: A=Auto, M=Manual, B=Both (Auto and Manual). `Required` `Default("B")` `Filter(multi eq)` 
| [AllowObsoleteGeneration](Systems.Documents.Routes.md#allowobsoletegeneration) | boolean | Allows the usage of unsupported generation procedures (marked as obsolete). This is a user override of the system prohibition of the usage of obsolete procedures. `Required` `Default(false)` 
| [ConditionFilterXML](Systems.Documents.Routes.md#conditionfilterxml) | dataaccessfilter __nullable__ | Contains filter condition, which the document must match in order to execute the route. `Unit: obj.DocumentType.EntityName` 
| [ConditionStatesBitMask](Systems.Documents.Routes.md#conditionstatesbitmask) | [DocumentStateFlags](Systems.Documents.Routes.md#conditionstatesbitmask) | The system states for which to execute the specified route. `Required` `Default(0)` `Filter(like)` 
| [ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition) | [ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition) | A - any party; C - connected party: to_party is enterprise company; U - unconnected party - not enterprise company;. `Required` `Default("A")` 
| [DeactivationDate](Systems.Documents.Routes.md#deactivationdate) | date __nullable__ | The date until (including) the route is active. The date is matched against the document date of the generating document. Null means the route does not have a deactivation date. `Filter(ge;le)` 
| [DestinationState](Systems.Documents.Routes.md#destinationstate) | [DocumentState](Systems.Documents.Routes.md#destinationstate) | 0=New;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed. `Required` 
| [DisplayText](Systems.Documents.Routes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Documents.Routes.md#id) | guid |  
| [NegativeConditionFilterXml](Systems.Documents.Routes.md#negativeconditionfilterxml) | dataaccessfilter __nullable__ | The negative condition should NOT be matched by the document in order to execute the route. `Unit: obj.DocumentType.EntityName` 
| [Notes](Systems.Documents.Routes.md#notes) | string (254) __nullable__ | Notes for this Route. 
| [ObjectVersion](Systems.Documents.Routes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype) | [ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype) | Determines the default relationship type between the generated document and the parent document. `Required` `Default("S")` 
| [ProcedureName](Systems.Documents.Routes.md#procedurename) | string (254) | The system name of the generation procedure, which must be executed by the route. `Required` 
| [ProcessEvent](Systems.Documents.Routes.md#processevent) | string (254) | Event which triggers the route. Usually the event is change of state. Every document entity may define own custom events. `Required` `Filter(eq)` 
| [ReadOnly](Systems.Documents.Routes.md#readonly) | boolean | Indicates wheather the destination document shoul be read only. true - the destination document is read only. `Required` `Default(false)` 
| [<s>SchemaXML</s>](Systems.Documents.Routes.md#schemaxml) | string (max) __nullable__ | **OBSOLETE! Do not use!** Not used. `Obsolete` `Obsoleted in version 22.1.6.61` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionEnterpriseCompany](Systems.Documents.Routes.md#conditionenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company for which this route is activated. `Filter(multi eq)` |
| [ConditionUserStatus](Systems.Documents.Routes.md#conditionuserstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user-defined status, for which the document route is activated. `Filter(multi eq)` |
| [DestinationDocumentType](Systems.Documents.Routes.md#destinationdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The type of the document, that will be generated by executing the route. `Filter(multi eq)` |
| [DestinationEnterprise<br />Company](Systems.Documents.Routes.md#destinationenterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company in which to generate the target document. `Filter(multi eq)` |
| [DestinationEnterprise<br />CompanyLocation](Systems.Documents.Routes.md#destinationenterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location in which to generate the target document. `Filter(multi eq)` |
| [DestinationUserStatus](Systems.Documents.Routes.md#destinationuserstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user defined status to set to the generated document. `Filter(multi eq)` |
| [DocumentType](Systems.Documents.Routes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type from which this route originates. Documents from this type generate sub-documents using this route. `Required` `Filter(multi eq)` `Owner` |

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

The date from which (including) the route is active. The date is matched against the document date of the generating document. `Required` `Default(Today)` `Filter(ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### Active

True if the route is active, otherwise 0. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AllowedGenerationTypes

Determines the possible types of the generation of the destination document: A=Auto, M=Manual, B=Both (Auto and Manual). `Required` `Default("B")` `Filter(multi eq)`

_Type_: **[AllowedGenerationTypes](Systems.Documents.Routes.md#allowedgenerationtypes)**  
_Category_: **System**  
Allowed values for the `AllowedGenerationTypes`(Systems.Documents.Routes.md#allowedgenerationtypes) data attribute  
_Allowed Values (Systems.Documents.RoutesRepository.AllowedGenerationTypes Enum Members)_  

| Value | Description |
| ---- | --- |
| Auto | Auto value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Auto' |
| BothAutoAndManually | BothAutoAndManually value. Stored as 'B'. <br /> _Database Value:_ 'B' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BothAutoAndManually' |
| Manually | Manually value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Manually' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **BothAutoAndManually**  
_Show in UI_: **ShownByDefault**  

### AllowObsoleteGeneration

Allows the usage of unsupported generation procedures (marked as obsolete). This is a user override of the system prohibition of the usage of obsolete procedures. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ConditionFilterXML

Contains filter condition, which the document must match in order to execute the route. `Unit: obj.DocumentType.EntityName`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConditionStatesBitMask

The system states for which to execute the specified route. `Required` `Default(0)` `Filter(like)`

_Type_: **[DocumentStateFlags](Systems.Documents.Routes.md#conditionstatesbitmask)**  
_Category_: **System**  
Enumeration of document system states that can be combined in bit mask  
_Allowed Values (General.Documents.DocumentStateFlags Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 1). <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'New' |
| Planned | Planned by the system for future releasing. (Stored as 2). <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 4). <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 8). <br /> _Database Value:_ 8 <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'Released' |
| Completed | Work has completed. (Stored as 16). <br /> _Database Value:_ 16 <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'Completed' |
| Adjustment | Document which adjusts other released documents. (Stored as 32). <br /> _Database Value:_ 32 <br /> _Model Value:_ 32 <br /> _Domain API Value:_ 'Adjustment' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 64). <br /> _Database Value:_ 64 <br /> _Model Value:_ 64 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ConnectedPartyCondition

A - any party; C - connected party: to_party is enterprise company; U - unconnected party - not enterprise company;. `Required` `Default("A")`

_Type_: **[ConnectedPartyCondition](Systems.Documents.Routes.md#connectedpartycondition)**  
_Category_: **System**  
Allowed values for the `ConnectedPartyCondition`(Systems.Documents.Routes.md#connectedpartycondition) data attribute  
_Allowed Values (Systems.Documents.RoutesRepository.ConnectedPartyCondition Enum Members)_  

| Value | Description |
| ---- | --- |
| AnyParty | AnyParty value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AnyParty' |
| ConnectedParty | ConnectedParty value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ConnectedParty' |
| UnconnectedParty | UnconnectedParty value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'UnconnectedParty' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **AnyParty**  
_Show in UI_: **ShownByDefault**  

### DeactivationDate

The date until (including) the route is active. The date is matched against the document date of the generating document. Null means the route does not have a deactivation date. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DestinationState

0=New;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed. `Required`

_Type_: **[DocumentState](Systems.Documents.Routes.md#destinationstate)**  
_Category_: **System**  
Enumeration of document system states  
_Allowed Values (General.Documents.DocumentState Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### NegativeConditionFilterXml

The negative condition should NOT be matched by the document in order to execute the route. `Unit: obj.DocumentType.EntityName`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Route.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentDocumentRelationshipType

Determines the default relationship type between the generated document and the parent document. `Required` `Default("S")`

_Type_: **[ParentDocument<br />RelationshipType](Systems.Documents.Routes.md#parentdocumentrelationshiptype)**  
_Category_: **System**  
Relationship between parent and child documents  
_Allowed Values (General.Documents.ParentDocumentRelationshipType Enum Members)_  

| Value | Description |
| ---- | --- |
| Subtask | The child document is a sub-task of the parent document. (Complete child to complete parent) <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Subtask' |
| NextTask | The child document is next task of the parent document. (Complete parent to complete child) <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'NextTask' |
| IndependentTask | The document is not dependent of neither child nor parent document. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'IndependentTask' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Subtask**  
_Show in UI_: **ShownByDefault**  

### ProcedureName

The system name of the generation procedure, which must be executed by the route. `Required`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ProcessEvent

Event which triggers the route. Usually the event is change of state. Every document entity may define own custom events. `Required` `Filter(eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ReadOnly

Indicates wheather the destination document shoul be read only. true - the destination document is read only. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### SchemaXML

**OBSOLETE! Do not use!** Not used. `Obsolete` `Obsoleted in version 22.1.6.61`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  


## Reference Details

### ConditionEnterpriseCompany

The enterprise company for which this route is activated. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ConditionUserStatus

The user-defined status, for which the document route is activated. `Filter(multi eq)`

_Type_: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DestinationDocumentType

The type of the document, that will be generated by executing the route. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DestinationEnterpriseCompany

The enterprise company in which to generate the target document. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DestinationEnterpriseCompanyLocation

The enterprise company location in which to generate the target document. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DestinationUserStatus

The user defined status to set to the generated document. `Filter(multi eq)`

_Type_: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

The document type from which this route originates. Documents from this type generate sub-documents using this route. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

