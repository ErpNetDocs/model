---
uid: Finance.Vat.BGVATDocumentTypeVATCodes
---
# Finance.Vat.BGVATDocumentTypeVATCodes Entity

**Namespace:** [Finance.Vat](Finance.Vat.md)  

Contains the VAT codes, which should be used, when reporting VAT for the different document types. Entity: Nat_BG_VAT_Document_Type_VAT_Codes

## Default Visualization
Default Display Text Format:  
_{Id}: {DocumentTypeId}_  
Default Search Members:  
__  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Vat.BGVATDocumentTypeVATCodes](Finance.Vat.BGVATDocumentTypeVATCodes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) | [CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) __nullable__ | VAT code, which will be used when Cash Reporting mode is used for the entry. Allowed values are the same as for VAT Code. 
| [DisplayText](Finance.Vat.BGVATDocumentTypeVATCodes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Finance.Vat.BGVATDocumentTypeVATCodes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Vat.BGVATDocumentTypeVATCodes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Finance.Vat.BGVATDocumentTypeVATCodes.md#id) | guid |  
| [ObjectVersion](Finance.Vat.BGVATDocumentTypeVATCodes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) | [VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) __nullable__ | VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Finance.Vat.BGVATDocumentTypeVATCodes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | Document type that generates VAT entries. `Required` `Filter(multi eq)` |


## Attribute Details

### CashReportingVATCode

VAT code, which will be used when Cash Reporting mode is used for the entry. Allowed values are the same as for VAT Code.

_Type_: **[CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) __nullable__**  
_Category_: **System**  
Allowed values for the `CashReportingVATCode`(Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) data attribute  
_Allowed Values (Finance.Vat.BGVATDocumentTypeVATCodesRepository.CashReportingVATCode Enum Members)_  

| Value | Description |
| ---- | --- |
| Invoice | Invoice value. Stored as '01'. <br /> _Database Value:_ '01' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Invoice' |
| DebitNote | DebitNote value. Stored as '02'. <br /> _Database Value:_ '02' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'DebitNote' |
| CreditNote | CreditNote value. Stored as '03'. <br /> _Database Value:_ '03' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'CreditNote' |
| CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry | CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry value. Stored as '04'. <br /> _Database Value:_ '04' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry' |
| CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry | CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry value. Stored as '05'. <br /> _Database Value:_ '05' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry' |
| CustomHouseEntry | CustomHouseEntry value. Stored as '07'. <br /> _Database Value:_ '07' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CustomHouseEntry' |
| Protocol | Protocol value. Stored as '09'. <br /> _Database Value:_ '09' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Protocol' |
| InvoiceCashReporting | InvoiceCashReporting value. Stored as '11'. <br /> _Database Value:_ '11' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'InvoiceCashReporting' |
| DebitNoteCashReporting | DebitNoteCashReporting value. Stored as '12'. <br /> _Database Value:_ '12' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DebitNoteCashReporting' |
| CreditNoteCashReporting | CreditNoteCashReporting value. Stored as '13'. <br /> _Database Value:_ '13' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'CreditNoteCashReporting' |
| CreditNoteByArticle126b<br />Al1OfBGVATLaw | CreditNoteByArticle126b<br />Al1OfBGVATLaw value. Stored as '23'. <br /> _Database Value:_ '23' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'CreditNoteByArticle126b<br />Al1OfBGVATLaw' |
| ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law | ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law value. Stored as '29'. <br /> _Database Value:_ '29' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law' |
| ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted | ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted value. Stored as '50'. <br /> _Database Value:_ '50' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted' |
| SalesReport | SalesReport value. Stored as '81'. <br /> _Database Value:_ '81' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'SalesReport' |
| SpecialTaxOrderSalesReport | SpecialTaxOrderSalesReport value. Stored as '82'. <br /> _Database Value:_ '82' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'SpecialTaxOrderSalesReport' |
| ReportOnSalesMade<br />WithFuelCompensation<br />Provided | ReportOnSalesMade<br />WithFuelCompensation<br />Provided value. Stored as '83'. <br /> _Database Value:_ '83' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'ReportOnSalesMade<br />WithFuelCompensation<br />Provided' |
| ReportOnTheSalesOfBread | ReportOnTheSalesOfBread value. Stored as '84'. <br /> _Database Value:_ '84' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'ReportOnTheSalesOfBread' |
| ReportOnTheSalesOfFlour | ReportOnTheSalesOfFlour value. Stored as '85'. <br /> _Database Value:_ '85' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'ReportOnTheSalesOfFlour' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw | RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw value. Stored as '91'. <br /> _Database Value:_ '91' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw' |
| RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 | RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 value. Stored as '92'. <br /> _Database Value:_ '92' <br /> _Model Value:_ 19 <br /> _Domain API Value:_ 'RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver value. Stored as '93'. <br /> _Database Value:_ '93' <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver value. Stored as '94'. <br /> _Database Value:_ '94' <br /> _Model Value:_ 21 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver' |

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### VATCode

VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values.

_Type_: **[VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) __nullable__**  
_Category_: **System**  
Allowed values for the `VATCode`(Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) data attribute  
_Allowed Values (Finance.Vat.BGVATDocumentTypeVATCodesRepository.VATCode Enum Members)_  

| Value | Description |
| ---- | --- |
| Invoice | Invoice value. Stored as '01'. <br /> _Database Value:_ '01' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Invoice' |
| DebitNote | DebitNote value. Stored as '02'. <br /> _Database Value:_ '02' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'DebitNote' |
| CreditNote | CreditNote value. Stored as '03'. <br /> _Database Value:_ '03' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'CreditNote' |
| CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry | CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry value. Stored as '04'. <br /> _Database Value:_ '04' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry' |
| CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry | CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry value. Stored as '05'. <br /> _Database Value:_ '05' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry' |
| CustomHouseEntry | CustomHouseEntry value. Stored as '07'. <br /> _Database Value:_ '07' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CustomHouseEntry' |
| Protocol | Protocol value. Stored as '09'. <br /> _Database Value:_ '09' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Protocol' |
| InvoiceCashReporting | InvoiceCashReporting value. Stored as '11'. <br /> _Database Value:_ '11' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'InvoiceCashReporting' |
| DebitNoteCashReporting | DebitNoteCashReporting value. Stored as '12'. <br /> _Database Value:_ '12' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DebitNoteCashReporting' |
| CreditNoteCashReporting | CreditNoteCashReporting value. Stored as '13'. <br /> _Database Value:_ '13' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'CreditNoteCashReporting' |
| CreditNoteByArticle126b<br />Al1OfBGVATLaw | CreditNoteByArticle126b<br />Al1OfBGVATLaw value. Stored as '23'. <br /> _Database Value:_ '23' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'CreditNoteByArticle126b<br />Al1OfBGVATLaw' |
| ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law | ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law value. Stored as '29'. <br /> _Database Value:_ '29' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law' |
| ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted | ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted value. Stored as '50'. <br /> _Database Value:_ '50' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted' |
| SalesReport | SalesReport value. Stored as '81'. <br /> _Database Value:_ '81' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'SalesReport' |
| SpecialTaxOrderSalesReport | SpecialTaxOrderSalesReport value. Stored as '82'. <br /> _Database Value:_ '82' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'SpecialTaxOrderSalesReport' |
| ReportOnSalesMade<br />WithFuelCompensation<br />Provided | ReportOnSalesMade<br />WithFuelCompensation<br />Provided value. Stored as '83'. <br /> _Database Value:_ '83' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'ReportOnSalesMade<br />WithFuelCompensation<br />Provided' |
| ReportOnTheSalesOfBread | ReportOnTheSalesOfBread value. Stored as '84'. <br /> _Database Value:_ '84' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'ReportOnTheSalesOfBread' |
| ReportOnTheSalesOfFlour | ReportOnTheSalesOfFlour value. Stored as '85'. <br /> _Database Value:_ '85' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'ReportOnTheSalesOfFlour' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw | RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw value. Stored as '91'. <br /> _Database Value:_ '91' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw' |
| RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 | RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 value. Stored as '92'. <br /> _Database Value:_ '92' <br /> _Model Value:_ 19 <br /> _Domain API Value:_ 'RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver value. Stored as '93'. <br /> _Database Value:_ '93' <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver value. Stored as '94'. <br /> _Database Value:_ '94' <br /> _Model Value:_ 21 <br /> _Domain API Value:_ 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentType

Document type that generates VAT entries. `Required` `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Finance.Vat.BGVATDocumentTypeVATCodes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Vat.BGVATDocumentTypeVATCodes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Vat_BGVATDocumentTypeVATCodes

Domain API Entity Type: 
Finance_Vat_BGVATDocumentTypeVATCode

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Vat_BGVATDocumentTypeVATCodes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Vat_BGVATDocumentTypeVATCodes?$top=10>

