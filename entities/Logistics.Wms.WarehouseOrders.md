---
uid: Logistics.Wms.WarehouseOrders
---
# Logistics.Wms.WarehouseOrders


Contains order for internal warehouse operation or plan for execution of warehouse requisition.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseOrders  
Inherited From: [General.Documents.Documents](General.Documents.Documents.md)  
Base Table: Wms_Warehouse_Orders  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentType.TypeName:T} {DocumentNo}{StateTagsAttribute}  
Search Members: DocumentNo  
Code Member: DocumentNo  
Category:  Documents  
Show in UI:  ShownByDefault  
Layout category By:  DocumentTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseOrders](Logistics.Wms.WarehouseOrders.md)  
  * [Logistics.Wms.WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md)  
  * [General.Documents.DocumentAmounts](General.Documents.DocumentAmounts.md)  
    * [General.Documents.DocumentAmountReferencedDocuments](General.Documents.DocumentAmountReferencedDocuments.md)  
  * [General.Documents.DocumentComments](General.Documents.DocumentComments.md)  
  * [General.Documents.DocumentDistributedAmounts](General.Documents.DocumentDistributedAmounts.md)  
  * [General.Documents.DocumentFileAttachments](General.Documents.DocumentFileAttachments.md)  
  * [General.Documents.DocumentFulfillments](General.Documents.DocumentFulfillments.md)  
  * [General.Documents.DocumentLineAmounts](General.Documents.DocumentLineAmounts.md)  
  * [General.Documents.DocumentParties](General.Documents.DocumentParties.md)  
  * [General.Documents.DocumentPrints](General.Documents.DocumentPrints.md)  
  * [General.Documents.DocumentStateChanges](General.Documents.DocumentStateChanges.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AdditionalDetailsJson](Logistics.Wms.WarehouseOrders.md#additionaldetailsjson) | string (max) __nullable__ | Stores additional information for the Warehouse Order in JSON format. The field is intended as a universal container for process-specific data and is populated automatically by the system.`Introduced in version 26.2.1.44` 
| [AdjustmentNumber](Logistics.Wms.WarehouseOrders.md#adjustmentnumber) | int32 | Consecutive number of the correction that this document is applying to the adjusted document. `Required` `Default(0)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [AdjustmentTime](Logistics.Wms.WarehouseOrders.md#adjustmenttime) | datetime __nullable__ | Date/time when the document last has been adjusted by corrective document. `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [AdjustmentUser](Logistics.Wms.WarehouseOrders.md#adjustmentuser) | string (64) __nullable__ | The user who adjusted the document. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [CompleteTime](Logistics.Wms.WarehouseOrders.md#completetime) | datetime __nullable__ | Date and time when the document was completed (State set to Completed). `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [CreationTime](Logistics.Wms.WarehouseOrders.md#creationtime) | datetime | Date/Time when the document was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [CreationUser](Logistics.Wms.WarehouseOrders.md#creationuser) | string (64) | The login name of the user, who created the document. `Required` `Filter(like)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [DocumentDate](Logistics.Wms.WarehouseOrders.md#documentdate) | date | The date on which the document was issued. `Required` `Default(Today)` `Filter(eq;ge;le)` `ORD` (Inherited from [Documents](General.Documents.Documents.md)) 
| [DocumentNo](Logistics.Wms.WarehouseOrders.md#documentno) | string (20) | Document number, unique within Document_Type_Id. `Required` `Filter(eq;like)` `ORD` (Inherited from [Documents](General.Documents.Documents.md)) 
| [DocumentNotes](Logistics.Wms.WarehouseOrders.md#documentnotes) | string (max) __nullable__ | Notes for this Document. (Inherited from [Documents](General.Documents.Documents.md)) 
| [DocumentVersion](Logistics.Wms.WarehouseOrders.md#documentversion) | int32 | Consecutive version number, starting with 1. Each update produces a new version of the document. `Required` `Default(1)` `Filter(eq;ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [EntityName](Logistics.Wms.WarehouseOrders.md#entityname) | string (64) | The entity name of the document header. `Required` `Filter(eq)` `ORD` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [FullState](Logistics.Wms.WarehouseOrders.md#fullstate) | string | Full state of the document based on its system and user state. [ReadOnly] 
| [ParentDocument<br />RelationshipType](Logistics.Wms.WarehouseOrders.md#parentdocumentrelationshiptype) | [ParentDocument<br />RelationshipType](Logistics.Wms.WarehouseOrders.md#parentdocumentrelationshiptype) __nullable__ | Type of relationship between the current document and the parent document(s). Affects the constraints for execution/completion for the documents. Possible values: 'S' = 'Subtask', 'N' = 'Next task'. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [PlanningOnly](Logistics.Wms.WarehouseOrders.md#planningonly) | boolean | Indicates that the document is used only for planning (and as consequence its state cannot be greater than Planned). `Required` `Default(false)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [ReadOnly](Logistics.Wms.WarehouseOrders.md#readonly) | boolean | True - the document is read only; false - the document is not read only. `Required` `Default(false)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [ReferenceDate](Logistics.Wms.WarehouseOrders.md#referencedate) | datetime __nullable__ | Indicates the date, when the event, described by the document, actually occurred. Generally, the document should be created at the date of the event. However, if the document is created later than the event, this field contains the date of the actual event. If the field is empty, this means that the document was created at the date of the actual event and Document Date is indicative of the date of the event. Contrast this with CreationTime, which indicates when the document was entered into the system. So, generally: Reference Date &lt;= DocumentDate &lt;= CreationTime. `Default(Today)` `Filter(ge;le)` (Inherited from [Documents](General.Documents.Documents.md)) 
| [ReferenceDocumentNo](Logistics.Wms.WarehouseOrders.md#referencedocumentno) | string (20) __nullable__ | The number of the document (issued by the other party), which was the reason for the creation of the current document. The number should be unique within the party documents. `Filter(eq;like)` (Inherited from [Documents](General.Documents.Documents.md)) 
| [ReleaseTime](Logistics.Wms.WarehouseOrders.md#releasetime) | datetime __nullable__ | Date and time when the document was released (State set to Released). `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [State](Logistics.Wms.WarehouseOrders.md#state) | [DocumentState](Logistics.Wms.WarehouseOrders.md#state) | The current system state of the document. Allowed values: 0=New;5=Corrective;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed. `Required` `Default(0)` `Filter(multi eq;ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [StateTagsAttribute](Logistics.Wms.WarehouseOrders.md#statetagsattribute) | string | Specifies the state of the document. 
| [TaskType](Logistics.Wms.WarehouseOrders.md#tasktype) | [TaskType](Logistics.Wms.WarehouseOrders.md#tasktype) __nullable__ | The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble.`Filter(multi eq)` `Introduced in version 26.2.0.28` 
| [Void](Logistics.Wms.WarehouseOrders.md#void) | boolean | True if the document is null and void. `Required` `Default(false)` `Filter(eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [VoidReason](Logistics.Wms.WarehouseOrders.md#voidreason) | string (254) __nullable__ | Reason for voiding the document, entered by the user. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [VoidTime](Logistics.Wms.WarehouseOrders.md#voidtime) | datetime __nullable__ | Date/time when the document has become void. `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 
| [VoidUser](Logistics.Wms.WarehouseOrders.md#voiduser) | string (64) __nullable__ | The user who voided the document. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Logistics.Wms.WarehouseOrders.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the user permissions for this document. null means that all users have unlimited permissions. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [AdjustedDocument](Logistics.Wms.WarehouseOrders.md#adjusteddocument) | [Documents](General.Documents.Documents.md) (nullable) | The primary document, which the current document adjusts. null when this is not an adjustment document. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) |
| [AssignedToUser](Logistics.Wms.WarehouseOrders.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | The user to which this document is assigned for handling. null means that the document is not assigned to specific user. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [CurrencyDirectory](Logistics.Wms.WarehouseOrders.md#currencydirectory) | [CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable) | The currency directory, containing all the convertion rates, used by the document. null means that the document does not need currency convertions. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [DocumentType](Logistics.Wms.WarehouseOrders.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The user defined type of the document. Determines document behaviour, properties, additional amounts, validation, generations, etc. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [EnterpriseCompany](Logistics.Wms.WarehouseOrders.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [EnterpriseCompanyLocation](Logistics.Wms.WarehouseOrders.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The branch of the enterprise company that issues the document.  Even when the enterprise company operates with a single branch, it must be explicitly specified. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [FromCompanyDivision](Logistics.Wms.WarehouseOrders.md#fromcompanydivision) | [CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable) | The division of the company, issuing the document. null when the document is not issued by any specific division. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [FromParty](Logistics.Wms.WarehouseOrders.md#fromparty) | [Parties](General.Contacts.Parties.md) | The party which issued the document. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [MasterDocument](Logistics.Wms.WarehouseOrders.md#masterdocument) | [Documents](General.Documents.Documents.md) | In a multi-document tree, this is the root document, that created the whole tree. If this is the root it is equal to Id. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [Parent](Logistics.Wms.WarehouseOrders.md#parent) | [Documents](General.Documents.Documents.md) (nullable) | In a multi-document tree, this is the direct parent document. If this is the root it is null. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [PrimeCauseDocument](Logistics.Wms.WarehouseOrders.md#primecausedocument) | [Documents](General.Documents.Documents.md) (nullable) | The document that is the prime cause for creation of the current document. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [ResponsiblePerson](Logistics.Wms.WarehouseOrders.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | The person that is responsible for this order or transaction. It could be the sales person, the orderer, etc. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [ReverseOfDocument](Logistics.Wms.WarehouseOrders.md#reverseofdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document which the current document is reverse of. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) |
| [Sequence](Logistics.Wms.WarehouseOrders.md#sequence) | [Sequences](Systems.Documents.Sequences.md) (nullable) | The sequence that will be used to give new numbers to the documents of this type. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) |
| [ToCompanyDivision](Logistics.Wms.WarehouseOrders.md#tocompanydivision) | [CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable) | The division of the company, receiving the document. null when the document is not received by any specific division. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [ToParty](Logistics.Wms.WarehouseOrders.md#toparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party which should receive the document. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md)) |
| [UserStatus](Logistics.Wms.WarehouseOrders.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user status of this document if applicable for this document type. null means unknown or not yet set. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md)) |
| [Warehouse](Logistics.Wms.WarehouseOrders.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse, where the order will be executed. |
| [WarehouseWorker](Logistics.Wms.WarehouseOrders.md#warehouseworker) | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable) | When set, denotes that the whole order is assigned to the specified worker. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseOrders.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseOrders.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Wms.WarehouseOrders.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.WarehouseOrders.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Wms.WarehouseOrders.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Wms.WarehouseOrders.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Comments | [DocumentComments](General.Documents.DocumentComments.md) | List of `DocumentComment`(General.Documents.DocumentComments.md) child objects, based on the `General.Documents.DocumentComment.Document`(General.Documents.DocumentComments.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| DistributedAmounts | [DocumentDistributedAmounts](General.Documents.DocumentDistributedAmounts.md) | List of `DocumentDistributed<br />Amount`(General.Documents.DocumentDistributedAmounts.md) child objects, based on the `General.Documents.DocumentDistributedAmount.Document`(General.Documents.DocumentDistributedAmounts.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| DocumentAmounts | [DocumentAmounts](General.Documents.DocumentAmounts.md) | List of `DocumentAmount`(General.Documents.DocumentAmounts.md) child objects, based on the `General.Documents.DocumentAmount.Document`(General.Documents.DocumentAmounts.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| FileAttachments | [DocumentFileAttachments](General.Documents.DocumentFileAttachments.md) | List of `DocumentFileAttachment`(General.Documents.DocumentFileAttachments.md) child objects, based on the `General.Documents.DocumentFileAttachment.Document`(General.Documents.DocumentFileAttachments.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| Fulfillments | [DocumentFulfillments](General.Documents.DocumentFulfillments.md) | List of `DocumentFulfillment`(General.Documents.DocumentFulfillments.md) child objects, based on the `General.Documents.DocumentFulfillment.Document`(General.Documents.DocumentFulfillments.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| LineAmounts | [DocumentLineAmounts](General.Documents.DocumentLineAmounts.md) | List of `DocumentLineAmount`(General.Documents.DocumentLineAmounts.md) child objects, based on the `General.Documents.DocumentLineAmount.Document`(General.Documents.DocumentLineAmounts.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| Lines | [WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) | List of `WarehouseOrderLine`(Logistics.Wms.WarehouseOrderLines.md) child objects, based on the `Logistics.Wms.WarehouseOrderLine.WarehouseOrder`(Logistics.Wms.WarehouseOrderLines.md#warehouseorder) back reference 
| Parties | [DocumentParties](General.Documents.DocumentParties.md) | List of `DocumentParty`(General.Documents.DocumentParties.md) child objects, based on the `General.Documents.DocumentParty.Document`(General.Documents.DocumentParties.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| Prints | [DocumentPrints](General.Documents.DocumentPrints.md) | List of `DocumentPrint`(General.Documents.DocumentPrints.md) child objects, based on the `General.Documents.DocumentPrint.Document`(General.Documents.DocumentPrints.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 
| StateChanges | [DocumentStateChanges](General.Documents.DocumentStateChanges.md) | List of `DocumentStateChange`(General.Documents.DocumentStateChanges.md) child objects, based on the `General.Documents.DocumentStateChange.Document`(General.Documents.DocumentStateChanges.md#document) back reference (Inherited from [Documents](General.Documents.Documents.md)) 


## Attribute Details

### AdditionalDetailsJson

Stores additional information for the Warehouse Order in JSON format. The field is intended as a universal container for process-specific data and is populated automatically by the system.`Introduced in version 26.2.1.44`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### AdjustmentNumber

Consecutive number of the correction that this document is applying to the adjusted document. `Required` `Default(0)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

### AdjustmentTime

Date/time when the document last has been adjusted by corrective document. `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### AdjustmentUser

The user who adjusted the document. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### CompleteTime

Date and time when the document was completed (State set to Completed). `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationTime

Date/Time when the document was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **HiddenByDefault**  

### CreationUser

The login name of the user, who created the document. `Required` `Filter(like)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### DocumentDate

The date on which the document was issued. `Required` `Default(Today)` `Filter(eq;ge;le)` `ORD` (Inherited from [Documents](General.Documents.Documents.md))

Type: **date**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### DocumentNo

Document number, unique within Document_Type_Id. `Required` `Filter(eq;like)` `ORD` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (20)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### DocumentNotes

Notes for this Document. (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### DocumentVersion

Consecutive version number, starting with 1. Each update produces a new version of the document. `Required` `Default(1)` `Filter(eq;ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **HiddenByDefault**  

### EntityName

The entity name of the document header. `Required` `Filter(eq)` `ORD` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **CannotBeShown**  

### FullState

Full state of the document based on its system and user state. [ReadOnly]

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ParentDocumentRelationshipType

Type of relationship between the current document and the parent document(s). Affects the constraints for execution/completion for the documents. Possible values: 'S' = 'Subtask', 'N' = 'Next task'. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[ParentDocument<br />RelationshipType](Logistics.Wms.WarehouseOrders.md#parentdocumentrelationshiptype) __nullable__**  
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
Show in UI: **HiddenByDefault**  

### PlanningOnly

Indicates that the document is used only for planning (and as consequence its state cannot be greater than Planned). `Required` `Default(false)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### ReadOnly

True - the document is read only; false - the document is not read only. `Required` `Default(false)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### ReferenceDate

Indicates the date, when the event, described by the document, actually occurred. Generally, the document should be created at the date of the event. However, if the document is created later than the event, this field contains the date of the actual event. If the field is empty, this means that the document was created at the date of the actual event and Document Date is indicative of the date of the event. Contrast this with CreationTime, which indicates when the document was entered into the system. So, generally: Reference Date &lt;= DocumentDate &lt;= CreationTime. `Default(Today)` `Filter(ge;le)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **HiddenByDefault**  

### ReferenceDocumentNo

The number of the document (issued by the other party), which was the reason for the creation of the current document. The number should be unique within the party documents. `Filter(eq;like)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (20) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **HiddenByDefault**  

### ReleaseTime

Date and time when the document was released (State set to Released). `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### State

The current system state of the document. Allowed values: 0=New;5=Corrective;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed. `Required` `Default(0)` `Filter(multi eq;ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[DocumentState](Logistics.Wms.WarehouseOrders.md#state)**  
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

Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

### StateTagsAttribute

Specifies the state of the document.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### TaskType

The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble.`Filter(multi eq)` `Introduced in version 26.2.0.28`

Type: **[TaskType](Logistics.Wms.WarehouseOrders.md#tasktype) __nullable__**  
Category: **System**  
Allowed values for the `TaskType`(Logistics.Wms.WarehouseOrderLines.md#tasktype) data attribute  
Allowed Values (Logistics.Wms.WarehouseOrderLinesRepository.TaskType Enum Members)  

| Value | Description |
| ---- | --- |
| Receive | Receive value. Stored as 'REC'. <br /> Database Value: 'REC' <br /> Model Value: 0 <br /> Domain API Value: 'Receive' |
| Dispatch | Dispatch value. Stored as 'DIS'. <br /> Database Value: 'DIS' <br /> Model Value: 1 <br /> Domain API Value: 'Dispatch' |
| Move | Move value. Stored as 'MOV'. <br /> Database Value: 'MOV' <br /> Model Value: 2 <br /> Domain API Value: 'Move' |
| Label | Label value. Stored as 'LBL'. <br /> Database Value: 'LBL' <br /> Model Value: 3 <br /> Domain API Value: 'Label' |
| Inspect | Inspect value. Stored as 'INS'. <br /> Database Value: 'INS' <br /> Model Value: 4 <br /> Domain API Value: 'Inspect' |
| Pack | Pack value. Stored as 'PCK'. <br /> Database Value: 'PCK' <br /> Model Value: 5 <br /> Domain API Value: 'Pack' |
| Unpack | Unpack value. Stored as 'UPK'. <br /> Database Value: 'UPK' <br /> Model Value: 6 <br /> Domain API Value: 'Unpack' |
| Kit | Kit value. Stored as 'KIT'. <br /> Database Value: 'KIT' <br /> Model Value: 7 <br /> Domain API Value: 'Kit' |
| Dekit | Dekit value. Stored as 'DKT'. <br /> Database Value: 'DKT' <br /> Model Value: 8 <br /> Domain API Value: 'Dekit' |
| Count | Count value. Stored as 'CNT'. <br /> Database Value: 'CNT' <br /> Model Value: 9 <br /> Domain API Value: 'Count' |
| UserTask | UserTask value. Stored as 'TSK'. <br /> Database Value: 'TSK' <br /> Model Value: 10 <br /> Domain API Value: 'UserTask' |
| ComponentDispatch | ComponentDispatch value. Stored as 'CDP'. <br /> Database Value: 'CDP' <br /> Model Value: 11 <br /> Domain API Value: 'ComponentDispatch' |
| ComponentReceive | ComponentReceive value. Stored as 'CRC'. <br /> Database Value: 'CRC' <br /> Model Value: 12 <br /> Domain API Value: 'ComponentReceive' |
| Assemble | Assemble value. Stored as 'ASM'. <br /> Database Value: 'ASM' <br /> Model Value: 13 <br /> Domain API Value: 'Assemble' |
| Disassemble | Disassemble value. Stored as 'DSM'. <br /> Database Value: 'DSM' <br /> Model Value: 14 <br /> Domain API Value: 'Disassemble' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Lines.Select( c => WarehouseOrderLinesRepository.TaskTypeAttribute.GetUntypedValue( c, False)).Distinct( ).OnlyIfSingle( )`
### Void

True if the document is null and void. `Required` `Default(false)` `Filter(eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **boolean**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### VoidReason

Reason for voiding the document, entered by the user. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### VoidTime

Date/time when the document has become void. `Filter(ge;le)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### VoidUser

The user who voided the document. `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

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

### AccessKey

The access key, containing the user permissions for this document. null means that all users have unlimited permissions. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### AdjustedDocument

The primary document, which the current document adjusts. null when this is not an adjustment document. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### AssignedToUser

The user to which this document is assigned for handling. null means that the document is not assigned to specific user. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CurrencyDirectory

The currency directory, containing all the convertion rates, used by the document. null means that the document does not need currency convertions. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### DocumentType

The user defined type of the document. Determines document behaviour, properties, additional amounts, validation, generations, etc. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

The branch of the enterprise company that issues the document.  Even when the enterprise company operates with a single branch, it must be explicitly specified. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### FromCompanyDivision

The division of the company, issuing the document. null when the document is not issued by any specific division. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### FromParty

The party which issued the document. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### MasterDocument

In a multi-document tree, this is the root document, that created the whole tree. If this is the root it is equal to Id. `Required` `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Parent

In a multi-document tree, this is the direct parent document. If this is the root it is null. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PrimeCauseDocument

The document that is the prime cause for creation of the current document. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ResponsiblePerson

The person that is responsible for this order or transaction. It could be the sales person, the orderer, etc. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ReverseOfDocument

The document which the current document is reverse of. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Sequence

The sequence that will be used to give new numbers to the documents of this type. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Sequences](Systems.Documents.Sequences.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ToCompanyDivision

The division of the company, receiving the document. null when the document is not received by any specific division. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ToParty

The party which should receive the document. `Filter(multi eq)` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.ObtainToParty( )`

### UserStatus

The user status of this document if applicable for this document type. null means unknown or not yet set. `Filter(multi eq)` `ReadOnly` (Inherited from [Documents](General.Documents.Documents.md))

Type: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Warehouse

The warehouse, where the order will be executed.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseWorker

When set, denotes that the whole order is assigned to the specified worker.

Type: **[WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Lines.Select( c => c.WarehouseWorker).Distinct( ).OnlyIfSingle( )`

## API Methods

Methods that can be invoked in public APIs.

### ChangeState

Changes the document state to the specified new state              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **void**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **newState**  
    The desired new state of the document  
    Type: General.Documents.DocumentState  
    Enumeration of document system states  
    Allowed Values (General.Documents.DocumentState Enum Members)  

    | Value | Description |
    | ---- | --- |
    | New | New document, just created. Can be edited. (Stored as 0). <br /> Model Value: 0 <br /> Domain API Value: 'New' |
    | Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> Model Value: 5 <br /> Domain API Value: 'Adjustment' |
    | Planned | Planned by the system for future releasing. (Stored as 10). <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
    | FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
    | Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
    | Completed | Work has completed. (Stored as 40). <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
    | Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |


  * **userStatus**  
    The desired new user status of the document. Can be null.  
    Type: [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md)  
     Optional: True  
    Default Value: null  


The process of changing the document state is very labor intensive and includes              validation, generation of sub-documents and some other document-specific tasks.                          The state changing process might be very time-consuming, usually ranging              from 500 to 5000 milliseconds.                          Document states usually can only be advanced to higher states, but there are              exceptions from this rule. Database settings and configuration options might affect             the allowed state changes.                          Numerous kinds of document-specific and generic exceptions can be thrown during the             process.

### ProcessSingleRoute

Processes the document route.               (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **void**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **route**  
      
    Type: [Routes](Systems.Documents.Routes.md)  

  * **processForLowerDocumentStates**  
      
    Type: boolean  


### Complete

Changes the document state to Completed with all Release-ed sub-documents              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **void**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **completion**  
    How the sub-documents will be completed, if at all  
    Type: General.Documents.DocumentCompletion  
    Determines how Document will be completed  
    Allowed Values (General.Documents.DocumentCompletion Enum Members)  

    | Value | Description |
    | ---- | --- |
    | OnlyDocument | Only the document will be completed <br /> Model Value: 0 <br /> Domain API Value: 'OnlyDocument' |
    | WithAllChildren | The document, along with is sub-documents, will be completed <br /> Model Value: 1 <br /> Domain API Value: 'WithAllChildren' |
    | WithReleasedChildren | The document, along with its Release-ed sub-documents, will be completed <br /> Model Value: 2 <br /> Domain API Value: 'WithReleasedChildren' |



The process of changing the document state is very labor intensive and includes              validation, generation of sub-documents and some other document-specific tasks.                          The state changing process might be very time-consuming, usually ranging              from 500 to 5000 milliseconds.                          Document states usually can only be advanced to higher states, but there are              exceptions from this rule. Database settings and configuration options might affect             the allowed state changes.                          Numerous kinds of document-specific and generic exceptions can be thrown during the             process.

### MakeVoid

Makes the document void. The operation is irreversible.              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **void**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **reason**  
    The reason for voiding the document.  
    Type: string  

  * **voidType**  
    The type of void operation to execute.  
    Type: General.Documents.DocumentsRepositoryBase.VoidType  
    Specifies the type of void operation  
    Allowed Values (General.Documents.DocumentsRepositoryBase.VoidType Enum Members)  

    | Value | Description |
    | ---- | --- |
    | VoidDocument | Void only the document. If there are sub-documents, the operation might fail. <br /> Model Value: 0 <br /> Domain API Value: 'VoidDocument' |
    | VoidWithSubDocuments | Void the document and its non-released sub-documents. If there are released sub-documents, the operation might fail. <br /> Model Value: 1 <br /> Domain API Value: 'VoidWithSubDocuments' |
    | VoidWithReleased<br />SubDocuments | Void the document and all of its sub-documents, even the released ones. <br /> Model Value: 2 <br /> Domain API Value: 'VoidWithReleased<br />SubDocuments' |

     Optional: True  
    Default Value: VoidDocument  

  * **resetParentState**  
    Resets the parent state of document.  
    Type: boolean  
     Optional: True  
    Default Value: True  


### GetPrintout

Gets a document printout as a file. The returned value is Base64 string representation of the file contents.             This method creates `DocumentPrint`(General.Documents.DocumentPrints.md).              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **string**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **fileFormat**  
    The file format: pdf, html, xlsx, xls, docx, txt and png. The default format is 'pdf'.  
    Type: string  
     Optional: True  
    Default Value: pdf  

  * **printout**  
    The printout defined for the document type of the document. If null the default printout of the document type is used.  
    Type: [Printouts](Systems.Documents.Printouts.md)  
     Optional: True  
    Default Value: null  


### Recalculate

The document and all of its owned objects will be altered to become valid.              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **void**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **POST**  

In some cases the objects in child collection of the document depend on values from other child objects.             This method ensures that all child objects are properly validated.             The changes are only in memory and are not committed to the server.

### GetAllParentDocuments

Gets all parent documents, traversing the parent document chain by using the Parent property.              (Inherited from [Documents](General.Documents.Documents.md))  
Return Type: **Collection Of [Documents](General.Documents.Documents.md)**  
Declaring Type: **[Documents](General.Documents.Documents.md)**  
Domain API Request: **GET**  

**Parameters**  
  * **includeSelf**  
    if set to true the current document is included.  
    Type: boolean  
     Optional: True  
    Default Value: False  


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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseOrders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseOrders erp.type=front-end-business-rule default-text="None"]

## Generations

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseOrders erp.type=generation default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseOrders

Domain API Entity Type: 
Logistics_Wms_WarehouseOrder

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseOrders?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseOrders?$top=10>

