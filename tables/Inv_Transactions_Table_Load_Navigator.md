# Query Inv_Transactions_Table_Load_Navigator


## Summary

| Name | Type | Description |
| - | - | --- |
|[Store_Id](#store_id)|`uniqueidentifier` ||
|[Movement_Type](#movement_type)|`nvarchar` Allowed: `I`, `R`||
|[Cost_Source](#cost_source)|`nvarchar` Allowed: `S`, `D`, Readonly||
|[Document_Cost](#document_cost)|`decimal(0, 0)` ||
|[Document_Currency_Id](#document_currency_id)|`uniqueidentifier` ||
|[Base_Cost](#base_cost)|`decimal(0, 0)` ||
|[Base_Currency_Id](#base_currency_id)|`uniqueidentifier` ||
|[Document_Id](#document_id)|`uniqueidentifier` `PK`||
|[From_Party_Id](#from_party_id)|`uniqueidentifier` ||
|[Enterprise_Company_Id](#enterprise_company_id)|`uniqueidentifier` ||
|[Document_Type_Id](#document_type_id)|`uniqueidentifier` ||
|[Document_No](#document_no)|`nvarchar` ||
|[Document_Date](#document_date)|`date` ||
|[Reference_Date](#reference_date)|`datetime` ||
|[State](#state)|`smallint` Allowed: `0`, `5`, `10`, `20`, `30`, `40`, `50`, Readonly|false|
|[Void](#void)|`bit` Readonly||
|[To_Party_Id](#to_party_id)|`uniqueidentifier` ||
|[Currency_Directory_Id](#currency_directory_id)|`uniqueidentifier` ||
|[Master_Document_Id](#master_document_id)|`uniqueidentifier` ||
|[Parent_Document_Id](#parent_document_id)|`uniqueidentifier` ||
|[Adjusted_Document_Id](#adjusted_document_id)|`uniqueidentifier` ||
|[Adjustment_Number](#adjustment_number)|`int` Readonly||
|[Creation_Time](#creation_time)|`datetime` Readonly||
|[Creation_User](#creation_user)|`nvarchar` Readonly||
|[Void_Time](#void_time)|`datetime` Readonly||
|[Void_User](#void_user)|`nvarchar` Readonly||
|[Adjustment_Time](#adjustment_time)|`datetime` Readonly||
|[Adjustment_User](#adjustment_user)|`nvarchar` Readonly||
|[Read_Only](#read_only)|`bit` Readonly||
|[Notes](#notes)|`nvarchar` ||
|[Document_Version](#document_version)|`int` Readonly||
|[Responsible_Person_Id](#responsible_person_id)|`uniqueidentifier` ||
|[Void_Reason](#void_reason)|`nvarchar` Readonly||
|[Reverse_Of_Document_Id](#reverse_of_document_id)|`uniqueidentifier` Readonly||
|[Enterprise_Company_Location_Id](#enterprise_company_location_id)|`uniqueidentifier` ||
|[Planning_Only](#planning_only)|`bit` Readonly||
|[Prime_Cause_Document_Id](#prime_cause_document_id)|`uniqueidentifier` ||
|[Release_Time](#release_time)|`datetime` Readonly||
|[Complete_Time](#complete_time)|`datetime` Readonly||
|[Parent_Document_Relationship_Type](#parent_document_relationship_type)|`nvarchar` Allowed: `S`, `N`||
|[Reference_Document_No](#reference_document_no)|`nvarchar` ||
|[User_Status_Id](#user_status_id)|`uniqueidentifier` Readonly||
|[From_Company_Division_Id](#from_company_division_id)|`uniqueidentifier` ||
|[To_Company_Division_Id](#to_company_division_id)|`uniqueidentifier` ||
|[Entity_Name](#entity_name)|`nvarchar` |The entity name of the document header.|
|[Row_Version](#row_version)|`timestamp` ||
|[Transaction_Id](#transaction_id)|`uniqueidentifier` `PK`||
|[Issuing_Person_Id](#issuing_person_id)|`uniqueidentifier` ||
|[Receiving_Person_Id](#receiving_person_id)|`uniqueidentifier` ||
|[Is_Scrap](#is_scrap)|`bit` ||
|[Scrap_Type_Id](#scrap_type_id)|`uniqueidentifier` ||
|[Parent_Store_Order_Id](#parent_store_order_id)|`uniqueidentifier` ||
|[AccountedSum](#accountedsum)|`decimal(0, 0)` ||
|[Adjusted_Document_Cost](#adjusted_document_cost)|`decimal(0, 0)` ||
|[Adjusted_Base_Cost](#adjusted_base_cost)|`decimal(0, 0)` ||

## Columns

### Store_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Movement_Type

| Property | Value |
| - | - |
|Type|nvarchar|

### Cost_Source

| Property | Value |
| - | - |
|Type|nvarchar|

### Document_Cost

| Property | Value |
| - | - |
|Type|decimal(0, 0)|

### Document_Currency_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Base_Cost

| Property | Value |
| - | - |
|Type|decimal(0, 0)|

### Base_Currency_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### From_Party_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Enterprise_Company_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Document_Type_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Document_No

| Property | Value |
| - | - |
|Type|nvarchar|

### Document_Date

| Property | Value |
| - | - |
|Type|date|

### Reference_Date

| Property | Value |
| - | - |
|Type|datetime|

### State

| Property | Value |
| - | - |
|Type|smallint|

### Void

| Property | Value |
| - | - |
|Type|bit|

### To_Party_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Currency_Directory_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Master_Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Parent_Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Adjusted_Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Adjustment_Number

| Property | Value |
| - | - |
|Type|int|

### Creation_Time

| Property | Value |
| - | - |
|Type|datetime|

### Creation_User

| Property | Value |
| - | - |
|Type|nvarchar|

### Void_Time

| Property | Value |
| - | - |
|Type|datetime|

### Void_User

| Property | Value |
| - | - |
|Type|nvarchar|

### Adjustment_Time

| Property | Value |
| - | - |
|Type|datetime|

### Adjustment_User

| Property | Value |
| - | - |
|Type|nvarchar|

### Read_Only

| Property | Value |
| - | - |
|Type|bit|

### Notes

| Property | Value |
| - | - |
|Type|nvarchar|

### Document_Version

| Property | Value |
| - | - |
|Type|int|

### Responsible_Person_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Void_Reason

| Property | Value |
| - | - |
|Type|nvarchar|

### Reverse_Of_Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Enterprise_Company_Location_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Planning_Only

| Property | Value |
| - | - |
|Type|bit|

### Prime_Cause_Document_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Release_Time

| Property | Value |
| - | - |
|Type|datetime|

### Complete_Time

| Property | Value |
| - | - |
|Type|datetime|

### Parent_Document_Relationship_Type

| Property | Value |
| - | - |
|Type|nvarchar|

### Reference_Document_No

| Property | Value |
| - | - |
|Type|nvarchar|

### User_Status_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### From_Company_Division_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### To_Company_Division_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Entity_Name

| Property | Value |
| - | - |
|Type|nvarchar|

### Row_Version

| Property | Value |
| - | - |
|Type|timestamp|

### Transaction_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Issuing_Person_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Receiving_Person_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Is_Scrap

| Property | Value |
| - | - |
|Type|bit|

### Scrap_Type_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Parent_Store_Order_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### AccountedSum

| Property | Value |
| - | - |
|Type|decimal(0, 0)|

### Adjusted_Document_Cost

| Property | Value |
| - | - |
|Type|decimal(0, 0)|

### Adjusted_Base_Cost

| Property | Value |
| - | - |
|Type|decimal(0, 0)|

