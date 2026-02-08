---
uid: Regulatory.Intrastat.DeclarationLines
---
# Regulatory.Intrastat.DeclarationLines


Contains the details of the Intrastat declarations, issued by the enterprise companies.

## General
Namespace: [Regulatory.Intrastat](Regulatory.Intrastat.md)  
Repository: Regulatory.Intrastat.DeclarationLines  
Base Table: Its_Declaration_Lines  
API access:  ReadWrite  

## Renames

Old name: Finance.Intrastat.DeclarationLines  
New name: Regulatory.Intrastat.DeclarationLines  
Version: 26.2.1.4  
Case: 39297  



## Visualization
Display Format: {IntrastatDeclaration.EntityName}  
Search Members: IntrastatDeclaration.EntityName  
Name Member: IntrastatDeclaration.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Intrastat.Declarations](Regulatory.Intrastat.Declarations.md)  
Aggregate Root:  
[Regulatory.Intrastat.Declarations](Regulatory.Intrastat.Declarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms) | [DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms) | Delivery terms - classification according to Intrastat`Required` 
| [InvoicedValueAmountBase](Regulatory.Intrastat.DeclarationLines.md#invoicedvalueamountbase) | [Amount (10, 0)](../data-types.md#amount) | Invoiced value of the goods in the base currency`Currency: IntrastatDeclaration.BaseCurrency` `Required` 
| [LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction) | [LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction) | Line action - 'NEW' = New, 'EDN' = Edited-New, 'EDO' = Edited-Old, 'DEL' = Deleted`Required` `Default(&quot;NEW&quot;)` 
| [LineNo](Regulatory.Intrastat.DeclarationLines.md#lineno) | int32 | Consequtive line number within the intrastat declaration`Required` `Filter(eq)` 
| [NetMassKg](Regulatory.Intrastat.DeclarationLines.md#netmasskg) | decimal (14, 3) | Net mass of the goods in kg`Required` `Filter(multi eq)` 
| [QuantitySupplementaryUnit](Regulatory.Intrastat.DeclarationLines.md#quantitysupplementaryunit) | decimal (10, 0) __nullable__ | Quantity of the goods in the supplementary unit 
| [StatisticalValueAmountBase](Regulatory.Intrastat.DeclarationLines.md#statisticalvalueamountbase) | [Amount (10, 0)](../data-types.md#amount) __nullable__ | Statistical value of the goods in the base currency`Currency: IntrastatDeclaration.BaseCurrency` 
| [TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature) | [TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature) | Transaction nature, according to the Intrastat classification`Required` 
| [TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode) | [TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode) | Transportation mode - type of transportation used`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](Regulatory.Intrastat.DeclarationLines.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) | Administrative region of the enterprise company at the time of the declaration |
| [IntrastatCommodityCode](Regulatory.Intrastat.DeclarationLines.md#intrastatcommoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) | The commodity code of the goods, according to the Intrastat commodity classification |
| [IntrastatDeclaration](Regulatory.Intrastat.DeclarationLines.md#intrastatdeclaration) | [Declarations](Regulatory.Intrastat.Declarations.md) | The intrastat declaration, to which this line belongs |
| [OriginCountry](Regulatory.Intrastat.DeclarationLines.md#origincountry) | [Countries](General.Geography.Countries.md) (nullable) | The country of origin of the goods. NULL for outbound declarations |
| [Party](Regulatory.Intrastat.DeclarationLines.md#party) | [Parties](General.Contacts.Parties.md) (nullable) | Partner to whom the goods are dispatched, or partner from whom the goods are received. |
| [PartyCountry](Regulatory.Intrastat.DeclarationLines.md#partycountry) | [Countries](General.Geography.Countries.md) | The country of the partner |
| [TransportCountry](Regulatory.Intrastat.DeclarationLines.md#transportcountry) | [Countries](General.Geography.Countries.md) | The country of the transportation company |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Intrastat.DeclarationLines.md#id) | guid |  
| [ObjectVersion](Regulatory.Intrastat.DeclarationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Intrastat.DeclarationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DeliveryTerms

Delivery terms - classification according to Intrastat`Required`

Type: **[DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms)**  
Category: **System**  
Generic enum type for DeliveryTerms properties  
Allowed Values (Regulatory.Intrastat.DeliveryTerms Enum Members)  

| Value | Description |
| ---- | --- |
| ExWorks | ExWorks value. Stored as 'EXW'. <br /> Database Value: 'EXW' <br /> Model Value: 0 <br /> Domain API Value: 'ExWorks' |
| FrancoCarrier | FrancoCarrier value. Stored as 'FCA'. <br /> Database Value: 'FCA' <br /> Model Value: 1 <br /> Domain API Value: 'FrancoCarrier' |
| FreeAlongsideShip | FreeAlongsideShip value. Stored as 'FAS'. <br /> Database Value: 'FAS' <br /> Model Value: 2 <br /> Domain API Value: 'FreeAlongsideShip' |
| FreeOnBoard | FreeOnBoard value. Stored as 'FOB'. <br /> Database Value: 'FOB' <br /> Model Value: 3 <br /> Domain API Value: 'FreeOnBoard' |
| CostAndFreightCF | CostAndFreightCF value. Stored as 'CFR'. <br /> Database Value: 'CFR' <br /> Model Value: 4 <br /> Domain API Value: 'CostAndFreightCF' |
| CostInsuranceAndFreight | CostInsuranceAndFreight value. Stored as 'CIF'. <br /> Database Value: 'CIF' <br /> Model Value: 5 <br /> Domain API Value: 'CostInsuranceAndFreight' |
| CarriagePaidTo | CarriagePaidTo value. Stored as 'CPT'. <br /> Database Value: 'CPT' <br /> Model Value: 6 <br /> Domain API Value: 'CarriagePaidTo' |
| CarriageAndInsurancePaidTo | CarriageAndInsurancePaidTo value. Stored as 'CIP'. <br /> Database Value: 'CIP' <br /> Model Value: 7 <br /> Domain API Value: 'CarriageAndInsurancePaidTo' |
| DeliveredAtPlace | DeliveredAtPlace value. Stored as 'DAP'. <br /> Database Value: 'DAP' <br /> Model Value: 8 <br /> Domain API Value: 'DeliveredAtPlace' |
| DeliveredAtTerminal | DeliveredAtTerminal value. Stored as 'DAT'. <br /> Database Value: 'DAT' <br /> Model Value: 9 <br /> Domain API Value: 'DeliveredAtTerminal' |
| DeliveredDutyPaid | DeliveredDutyPaid value. Stored as 'DDP'. <br /> Database Value: 'DDP' <br /> Model Value: 10 <br /> Domain API Value: 'DeliveredDutyPaid' |
| DeliveredAtPlaceUnloaded | DeliveredAtPlaceUnloaded value. Stored as 'DPU'. <br /> Database Value: 'DPU' <br /> Model Value: 11 <br /> Domain API Value: 'DeliveredAtPlaceUnloaded' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InvoicedValueAmountBase

Invoiced value of the goods in the base currency`Currency: IntrastatDeclaration.BaseCurrency` `Required`

Type: **[Amount (10, 0)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineAction

Line action - 'NEW' = New, 'EDN' = Edited-New, 'EDO' = Edited-Old, 'DEL' = Deleted`Required` `Default(&quot;NEW&quot;)`

Type: **[LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction)**  
Category: **System**  
Allowed values for the `LineAction`(Regulatory.Intrastat.DeclarationLines.md#lineaction) data attribute  
Allowed Values (Regulatory.Intrastat.DeclarationLinesRepository.LineAction Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'NEW'. <br /> Database Value: 'NEW' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| EditedNew | EditedNew value. Stored as 'EDN'. <br /> Database Value: 'EDN' <br /> Model Value: 1 <br /> Domain API Value: 'EditedNew' |
| EditedOld | EditedOld value. Stored as 'EDO'. <br /> Database Value: 'EDO' <br /> Model Value: 2 <br /> Domain API Value: 'EditedOld' |
| Deleted | Deleted value. Stored as 'DEL'. <br /> Database Value: 'DEL' <br /> Model Value: 3 <br /> Domain API Value: 'Deleted' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **New**  
Show in UI: **ShownByDefault**  

### LineNo

Consequtive line number within the intrastat declaration`Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.IntrastatDeclaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.IntrastatDeclaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### NetMassKg

Net mass of the goods in kg`Required` `Filter(multi eq)`

Type: **decimal (14, 3)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantitySupplementaryUnit

Quantity of the goods in the supplementary unit

Type: **decimal (10, 0) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StatisticalValueAmountBase

Statistical value of the goods in the base currency`Currency: IntrastatDeclaration.BaseCurrency`

Type: **[Amount (10, 0)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TransactionNature

Transaction nature, according to the Intrastat classification`Required`

Type: **[TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature)**  
Category: **System**  
Generic enum type for TransactionNature properties  
Allowed Values (Regulatory.Intrastat.TransactionNature Enum Members)  

| Value | Description |
| ---- | --- |
| OutrightPurchaseOrSale | OutrightPurchaseOrSale value. Stored as '11'. <br /> Database Value: '11' <br /> Model Value: 0 <br /> Domain API Value: 'OutrightPurchaseOrSale' |
| SupplyForSale | SupplyForSale value. Stored as '12'. <br /> Database Value: '12' <br /> Model Value: 1 <br /> Domain API Value: 'SupplyForSale' |
| BarterTrade | BarterTrade value. Stored as '13'. <br /> Database Value: '13' <br /> Model Value: 2 <br /> Domain API Value: 'BarterTrade' |
| FinancialLeasing | FinancialLeasing value. Stored as '14'. <br /> Database Value: '14' <br /> Model Value: 3 <br /> Domain API Value: 'FinancialLeasing' |
| OtherTransactions | OtherTransactions value. Stored as '19'. <br /> Database Value: '19' <br /> Model Value: 4 <br /> Domain API Value: 'OtherTransactions' |
| ReturnStokilizing | ReturnStokilizing value. Stored as '21'. <br /> Database Value: '21' <br /> Model Value: 5 <br /> Domain API Value: 'ReturnStokilizing' |
| ReplacementFor<br />ReturnedGoods | ReplacementFor<br />ReturnedGoods value. Stored as '22'. <br /> Database Value: '22' <br /> Model Value: 6 <br /> Domain API Value: 'ReplacementFor<br />ReturnedGoods' |
| ReplacementOfGoods<br />NotBeingReturned | ReplacementOfGoods<br />NotBeingReturned value. Stored as '23'. <br /> Database Value: '23' <br /> Model Value: 7 <br /> Domain API Value: 'ReplacementOfGoods<br />NotBeingReturned' |
| ReturnOrExchange<br />OfOtherGoods | ReturnOrExchange<br />OfOtherGoods value. Stored as '29'. <br /> Database Value: '29' <br /> Model Value: 8 <br /> Domain API Value: 'ReturnOrExchange<br />OfOtherGoods' |
| SpecificTransactions | SpecificTransactions value. Stored as '60'. <br /> Database Value: '60' <br /> Model Value: 9 <br /> Domain API Value: 'SpecificTransactions' |
| OperationsOnJointProjects | OperationsOnJointProjects value. Stored as '70'. <br /> Database Value: '70' <br /> Model Value: 10 <br /> Domain API Value: 'OperationsOnJointProjects' |
| TransactionsOf<br />ConstructionMaterials<br />AndEquipment | TransactionsOf<br />ConstructionMaterials<br />AndEquipment value. Stored as '80'. <br /> Database Value: '80' <br /> Model Value: 11 <br /> Domain API Value: 'TransactionsOf<br />ConstructionMaterials<br />AndEquipment' |
| OtherTransactionsLeasing | OtherTransactionsLeasing value. Stored as '91'. <br /> Database Value: '91' <br /> Model Value: 12 <br /> Domain API Value: 'OtherTransactionsLeasing' |
| OtherTransactionsOther | OtherTransactionsOther value. Stored as '99'. <br /> Database Value: '99' <br /> Model Value: 13 <br /> Domain API Value: 'OtherTransactionsOther' |
| DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind | DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind value. Stored as '30'. <br /> Database Value: '30' <br /> Model Value: 14 <br /> Domain API Value: 'DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind' |
| GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender | GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender value. Stored as '41'. <br /> Database Value: '41' <br /> Model Value: 15 <br /> Domain API Value: 'GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender' |
| GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender | GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender value. Stored as '42'. <br /> Database Value: '42' <br /> Model Value: 16 <br /> Domain API Value: 'GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender' |
| GoodsThatAreReturned<br />ToSender | GoodsThatAreReturned<br />ToSender value. Stored as '51'. <br /> Database Value: '51' <br /> Model Value: 17 <br /> Domain API Value: 'GoodsThatAreReturned<br />ToSender' |
| GoodsThatAreNot<br />ReturnedToSender | GoodsThatAreNot<br />ReturnedToSender value. Stored as '52'. <br /> Database Value: '52' <br /> Model Value: 18 <br /> Domain API Value: 'GoodsThatAreNot<br />ReturnedToSender' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TransportMode

Transportation mode - type of transportation used`Required`

Type: **[TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode)**  
Category: **System**  
Generic enum type for TransportMode properties  
Allowed Values (Regulatory.Intrastat.TransportMode Enum Members)  

| Value | Description |
| ---- | --- |
| Shipping | Shipping value. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'Shipping' |
| RailwayTransport | RailwayTransport value. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'RailwayTransport' |
| RoadTransport | RoadTransport value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'RoadTransport' |
| AirTransport | AirTransport value. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'AirTransport' |
| Mail | Mail value. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'Mail' |
| FixedTransport<br />Installations | FixedTransport<br />Installations value. Stored as '7'. <br /> Database Value: '7' <br /> Model Value: 5 <br /> Domain API Value: 'FixedTransport<br />Installations' |
| RiverTransport | RiverTransport value. Stored as '8'. <br /> Database Value: '8' <br /> Model Value: 6 <br /> Domain API Value: 'RiverTransport' |
| SelfPropelled | SelfPropelled value. Stored as '9'. <br /> Database Value: '9' <br /> Model Value: 7 <br /> Domain API Value: 'SelfPropelled' |

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

### AdministrativeRegion

Administrative region of the enterprise company at the time of the declaration

Type: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatCommodityCode

The commodity code of the goods, according to the Intrastat commodity classification

Type: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatDeclaration

The intrastat declaration, to which this line belongs

Type: **[Declarations](Regulatory.Intrastat.Declarations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### OriginCountry

The country of origin of the goods. NULL for outbound declarations

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

Partner to whom the goods are dispatched, or partner from whom the goods are received.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PartyCountry

The country of the partner

Type: **[Countries](General.Geography.Countries.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TransportCountry

The country of the transportation company

Type: **[Countries](General.Geography.Countries.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Intrastat.DeclarationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Intrastat.DeclarationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Intrastat_DeclarationLines

Domain API Entity Type: 
Regulatory_Intrastat_DeclarationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Intrastat_DeclarationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Intrastat_DeclarationLines?$top=10>

