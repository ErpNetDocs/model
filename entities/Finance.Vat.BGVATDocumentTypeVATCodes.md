---
uid: Finance.Vat.BGVATDocumentTypeVATCodes
---
# Finance.Vat.BGVATDocumentTypeVATCodes


Contains the VAT codes, which should be used, when reporting VAT for the different document types.

## General
Namespace: [Finance.Vat](Finance.Vat.md)  
Repository: Finance.Vat.BGVATDocumentTypeVATCodes  
Base Table: Nat_BG_VAT_Document_Type_VAT_Codes  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {DocumentTypeId}  
Search Members:   
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Vat.BGVATDocumentTypeVATCodes](Finance.Vat.BGVATDocumentTypeVATCodes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) | [CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) __nullable__ | VAT code, which will be used when Cash Reporting mode is used for the entry 
| [VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) | [VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) __nullable__ | VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Finance.Vat.BGVATDocumentTypeVATCodes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | Document type that generates VAT entries. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Vat.BGVATDocumentTypeVATCodes.md#id) | guid |  
| [ObjectVersion](Finance.Vat.BGVATDocumentTypeVATCodes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Vat.BGVATDocumentTypeVATCodes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Vat.BGVATDocumentTypeVATCodes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Vat.BGVATDocumentTypeVATCodes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Vat.BGVATDocumentTypeVATCodes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CashReportingVATCode

VAT code, which will be used when Cash Reporting mode is used for the entry

Type: **[CashReportingVATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) __nullable__**  
Category: **System**  
Allowed values for the `CashReportingVATCode`(Finance.Vat.BGVATDocumentTypeVATCodes.md#cashreportingvatcode) data attribute  
Allowed Values (Finance.Vat.BGVATDocumentTypeVATCodesRepository.CashReportingVATCode Enum Members)  

| Value | Description |
| ---- | --- |
| Invoice | Invoice value. Stored as '01'. <br /> Database Value: '01' <br /> Model Value: 0 <br /> Domain API Value: 'Invoice' |
| DebitNote | DebitNote value. Stored as '02'. <br /> Database Value: '02' <br /> Model Value: 1 <br /> Domain API Value: 'DebitNote' |
| CreditNote | CreditNote value. Stored as '03'. <br /> Database Value: '03' <br /> Model Value: 2 <br /> Domain API Value: 'CreditNote' |
| CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry | CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry value. Stored as '04'. <br /> Database Value: '04' <br /> Model Value: 3 <br /> Domain API Value: 'CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry' |
| CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry | CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry value. Stored as '05'. <br /> Database Value: '05' <br /> Model Value: 4 <br /> Domain API Value: 'CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry' |
| CustomHouseEntry | CustomHouseEntry value. Stored as '07'. <br /> Database Value: '07' <br /> Model Value: 5 <br /> Domain API Value: 'CustomHouseEntry' |
| Protocol | Protocol value. Stored as '09'. <br /> Database Value: '09' <br /> Model Value: 6 <br /> Domain API Value: 'Protocol' |
| InvoiceCashReporting | InvoiceCashReporting value. Stored as '11'. <br /> Database Value: '11' <br /> Model Value: 7 <br /> Domain API Value: 'InvoiceCashReporting' |
| DebitNoteCashReporting | DebitNoteCashReporting value. Stored as '12'. <br /> Database Value: '12' <br /> Model Value: 8 <br /> Domain API Value: 'DebitNoteCashReporting' |
| CreditNoteCashReporting | CreditNoteCashReporting value. Stored as '13'. <br /> Database Value: '13' <br /> Model Value: 9 <br /> Domain API Value: 'CreditNoteCashReporting' |
| CreditNoteByArticle126b<br />Al1OfBGVATLaw | CreditNoteByArticle126b<br />Al1OfBGVATLaw value. Stored as '23'. <br /> Database Value: '23' <br /> Model Value: 10 <br /> Domain API Value: 'CreditNoteByArticle126b<br />Al1OfBGVATLaw' |
| ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law | ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law value. Stored as '29'. <br /> Database Value: '29' <br /> Model Value: 11 <br /> Domain API Value: 'ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law' |
| ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted | ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted value. Stored as '50'. <br /> Database Value: '50' <br /> Model Value: 12 <br /> Domain API Value: 'ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted' |
| SalesReport | SalesReport value. Stored as '81'. <br /> Database Value: '81' <br /> Model Value: 13 <br /> Domain API Value: 'SalesReport' |
| SpecialTaxOrderSalesReport | SpecialTaxOrderSalesReport value. Stored as '82'. <br /> Database Value: '82' <br /> Model Value: 14 <br /> Domain API Value: 'SpecialTaxOrderSalesReport' |
| ReportOnSalesMade<br />WithFuelCompensation<br />Provided | ReportOnSalesMade<br />WithFuelCompensation<br />Provided value. Stored as '83'. <br /> Database Value: '83' <br /> Model Value: 15 <br /> Domain API Value: 'ReportOnSalesMade<br />WithFuelCompensation<br />Provided' |
| ReportOnTheSalesOfBread | ReportOnTheSalesOfBread value. Stored as '84'. <br /> Database Value: '84' <br /> Model Value: 16 <br /> Domain API Value: 'ReportOnTheSalesOfBread' |
| ReportOnTheSalesOfFlour | ReportOnTheSalesOfFlour value. Stored as '85'. <br /> Database Value: '85' <br /> Model Value: 17 <br /> Domain API Value: 'ReportOnTheSalesOfFlour' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw | RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw value. Stored as '91'. <br /> Database Value: '91' <br /> Model Value: 18 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw' |
| RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 | RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 value. Stored as '92'. <br /> Database Value: '92' <br /> Model Value: 19 <br /> Domain API Value: 'RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver value. Stored as '93'. <br /> Database Value: '93' <br /> Model Value: 20 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver value. Stored as '94'. <br /> Database Value: '94' <br /> Model Value: 21 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VATCode

VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values.

Type: **[VATCode](Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) __nullable__**  
Category: **System**  
Allowed values for the `VATCode`(Finance.Vat.BGVATDocumentTypeVATCodes.md#vatcode) data attribute  
Allowed Values (Finance.Vat.BGVATDocumentTypeVATCodesRepository.VATCode Enum Members)  

| Value | Description |
| ---- | --- |
| Invoice | Invoice value. Stored as '01'. <br /> Database Value: '01' <br /> Model Value: 0 <br /> Domain API Value: 'Invoice' |
| DebitNote | DebitNote value. Stored as '02'. <br /> Database Value: '02' <br /> Model Value: 1 <br /> Domain API Value: 'DebitNote' |
| CreditNote | CreditNote value. Stored as '03'. <br /> Database Value: '03' <br /> Model Value: 2 <br /> Domain API Value: 'CreditNote' |
| CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry | CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry value. Stored as '04'. <br /> Database Value: '04' <br /> Model Value: 3 <br /> Domain API Value: 'CallOffStockRegister<br />TheGoodsAreSent<br />OrTransportedFrom<br />TheCountryToAnother<br />EUCountry' |
| CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry | CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry value. Stored as '05'. <br /> Database Value: '05' <br /> Model Value: 4 <br /> Domain API Value: 'CallOffStockRegister<br />TheGoodsAreReceived<br />InTheCountry' |
| CustomHouseEntry | CustomHouseEntry value. Stored as '07'. <br /> Database Value: '07' <br /> Model Value: 5 <br /> Domain API Value: 'CustomHouseEntry' |
| Protocol | Protocol value. Stored as '09'. <br /> Database Value: '09' <br /> Model Value: 6 <br /> Domain API Value: 'Protocol' |
| InvoiceCashReporting | InvoiceCashReporting value. Stored as '11'. <br /> Database Value: '11' <br /> Model Value: 7 <br /> Domain API Value: 'InvoiceCashReporting' |
| DebitNoteCashReporting | DebitNoteCashReporting value. Stored as '12'. <br /> Database Value: '12' <br /> Model Value: 8 <br /> Domain API Value: 'DebitNoteCashReporting' |
| CreditNoteCashReporting | CreditNoteCashReporting value. Stored as '13'. <br /> Database Value: '13' <br /> Model Value: 9 <br /> Domain API Value: 'CreditNoteCashReporting' |
| CreditNoteByArticle126b<br />Al1OfBGVATLaw | CreditNoteByArticle126b<br />Al1OfBGVATLaw value. Stored as '23'. <br /> Database Value: '23' <br /> Model Value: 10 <br /> Domain API Value: 'CreditNoteByArticle126b<br />Al1OfBGVATLaw' |
| ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law | ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law value. Stored as '29'. <br /> Database Value: '29' <br /> Model Value: 11 <br /> Domain API Value: 'ProtocolByArticle126b<br />Al2And7OfBGVAT<br />Law' |
| ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted | ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted value. Stored as '50'. <br /> Database Value: '50' <br /> Model Value: 12 <br /> Domain API Value: 'ProtocolForCharging<br />TheRequiredVAT<br />ForFuelSupplies<br />ForWhichCompensation<br />HasBeenGranted' |
| SalesReport | SalesReport value. Stored as '81'. <br /> Database Value: '81' <br /> Model Value: 13 <br /> Domain API Value: 'SalesReport' |
| SpecialTaxOrderSalesReport | SpecialTaxOrderSalesReport value. Stored as '82'. <br /> Database Value: '82' <br /> Model Value: 14 <br /> Domain API Value: 'SpecialTaxOrderSalesReport' |
| ReportOnSalesMade<br />WithFuelCompensation<br />Provided | ReportOnSalesMade<br />WithFuelCompensation<br />Provided value. Stored as '83'. <br /> Database Value: '83' <br /> Model Value: 15 <br /> Domain API Value: 'ReportOnSalesMade<br />WithFuelCompensation<br />Provided' |
| ReportOnTheSalesOfBread | ReportOnTheSalesOfBread value. Stored as '84'. <br /> Database Value: '84' <br /> Model Value: 16 <br /> Domain API Value: 'ReportOnTheSalesOfBread' |
| ReportOnTheSalesOfFlour | ReportOnTheSalesOfFlour value. Stored as '85'. <br /> Database Value: '85' <br /> Model Value: 17 <br /> Domain API Value: 'ReportOnTheSalesOfFlour' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw | RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw value. Stored as '91'. <br /> Database Value: '91' <br /> Model Value: 18 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al3OfBGVATLaw' |
| RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 | RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14 value. Stored as '92'. <br /> Database Value: '92' <br /> Model Value: 19 <br /> Domain API Value: 'RecordForTaxCredit<br />ByArticle151gAl3<br />OfBGVATLawOrReport<br />ByArt104zhAl14' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver value. Stored as '93'. <br /> Database Value: '93' <br /> Model Value: 20 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />NoCashReporting<br />Receiver' |
| RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver | RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver value. Stored as '94'. <br /> Database Value: '94' <br /> Model Value: 21 <br /> Domain API Value: 'RecordForRecoverable<br />TaxByArticle151v<br />Al7OfBGVATLawWith<br />CashReportingReceiver' |

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

### DocumentType

Document type that generates VAT entries.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
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

