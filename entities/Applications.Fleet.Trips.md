# Applications.Fleet.Trips

Represents actual trip made by the vehicles. Entity: Fleet_Trips

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.Trips.md#Id) | guid |  
| [CompleteTime](Applications.Fleet.Trips.md#CompleteTime) | datetime (nullable) | Exact time, when the document was last completed[Filter(ge;le)] 
| [CreationTime](Applications.Fleet.Trips.md#CreationTime) | datetime | Date/Time when the document was created [Required][Filter(ge;le)] 
| [CreationUser](Applications.Fleet.Trips.md#CreationUser) | string | The login name of the user, who created the document [Required][Filter(like)] 
| [DocumentDate](Applications.Fleet.Trips.md#DocumentDate) | datetime | The date on which the document was issued [Required][Filter(eq;ge;le)][ORD] 
| [DocumentNo](Applications.Fleet.Trips.md#DocumentNo) | string | Document number, unique within Document_Type_Id [Required][Filter(eq;like)][ORD] 
| [DocumentVersion](Applications.Fleet.Trips.md#DocumentVersion) | int32 | [Filter(eq;ge;le)] 
| [DocumentNotes](Applications.Fleet.Trips.md#DocumentNotes) | string (nullable) | Notes for this Document 
| [ParentDocumentRelationshipType](Applications.Fleet.Trips.md#ParentDocumentRelationshipType) | [General.ParentDocumentRelationshipType](Applications.Fleet.Trips.md#ParentDocumentRelationshipType) (nullable) | Type of relationship between the current document and the parent document(s). Affects the constraints for execution/completion for the documents. Possible values: 'S' = 'Subtask', 'N' = 'Next task'. 
| [PlanningOnly](Applications.Fleet.Trips.md#PlanningOnly) | boolean (nullable) | Indicates that the document is used only for planning (and as consequence its state cannot be greater than Planned) [Required] 
| [ReadOnly](Applications.Fleet.Trips.md#ReadOnly) | boolean | True - the document is read only; false - the document is not read only [Required] 
| [ReferenceDate](Applications.Fleet.Trips.md#ReferenceDate) | datetime (nullable) | The date to which this document refers, i.e. when the action really occurred. If null, Document_Date is taken [Filter(ge;le)] 
| [ReferenceDocumentNo](Applications.Fleet.Trips.md#ReferenceDocumentNo) | string (nullable) | The number of the document (issued by the other party), which was the reason for the creation of the current document. The numebr should be unique within the party documents [Filter(eq;like)] 
| [ReleaseTime](Applications.Fleet.Trips.md#ReleaseTime) | datetime (nullable) | Exact time, when the document was first released [Filter(ge;le)] 
| [State](Applications.Fleet.Trips.md#State) | [General.DocumentState](Applications.Fleet.Trips.md#State) | 0=New;5=Corrective;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed [Required][Filter(eq;ge;le)] 
| [Void](Applications.Fleet.Trips.md#Void) | boolean | True if the document is null and void [Required][Filter(eq)] 
| [VoidReason](Applications.Fleet.Trips.md#VoidReason) | string (nullable) | Reason for voiding the document, entered by the user 
| [VoidTime](Applications.Fleet.Trips.md#VoidTime) | datetime (nullable) | Date/time when the document has become void 
| [VoidUser](Applications.Fleet.Trips.md#VoidUser) | string (nullable) | The user who voided the document 
| [EntityName](Applications.Fleet.Trips.md#EntityName) | string | The entity name of the document equal to the entity name of the document type.[Filter(eq)] [ORD] 
| [IsReleased](Applications.Fleet.Trips.md#IsReleased) | boolean | True if the document is not void and its state is released or greater. [Required] [Default(false)] [Filter(eq)] [ReadOnly] 
| [IsSingleExecution](Applications.Fleet.Trips.md#IsSingleExecution) | boolean | Specifies whether the document is a single execution of its order document. [Required] [Default(false)] [Filter(eq)] [ReadOnly] 
| [PrimaryVehicleEndingMileage](Applications.Fleet.Trips.md#PrimaryVehicleEndingMileage) | decimal (nullable) | Mileage of the primary vehicle in the vehicle set at the ending of the trip. null means unknown. 
| [PrimaryVehicleStartingMileage](Applications.Fleet.Trips.md#PrimaryVehicleStartingMileage) | decimal (nullable) | Mileage of the primary vehicle in the vehicle set at the begining of the trip. null means unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Applications.Fleet.Trips.md#AccessKey) | [Systems.Security.AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the user permissions for this document. null means that all users have unlimited permissions |
| [AdjustedDocument](Applications.Fleet.Trips.md#AdjustedDocument) | [General.Documents](General.Documents.md) (nullable) | The primary document, which the current document adjusts. null when this is not an adjustment document |
| [AssignedToUser](Applications.Fleet.Trips.md#AssignedToUser) | [Systems.Security.Users](Systems.Security.Users.md) (nullable) | The user to which this document is assigned for handling. null means that the document is not assigned to specific user |
| [CurrencyDirectory](Applications.Fleet.Trips.md#CurrencyDirectory) | [General.CurrencyDirectories](General.CurrencyDirectories.md) (nullable) | The currency directory, containing all the convertion rates, used by the document. null means that the document does not need currency convertions |
| [DocumentType](Applications.Fleet.Trips.md#DocumentType) | [General.DocumentTypes](General.DocumentTypes.md) | The user defined type of the document. Determines document behaviour, properties, additional amounts, validation, generations, etc. [Required] |
| [EnterpriseCompany](Applications.Fleet.Trips.md#EnterpriseCompany) | [General.EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document [Required] |
| [EnterpriseCompanyLocation](Applications.Fleet.Trips.md#EnterpriseCompanyLocation) | [General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location which issued the document. null means that there is only one location within the enterprise company and locations are not used |
| [FromCompanyDivision](Applications.Fleet.Trips.md#FromCompanyDivision) | [General.Contacts.CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable) | The division of the company, issuing the document. null when the document is not issued by any specific division |
| [FromParty](Applications.Fleet.Trips.md#FromParty) | [General.Contacts.Parties](General.Contacts.Parties.md) | The party which issued the document [Required] |
| [MasterDocument](Applications.Fleet.Trips.md#MasterDocument) | [General.Documents](General.Documents.md) | In a multi-document tree, this is the root document, that created the whole tree. If this is the root it is equal to Id [Required] |
| [Parent](Applications.Fleet.Trips.md#Parent) | [General.Documents](General.Documents.md) (nullable) | In a multi-document tree, this is the direct parent document. If this is the root it is null |
| [PrimeCauseDocument](Applications.Fleet.Trips.md#PrimeCauseDocument) | [General.Documents](General.Documents.md) (nullable) | The document that is the prime cause for creation of the current document |
| [ResponsiblePerson](Applications.Fleet.Trips.md#ResponsiblePerson) | [General.Contacts.Persons](General.Contacts.Persons.md) (nullable) | The person that is responsible for this order or transaction. It could be the sales person, the orderer, etc. |
| [ReverseOfDocument](Applications.Fleet.Trips.md#ReverseOfDocument) | [General.Documents](General.Documents.md) (nullable) | The document which the current document is reverse of |
| [Sequence](Applications.Fleet.Trips.md#Sequence) | [General.Sequences](General.Sequences.md) (nullable) | The sequence that will be used to give new numbers to the documents of this type |
| [ToCompanyDivision](Applications.Fleet.Trips.md#ToCompanyDivision) | [General.Contacts.CompanyDivisions](General.Contacts.CompanyDivisions.md) | The division of the company, receiving the document. null when the document is not received by any specific division |
| [ToParty](Applications.Fleet.Trips.md#ToParty) | [General.Contacts.Parties](General.Contacts.Parties.md) (nullable) | The party which should receive the document |
| [UserStatus](Applications.Fleet.Trips.md#UserStatus) | [General.DocumentTypeUserStatuses](General.DocumentTypeUserStatuses.md) (nullable) | The user status of this document if applicable for this document type. null means unknown or not yet set |
| [Crew](Applications.Fleet.Trips.md#Crew) | [Applications.Fleet.Crews](Applications.Fleet.Crews.md) | The crew, which operated the vehicle set. [Required] [Filter(multi eq)] |
| [VehicleSet](Applications.Fleet.Trips.md#VehicleSet) | [Applications.Fleet.VehicleSets](Applications.Fleet.VehicleSets.md) | The vehicle set for which the trip is reported. [Required] [Filter(multi eq)] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| DocumentAmounts | [General.DocumentAmounts](General.DocumentAmounts.md) |  
| Comments | [General.DocumentComments](General.DocumentComments.md) | List of [DocumentComment](General.DocumentComments.md) child objects, based on the [DocumentComment.Document](General.DocumentComments.md#Document) back reference 
| DistributedAmounts | [General.DocumentDistributedAmounts](General.DocumentDistributedAmounts.md) | List of [DocumentDistributedAmount](General.DocumentDistributedAmounts.md) child objects, based on the [DocumentDistributedAmount.Document](General.DocumentDistributedAmounts.md#Document) back reference 
| FileAttachments | [General.DocumentFileAttachments](General.DocumentFileAttachments.md) | List of [DocumentFileAttachment](General.DocumentFileAttachments.md) child objects, based on the [DocumentFileAttachment.Document](General.DocumentFileAttachments.md#Document) back reference 
| LineAmounts | [General.DocumentLineAmounts](General.DocumentLineAmounts.md) | List of [DocumentLineAmount](General.DocumentLineAmounts.md) child objects, based on the [DocumentLineAmount.Document](General.DocumentLineAmounts.md#Document) back reference 
| Prints | [General.DocumentPrints](General.DocumentPrints.md) | List of [DocumentPrint](General.DocumentPrints.md) child objects, based on the [DocumentPrint.Document](General.DocumentPrints.md#Document) back reference 
| StateChanges | [General.DocumentStateChanges](General.DocumentStateChanges.md) | List of [DocumentStateChange](General.DocumentStateChanges.md) child objects, based on the [DocumentStateChange.Document](General.DocumentStateChanges.md#Document) back reference 
| Versions | [General.DocumentVersions](General.DocumentVersions.md) | List of [DocumentVersion](General.Documents.md#DocumentVersion) child objects, based on the [DocumentVersion.Document](General.DocumentVersions.md#Document) back reference 
| Segments | [Applications.Fleet.TripSegments](Applications.Fleet.TripSegments.md) | List of [TripSegment](Applications.Fleet.TripSegments.md) child objects, based on the [Applications.Fleet.TripSegment.Trip](Applications.Fleet.TripSegments.md#Trip) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### CompleteTime

> Exact time, when the document was last completed[Filter(ge;le)]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### CreationTime

> Date/Time when the document was created [Required][Filter(ge;le)]

_Type_: **datetime**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  

### CreationUser

> The login name of the user, who created the document [Required][Filter(like)]

_Type_: **string**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### DocumentDate

> The date on which the document was issued [Required][Filter(eq;ge;le)][ORD]

_Type_: **datetime**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDate**  

### DocumentNo

> Document number, unique within Document_Type_Id [Required][Filter(eq;like)][ORD]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  

### DocumentVersion

> [Filter(eq;ge;le)]

_Type_: **int32**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  

### DocumentNotes

> Notes for this Document

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ParentDocumentRelationshipType

> Type of relationship between the current document and the parent document(s). Affects the constraints for execution/completion for the documents. Possible values: 'S' = 'Subtask', 'N' = 'Next task'.

_Type_: **[General.ParentDocumentRelationshipType](Applications.Fleet.Trips.md#ParentDocumentRelationshipType) (nullable)**  
Relationship between parent and child documents  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| Subtask | The child document is a sub-task of the parent document. (Complete child to complete parent) <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Subtask' |
| NextTask | The child document is next task of the parent document. (Complete parent to complete child) <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'NextTask' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### PlanningOnly

> Indicates that the document is used only for planning (and as consequence its state cannot be greater than Planned) [Required]

_Type_: **boolean (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### ReadOnly

> True - the document is read only; false - the document is not read only [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### ReferenceDate

> The date to which this document refers, i.e. when the action really occurred. If null, Document_Date is taken [Filter(ge;le)]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### ReferenceDocumentNo

> The number of the document (issued by the other party), which was the reason for the creation of the current document. The numebr should be unique within the party documents [Filter(eq;like)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### ReleaseTime

> Exact time, when the document was first released [Filter(ge;le)]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### State

> 0=New;5=Corrective;10=Computer Planned;20=Human Planned;30=Released;40=Completed;50=Closed [Required][Filter(eq;ge;le)]

_Type_: **[General.DocumentState](Applications.Fleet.Trips.md#State)**  
Enumeration of document system states  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Void

> True if the document is null and void [Required][Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### VoidReason

> Reason for voiding the document, entered by the user

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### VoidTime

> Date/time when the document has become void

_Type_: **datetime (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### VoidUser

> The user who voided the document

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### EntityName

> The entity name of the document equal to the entity name of the document type.[Filter(eq)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  

### IsReleased

> True if the document is not void and its state is released or greater. [Required] [Default(false)] [Filter(eq)] [ReadOnly]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### IsSingleExecution

> Specifies whether the document is a single execution of its order document. [Required] [Default(false)] [Filter(eq)] [ReadOnly]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### PrimaryVehicleEndingMileage

> Mileage of the primary vehicle in the vehicle set at the ending of the trip. null means unknown.

_Type_: **decimal (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### PrimaryVehicleStartingMileage

> Mileage of the primary vehicle in the vehicle set at the begining of the trip. null means unknown.

_Type_: **decimal (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### AccessKey

> The access key, containing the user permissions for this document. null means that all users have unlimited permissions

_Type_: **[Systems.Security.AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### AdjustedDocument

> The primary document, which the current document adjusts. null when this is not an adjustment document

_Type_: **[General.Documents](General.Documents.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### AssignedToUser

> The user to which this document is assigned for handling. null means that the document is not assigned to specific user

_Type_: **[Systems.Security.Users](Systems.Security.Users.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### CurrencyDirectory

> The currency directory, containing all the convertion rates, used by the document. null means that the document does not need currency convertions

_Type_: **[General.CurrencyDirectories](General.CurrencyDirectories.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### DocumentType

> The user defined type of the document. Determines document behaviour, properties, additional amounts, validation, generations, etc. [Required]

_Type_: **[General.DocumentTypes](General.DocumentTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### EnterpriseCompany

> The enterprise company which issued the document [Required]

_Type_: **[General.EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### EnterpriseCompanyLocation

> The enterprise company location which issued the document. null means that there is only one location within the enterprise company and locations are not used

_Type_: **[General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### FromCompanyDivision

> The division of the company, issuing the document. null when the document is not issued by any specific division

_Type_: **[General.Contacts.CompanyDivisions](General.Contacts.CompanyDivisions.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### FromParty

> The party which issued the document [Required]

_Type_: **[General.Contacts.Parties](General.Contacts.Parties.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### MasterDocument

> In a multi-document tree, this is the root document, that created the whole tree. If this is the root it is equal to Id [Required]

_Type_: **[General.Documents](General.Documents.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Parent

> In a multi-document tree, this is the direct parent document. If this is the root it is null

_Type_: **[General.Documents](General.Documents.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### PrimeCauseDocument

> The document that is the prime cause for creation of the current document

_Type_: **[General.Documents](General.Documents.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### ResponsiblePerson

> The person that is responsible for this order or transaction. It could be the sales person, the orderer, etc.

_Type_: **[General.Contacts.Persons](General.Contacts.Persons.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### ReverseOfDocument

> The document which the current document is reverse of

_Type_: **[General.Documents](General.Documents.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### Sequence

> The sequence that will be used to give new numbers to the documents of this type

_Type_: **[General.Sequences](General.Sequences.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### ToCompanyDivision

> The division of the company, receiving the document. null when the document is not received by any specific division

_Type_: **[General.Contacts.CompanyDivisions](General.Contacts.CompanyDivisions.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ToParty

> The party which should receive the document

_Type_: **[General.Contacts.Parties](General.Contacts.Parties.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### UserStatus

> The user status of this document if applicable for this document type. null means unknown or not yet set

_Type_: **[General.DocumentTypeUserStatuses](General.DocumentTypeUserStatuses.md) (nullable)**  
_Supported Filters_: **EqualsIn**  
_Supports Order By_: **False**  

### Crew

> The crew, which operated the vehicle set. [Required] [Filter(multi eq)]

_Type_: **[Applications.Fleet.Crews](Applications.Fleet.Crews.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### VehicleSet

> The vehicle set for which the trip is reported. [Required] [Filter(multi eq)]

_Type_: **[Applications.Fleet.VehicleSets](Applications.Fleet.VehicleSets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.Fleet.Trips erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.Fleet.Trips erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.Fleet.Trips erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Fleet_Trips?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Fleet_Trips?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Fleet_Trips?$top=10>
