---
uid: Logistics.Inventory.Lots
---
# Logistics.Inventory.Lots Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Warehouse lots. They contain one row for each specific product, status, production batch and other specific warehousing conditions. Lot status can block certain operations. Entity: Inv_Lots

## Default Visualization
Default Display Text Format:  
_{Number}_  
Default Search Members:  
_Number_  
Code Data Member:  
_Number_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.Lots](Logistics.Inventory.Lots.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Logistics.Inventory.Lots.md#description) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The description of this Lot. 
| [DisplayText](Logistics.Inventory.Lots.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpiryDate](Logistics.Inventory.Lots.md#expirydate) | datetime __nullable__ | Expiry date for this lot. 
| [Id](Logistics.Inventory.Lots.md#id) | guid |  
| [LicenseNo](Logistics.Inventory.Lots.md#licenseno) | string (50) __nullable__ | The license number for this lot. Null when license number is N/A or unknown. 
| [Number](Logistics.Inventory.Lots.md#number) | string (30) | The unique number of the Lot. May contain characters, if required. `Required` `Filter(eq;like)` 
| [ObjectVersion](Logistics.Inventory.Lots.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProductionBatchId](Logistics.Inventory.Lots.md#productionbatchid) | guid __nullable__ | Non-null if the production batch is known. Production batches are automatically created for internal production, but can also be used for specifying production batches for purchased goods. `Filter(multi eq)` 
| [PurchaseLotNumber](Logistics.Inventory.Lots.md#purchaselotnumber) | string (30) __nullable__ | Identification of the purchase lost with which the products from this store lot are received. E.g. the document number of the Receiving order. `Filter(like)` 
| [ReceiptDate](Logistics.Inventory.Lots.md#receiptdate) | date __nullable__ | The date of the first receipt of products in this lot. `ReadOnly` 
| [Status](Logistics.Inventory.Lots.md#status) | [Status](Logistics.Inventory.Lots.md#status) | Status of the warehouse lot. Minus statuses describe blocked conditions. -3 blocked for document (sales or service order) -2 blocked for party -1 blocked for inspection 0 free to use. `Required` `Default(0)` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BlockedForDocument](Logistics.Inventory.Lots.md#blockedfordocument) | [Documents](General.Documents.md) (nullable) | If non-null, contains the document for which the lot is blocked. `Filter(multi eq)` |
| [BlockedForParty](Logistics.Inventory.Lots.md#blockedforparty) | [Parties](General.Contacts.Parties.md) (nullable) | Non-null when the warehouse lot is blocked specifically for some party. `Filter(multi eq)` |
| [CertificateDocument](Logistics.Inventory.Lots.md#certificatedocument) | [Documents](General.Documents.md) (nullable) | Document, containing the certificate for this lot. `Filter(multi eq)` |
| [ExciseMeasuringTransaction](Logistics.Inventory.Lots.md#excisemeasuringtransaction) | [MeasuringTransactions](Finance.Excise.MeasuringTransactions.md) (nullable) | When the lot was created in an excise controlled environment, specifies the measuring transaction which was used to create the lot. `Filter(multi eq)` `Introduced in version 21.1.1.59` |
| [Product](Logistics.Inventory.Lots.md#product) | [Products](General.Products.Products.md) | The product to which the lot is bound. `Required` `Filter(multi eq)` |
| [ReceiptStoreTransaction](Logistics.Inventory.Lots.md#receiptstoretransaction) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) (nullable) | The store receipt transaction, which created the lot. null if the lot is manually created. `Filter(multi eq)` |


## Attribute Details

### Description

The description of this Lot.

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ExpiryDate

Expiry date for this lot.

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LicenseNo

The license number for this lot. Null when license number is N/A or unknown.

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  

### Number

The unique number of the Lot. May contain characters, if required. `Required` `Filter(eq;like)`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ProductionBatchId

Non-null if the production batch is known. Production batches are automatically created for internal production, but can also be used for specifying production batches for purchased goods. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### PurchaseLotNumber

Identification of the purchase lost with which the products from this store lot are received. E.g. the document number of the Receiving order. `Filter(like)`

_Type_: **string (30) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  

### ReceiptDate

The date of the first receipt of products in this lot. `ReadOnly`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Status

Status of the warehouse lot. Minus statuses describe blocked conditions. -3 blocked for document (sales or service order) -2 blocked for party -1 blocked for inspection 0 free to use. `Required` `Default(0)` `Filter(multi eq)`

_Type_: **[Status](Logistics.Inventory.Lots.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Logistics.Inventory.Lots.md#status) data attribute  
_Allowed Values (Logistics.Inventory.LotsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| FreeToUse | FreeToUse value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'FreeToUse' |
| BlockedForDocument | BlockedForDocument value. Stored as -3. <br /> _Database Value:_ -3 <br /> _Model Value:_ -3 <br /> _Domain API Value:_ 'BlockedForDocument' |
| BlockedForParty | BlockedForParty value. Stored as -2. <br /> _Database Value:_ -2 <br /> _Model Value:_ -2 <br /> _Domain API Value:_ 'BlockedForParty' |
| BlockedForInspection | BlockedForInspection value. Stored as -1. <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'BlockedForInspection' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### BlockedForDocument

If non-null, contains the document for which the lot is blocked. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### BlockedForParty

Non-null when the warehouse lot is blocked specifically for some party. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### CertificateDocument

Document, containing the certificate for this lot. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### ExciseMeasuringTransaction

When the lot was created in an excise controlled environment, specifies the measuring transaction which was used to create the lot. `Filter(multi eq)` `Introduced in version 21.1.1.59`

_Type_: **[MeasuringTransactions](Finance.Excise.MeasuringTransactions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The product to which the lot is bound. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### ReceiptStoreTransaction

The store receipt transaction, which created the lot. null if the lot is manually created. `Filter(multi eq)`

_Type_: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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



## Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.Lots erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.Lots erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_Lots?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_Lots?$top=10>

