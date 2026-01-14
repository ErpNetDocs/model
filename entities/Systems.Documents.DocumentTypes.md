---
uid: Systems.Documents.DocumentTypes
---
# Systems.Documents.DocumentTypes Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

List of user-defined document types. Each type has associated system entity (object class). Entity: Gen_Document_Types

## Renames

Old name: **General.DocumentTypes**  
New name: **Systems.Documents.DocumentTypes**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{TypeName:T}_  
Default Search Members:  
_Code; TypeName_  
Code Data Member:  
_Code_  
Name Data Member:  
_TypeName_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _EntityName_  

## Track Changes  
Min level:  _4 - Track object attribute and blob changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
  * [Crm.Invoicing.InvoicesOptions](Crm.Invoicing.InvoicesOptions.md)  
  * [Crm.Presales.OffersOptions](Crm.Presales.OffersOptions.md)  
  * [Crm.Sales.DefaultSalesOrderDocumentProperties](Crm.Sales.DefaultSalesOrderDocumentProperties.md)  
  * [Crm.Sales.DefaultSalesOrderPaymentPlans](Crm.Sales.DefaultSalesOrderPaymentPlans.md)  
  * [Crm.Sales.DocumentTypePaymentOptions](Crm.Sales.DocumentTypePaymentOptions.md)  
  * [Crm.Sales.SalesOrdersOptions](Crm.Sales.SalesOrdersOptions.md)  
  * [Logistics.Inventory.CostCorrectionsOptions](Logistics.Inventory.CostCorrectionsOptions.md)  
  * [Logistics.Inventory.TransferOrdersOptions](Logistics.Inventory.TransferOrdersOptions.md)  
  * [Production.ShopFloor.WorkOrderDocumentTypesOptions](Production.ShopFloor.WorkOrderDocumentTypesOptions.md)  
  * [Logistics.Procurement.PurchaseInvoicesOptions](Logistics.Procurement.PurchaseInvoicesOptions.md)  
  * [Systems.Documents.DocumentTypeAmounts](Systems.Documents.DocumentTypeAmounts.md)  
  * [Systems.Documents.DocumentTypeEnterpriseCompanies](Systems.Documents.DocumentTypeEnterpriseCompanies.md)  
  * [Systems.Documents.DocumentTypeNotifications](Systems.Documents.DocumentTypeNotifications.md)  
  * [Systems.Documents.DocumentTypeProperties](Systems.Documents.DocumentTypeProperties.md)  
  * [Systems.Documents.DocumentTypeSecurityConditions](Systems.Documents.DocumentTypeSecurityConditions.md)  
  * [Systems.Documents.DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md)  
  * [Systems.Documents.Printouts](Systems.Documents.Printouts.md)  
  * [Systems.Documents.Routes](Systems.Documents.Routes.md)  
    * [Finance.Accounting.TemplateRouteLinks](Finance.Accounting.TemplateRouteLinks.md)  
    * [Finance.Accounting.Templates](Finance.Accounting.Templates.md)  
      * [Finance.Accounting.TemplateLines](Finance.Accounting.TemplateLines.md)  
        * [Finance.Accounting.TemplateLineProperties](Finance.Accounting.TemplateLineProperties.md)  
    * [Finance.Payments.PaymentSlipPaymentTransactionsTemplates](Finance.Payments.PaymentSlipPaymentTransactionsTemplates.md)  
    * [Crm.Sales.SalesOrderPaymentOrdersTemplates](Crm.Sales.SalesOrderPaymentOrdersTemplates.md)  
    * [Applications.Rental.TransactionTemplates](Applications.Rental.TransactionTemplates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Systems.Documents.DocumentTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](Systems.Documents.DocumentTypes.md#code) | string (16) | Unique descriptive code of the document type. `Required` `Filter(eq;like)` `ORD` 
| [CreateFulfillments<br />OnCompletion](Systems.Documents.DocumentTypes.md#createfulfillmentsoncompletion) | boolean | When document state is changed to Completed, creates completed document fulfillments for the parent document. Used only for logistic documents. `Required` `Default(false)` `Introduced in version 23.1.2.9` 
| [CreateManully](Systems.Documents.DocumentTypes.md#createmanully) | boolean | False if documents with this document type only can be generated; true - the user can create documents with this type. `Required` `Default(true)` `Filter(eq)` 
| [Description](Systems.Documents.DocumentTypes.md#description) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The description of this DocumentType. 
| [DisallowOpposite<br />ValuesGeneration](Systems.Documents.DocumentTypes.md#disallowoppositevaluesgeneration) | boolean | Disallow the generation of decreasing scalar values (values with opposite directions than the original values determined by the parent document) through this document type. `Required` `Default(false)` 
| [DisplayText](Systems.Documents.DocumentTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityName](Systems.Documents.DocumentTypes.md#entityname) | string (64) | System entity, which contains the documents. `Required` `Filter(multi eq)` `ORD` 
| [ExternalId](Systems.Documents.DocumentTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Documents.DocumentTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [GenerateSingleDocument](Systems.Documents.DocumentTypes.md#generatesingledocument) | boolean | Create maximum one document when documents from this type are generated by parent documents (usually from another document type). `Required` `Default(false)` 
| [Id](Systems.Documents.DocumentTypes.md#id) | guid |  
| [Notes](Systems.Documents.DocumentTypes.md#notes) | string (254) __nullable__ | Notes for this DocumentType. 
| [ObjectVersion](Systems.Documents.DocumentTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SchemaXML](Systems.Documents.DocumentTypes.md#schemaxml) | string (max) __nullable__ | Obsolete. Not used. 
| [TrackAttributeChanges](Systems.Documents.DocumentTypes.md#trackattributechanges) | [TrackAttributeChanges](Systems.Documents.DocumentTypes.md#trackattributechanges) | Enable/disable attributes change tracking for documents from this type. "Default" means that changes will be tracked for all documents, except transit and adjustment documents. `Required` `Default("DEF")` `Filter(eq)` `Introduced in version 24.1.3.37` 
| [TrackPrintImages](Systems.Documents.DocumentTypes.md#trackprintimages) | [TrackPrintImages](Systems.Documents.DocumentTypes.md#trackprintimages) | Enable/disable print images tracking for documents from this type. `Required` `Default("SDC")` `Filter(eq)` `Introduced in version 24.1.3.95` 
| [TransitionalDocument](Systems.Documents.DocumentTypes.md#transitionaldocument) | boolean | If checked determines that the documents from this type are automatically managed by the system and don't require management from the users. `Required` `Default(false)` 
| [TypeName](Systems.Documents.DocumentTypes.md#typename) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Description of the document type. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Documents.DocumentTypes.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this DocumentType. An empty value means that all users have unlimited permissions. `Filter(multi eq)` |
| [Sequence](Systems.Documents.DocumentTypes.md#sequence) | [Sequences](Systems.Documents.Sequences.md) (nullable) | The sequence that will be used to give new numbers to the documents of this type. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Amounts | [DocumentTypeAmounts](Systems.Documents.DocumentTypeAmounts.md) | List of `DocumentTypeAmount`(Systems.Documents.DocumentTypeAmounts.md) child objects, based on the `Systems.Documents.DocumentTypeAmount.DocumentType`(Systems.Documents.DocumentTypeAmounts.md#documenttype) back reference 
| CostCorrectionsOptions | [CostCorrectionsOptions](Logistics.Inventory.CostCorrectionsOptions.md) | List of `CostCorrectionsOption`(Logistics.Inventory.CostCorrectionsOptions.md) child objects, based on the `Logistics.Inventory.CostCorrectionsOption.DocumentType`(Logistics.Inventory.CostCorrectionsOptions.md#documenttype) back reference 
| DefaultSalesOrder<br />DocumentProperties | [DefaultSalesOrderDocumentProperties](Crm.Sales.DefaultSalesOrderDocumentProperties.md) | List of `DefaultSalesOrder<br />DocumentProperty`(Crm.Sales.DefaultSalesOrder<br />DocumentProperties.md) child objects, based on the `Crm.Sales.DefaultSalesOrder<br />DocumentProperty.DocumentType`(Crm.Sales.DefaultSalesOrder<br />DocumentProperties.md#documenttype) back reference 
| DefaultSalesOrder<br />PaymentPlans | [DefaultSalesOrderPaymentPlans](Crm.Sales.DefaultSalesOrderPaymentPlans.md) | List of `DefaultSalesOrder<br />PaymentPlan`(Crm.Sales.DefaultSalesOrder<br />PaymentPlans.md) child objects, based on the `Crm.Sales.DefaultSalesOrder<br />PaymentPlan.DocumentType`(Crm.Sales.DefaultSalesOrder<br />PaymentPlans.md#documenttype) back reference 
| DocumentTypeProperties | [DocumentTypeProperties](Systems.Documents.DocumentTypeProperties.md) | List of `DocumentTypeProperty`(Systems.Documents.DocumentTypeProperties.md) child objects, based on the `Systems.Documents.DocumentTypeProperty.DocumentType`(Systems.Documents.DocumentTypeProperties.md#documenttype) back reference 
| EnterpriseCompanies | [DocumentTypeEnterpriseCompanies](Systems.Documents.DocumentTypeEnterpriseCompanies.md) | List of `DocumentTypeEnterprise<br />Company`(Systems.Documents.DocumentTypeEnterprise<br />Companies.md) child objects, based on the `Systems.Documents.DocumentTypeEnterprise<br />Company.DocumentType`(Systems.Documents.DocumentTypeEnterprise<br />Companies.md#documenttype) back reference 
| InvoicesOptions | [InvoicesOptions](Crm.Invoicing.InvoicesOptions.md) | List of `InvoicesOption`(Crm.Invoicing.InvoicesOptions.md) child objects, based on the `Crm.Invoicing.InvoicesOption.DocumentType`(Crm.Invoicing.InvoicesOptions.md#documenttype) back reference 
| Notifications | [DocumentTypeNotifications](Systems.Documents.DocumentTypeNotifications.md) | List of `DocumentTypeNotification`(Systems.Documents.DocumentTypeNotifications.md) child objects, based on the `Systems.Documents.DocumentTypeNotification.DocumentType`(Systems.Documents.DocumentTypeNotifications.md#documenttype) back reference 
| OffersOptions | [OffersOptions](Crm.Presales.OffersOptions.md) | List of `OffersOption`(Crm.Presales.OffersOptions.md) child objects, based on the `Crm.Presales.OffersOption.DocumentType`(Crm.Presales.OffersOptions.md#documenttype) back reference 
| PaymentOptions | [DocumentTypePaymentOptions](Crm.Sales.DocumentTypePaymentOptions.md) | List of `DocumentTypePayment<br />Option`(Crm.Sales.DocumentTypePaymentOptions.md) child objects, based on the `Crm.Sales.DocumentTypePaymentOption.DocumentType`(Crm.Sales.DocumentTypePaymentOptions.md#documenttype) back reference 
| Printouts | [Printouts](Systems.Documents.Printouts.md) | List of `Printout`(Systems.Documents.Printouts.md) child objects, based on the `Systems.Documents.Printout.DocumentType`(Systems.Documents.Printouts.md#documenttype) back reference 
| PurchaseInvoicesOptions | [PurchaseInvoicesOptions](Logistics.Procurement.PurchaseInvoicesOptions.md) | List of `PurchaseInvoicesOption`(Logistics.Procurement.PurchaseInvoicesOptions.md) child objects, based on the `Logistics.Procurement.PurchaseInvoicesOption.DocumentType`(Logistics.Procurement.PurchaseInvoicesOptions.md#documenttype) back reference 
| Routes | [Routes](Systems.Documents.Routes.md) | List of `Route`(Systems.Documents.Routes.md) child objects, based on the `Systems.Documents.Route.DocumentType`(Systems.Documents.Routes.md#documenttype) back reference 
| SalesOrdersOptions | [SalesOrdersOptions](Crm.Sales.SalesOrdersOptions.md) | List of `SalesOrdersOption`(Crm.Sales.SalesOrdersOptions.md) child objects, based on the `Crm.Sales.SalesOrdersOption.DocumentType`(Crm.Sales.SalesOrdersOptions.md#documenttype) back reference 
| SecurityConditions | [DocumentTypeSecurityConditions](Systems.Documents.DocumentTypeSecurityConditions.md) | List of `DocumentTypeSecurity<br />Condition`(Systems.Documents.DocumentTypeSecurity<br />Conditions.md) child objects, based on the `Systems.Documents.DocumentTypeSecurity<br />Condition.DocumentType`(Systems.Documents.DocumentTypeSecurity<br />Conditions.md#documenttype) back reference 
| TransferOrdersOptions | [TransferOrdersOptions](Logistics.Inventory.TransferOrdersOptions.md) | List of `TransferOrdersOption`(Logistics.Inventory.TransferOrdersOptions.md) child objects, based on the `Logistics.Inventory.TransferOrdersOption.DocumentType`(Logistics.Inventory.TransferOrdersOptions.md#documenttype) back reference 
| UserStatuses | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) | List of `DocumentTypeUserStatus`(Systems.Documents.DocumentTypeUserStatuses.md) child objects, based on the `Systems.Documents.DocumentTypeUserStatus.DocumentType`(Systems.Documents.DocumentTypeUserStatuses.md#documenttype) back reference 
| WorkOrderDocument<br />TypesOptions | [WorkOrderDocumentTypesOptions](Production.ShopFloor.WorkOrderDocumentTypesOptions.md) | List of `WorkOrderDocument<br />TypesOption`(Production.ShopFloor.WorkOrderDocument<br />TypesOptions.md) child objects, based on the `Production.ShopFloor.WorkOrderDocument<br />TypesOption.DocumentType`(Production.ShopFloor.WorkOrderDocument<br />TypesOptions.md#documenttype) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Code

Unique descriptive code of the document type. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### CreateFulfillmentsOnCompletion

When document state is changed to Completed, creates completed document fulfillments for the parent document. Used only for logistic documents. `Required` `Default(false)` `Introduced in version 23.1.2.9`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### CreateManully

False if documents with this document type only can be generated; true - the user can create documents with this type. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.TransitionalDocument, False, obj.CreateManully)`
### Description

The description of this DocumentType.

_Type_: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisallowOppositeValuesGeneration

Disallow the generation of decreasing scalar values (values with opposite directions than the original values determined by the parent document) through this document type. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityName

System entity, which contains the documents. `Required` `Filter(multi eq)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

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

### GenerateSingleDocument

Create maximum one document when documents from this type are generated by parent documents (usually from another document type). `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this DocumentType.

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

### SchemaXML

Obsolete. Not used.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  

### TrackAttributeChanges

Enable/disable attributes change tracking for documents from this type. "Default" means that changes will be tracked for all documents, except transit and adjustment documents. `Required` `Default("DEF")` `Filter(eq)` `Introduced in version 24.1.3.37`

_Type_: **[TrackAttributeChanges](Systems.Documents.DocumentTypes.md#trackattributechanges)**  
_Category_: **System**  
Allowed values for the `TrackAttributeChanges`(Systems.Documents.DocumentTypes.md#trackattributechanges) data attribute  
_Allowed Values (Systems.Documents.DocumentTypesRepository.TrackAttributeChanges Enum Members)_  

| Value | Description |
| ---- | --- |
| Default | Default. Stored as 'DEF'. <br /> _Database Value:_ 'DEF' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Default' |
| ForceEnable | Force Enable. Stored as 'ENA'. <br /> _Database Value:_ 'ENA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ForceEnable' |
| ForceDisable | Force Disable. Stored as 'DIS'. <br /> _Database Value:_ 'DIS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ForceDisable' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Default**  
_Show in UI_: **ShownByDefault**  

### TrackPrintImages

Enable/disable print images tracking for documents from this type. `Required` `Default("SDC")` `Filter(eq)` `Introduced in version 24.1.3.95`

_Type_: **[TrackPrintImages](Systems.Documents.DocumentTypes.md#trackprintimages)**  
_Category_: **System**  
Allowed values for the `TrackPrintImages`(Systems.Documents.DocumentTypes.md#trackprintimages) data attribute  
_Allowed Values (Systems.Documents.DocumentTypesRepository.TrackPrintImages Enum Members)_  

| Value | Description |
| ---- | --- |
| DoNotTrack | DoNotTrack value. Stored as 'DNT'. <br /> _Database Value:_ 'DNT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DoNotTrack' |
| SaveSourceDataCompressed | SaveSourceDataCompressed value. Stored as 'SDC'. <br /> _Database Value:_ 'SDC' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'SaveSourceDataCompressed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **SaveSourceDataCompressed**  
_Show in UI_: **ShownByDefault**  

### TransitionalDocument

If checked determines that the documents from this type are automatically managed by the system and don't require management from the users. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.CreateManully, False, obj.TransitionalDocument)`
### TypeName

Description of the document type. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

The access key, containing the permissions for this DocumentType. An empty value means that all users have unlimited permissions. `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
| Release Documents | Permission1 |
| Complete Documents | Permission2 |
| Return to Released State | Permission3 |
| Release Documents On Different Date | Permission4 |
| Correct Documents | Permission5 |
| Void Documents | Permission6 |
| Set To Exit User State For Firm Planned Documents | Permission7 |
| Set To Exit User State For Released Documents | Permission8 |
### Sequence

The sequence that will be used to give new numbers to the documents of this type. `Filter(multi eq)`

_Type_: **[Sequences](Systems.Documents.Sequences.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentTypes

Domain API Entity Type: 
Systems_Documents_DocumentType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentTypes?$top=10>

