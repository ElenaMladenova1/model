# Query Pdm_Personal_Data_Processes_Table_Load_Navigator


## Summary

| Name | Type | Description |
| - | - | --- |
|[Personal_Data_Process_Id](#personal_data_process_id)|`uniqueidentifier` `PK`|Personal Data Management Process|
|[Code](#code)|`nvarchar` |Unique process code.|
|[Name](#name)|`nvarchar` `ML`|Name of the process (Multilanguage).|
|[Description](#description)|`nvarchar` |Description of the process.|
|[Enterprise_Company_Id](#enterprise_company_id)|`uniqueidentifier` |The enterprise company, which owns the process.|
|[Processing_Role](#processing_role)|`nvarchar` Allowed: `C`, `P`|The role of the enterprise company in the process - Controller or Processor. The controller owns the personal data process. The processor operates on behalf of the controller. C=Controller; P=Processor. |
|[Retention_Period_Months](#retention_period_months)|`int` |The period in months, for which the data is kept. Null when the period is unknown or N/A.|
|[List_Of_Used_Software](#list_of_used_software)|`nvarchar` |Comma-separated list of the names of the software products used to process the data.|
|[Process_Owner_Person_Id](#process_owner_person_id)|`uniqueidentifier` |The owner and responsible person for the process.|
|[List_Of_Technical_Measures](#list_of_technical_measures)|`nvarchar` |Comma-separated list of technical measures taken to keep the data privacy. Common measures include Pseudonymisation, Encryption, Data Access Audit, etc.|
|[Data_Subject_Category](#data_subject_category)|`nvarchar` Allowed: `EMP`, `JOB`, `CON`, `CUS`, `SUP`, `PAR`, `OTH`|The category of data subjects (persons), whose data is processed. EMP=Employees; JOB=Job Candidates; CON=Contractors; CUS=Customers; SUP=Suppliers; PAR=Partners; OTH=Other.|
|[Contains_Sensitive_Data](#contains_sensitive_data)|`bit` |True if sensitive personal data is processed (racial, political, criminal, biometric, etc).|
|[List_Of_Data_Categories](#list_of_data_categories)|`nvarchar` |Comma-separated list of categories of personal data (both sensitive and non-sensitive) processed by this process. Common sensitive types of data include racial, political views, religion, trade union membership, sex life, criminal records, etc.|
|[Legal_Basis_For_Processing](#legal_basis_for_processing)|`nvarchar` Allowed: `INT`, `CST`, `CTR`, `LEG`, `VIT`, `PUB`|The basis on which the data is processed. INT=Legitimate Interest; CST=Consent; CTR=Contract; LEG=Legal Compliance; VIT=Vital Interests; PUB=Public Interest;|
|[List_Of_Data_Recipient_Categories](#list_of_data_recipient_categories)|`nvarchar` |Comma-separated list of types of data users. Usual categories include Staff, Public Authority, Contractor, etc.|
|[List_Of_Processing_Purposes](#list_of_processing_purposes)|`nvarchar` |Comma-separated list of processing purposes. Common purposes include Invoicing, Newsletter, Notifications, Repeatable Orders, etc.|
|[List_Of_Transfers_To_Third_Countries](#list_of_transfers_to_third_countries)|`nvarchar` |Comma-separated list of third countries, to which data is sent.|
|[Third_Country_Transfers_Safeguards](#third_country_transfers_safeguards)|`nvarchar` |Description of safeguards, taken to protect personal data in case of third country transfers.|
|[Notes](#notes)|`nvarchar` ||
|[Row_Version](#row_version)|`timestamp` ||
|[Establish_Date](#establish_date)|`date` |The data on which the process was established and started functioning.|
|[Discontinuation_Date](#discontinuation_date)|`date` |The date on which the process was discontinued. Null if the process is still active.|

## Columns

### Personal_Data_Process_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Code

| Property | Value |
| - | - |
|Type|nvarchar|

### Name

| Property | Value |
| - | - |
|Type|nvarchar|

### Description

| Property | Value |
| - | - |
|Type|nvarchar|

### Enterprise_Company_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Processing_Role

| Property | Value |
| - | - |
|Type|nvarchar|

### Retention_Period_Months

| Property | Value |
| - | - |
|Type|int|

### List_Of_Used_Software

| Property | Value |
| - | - |
|Type|nvarchar|

### Process_Owner_Person_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### List_Of_Technical_Measures

| Property | Value |
| - | - |
|Type|nvarchar|

### Data_Subject_Category

| Property | Value |
| - | - |
|Type|nvarchar|

### Contains_Sensitive_Data

| Property | Value |
| - | - |
|Type|bit|

### List_Of_Data_Categories

| Property | Value |
| - | - |
|Type|nvarchar|

### Legal_Basis_For_Processing

| Property | Value |
| - | - |
|Type|nvarchar|

### List_Of_Data_Recipient_Categories

| Property | Value |
| - | - |
|Type|nvarchar|

### List_Of_Processing_Purposes

| Property | Value |
| - | - |
|Type|nvarchar|

### List_Of_Transfers_To_Third_Countries

| Property | Value |
| - | - |
|Type|nvarchar|

### Third_Country_Transfers_Safeguards

| Property | Value |
| - | - |
|Type|nvarchar|

### Notes

| Property | Value |
| - | - |
|Type|nvarchar|

### Row_Version

| Property | Value |
| - | - |
|Type|timestamp|

### Establish_Date

| Property | Value |
| - | - |
|Type|date|

### Discontinuation_Date

| Property | Value |
| - | - |
|Type|date|

