# Query Pos_Devices_Table_Load_Navigator


## Summary

| Name | Type | Description |
| - | - | --- |
|[Pos_Device_Id](#pos_device_id)|`uniqueidentifier` `PK`||
|[Pos_Terminal_Id](#pos_terminal_id)|`uniqueidentifier` |The POS terminal, to which this device is attached.|
|[Device_Type](#device_type)|`nvarchar` Allowed: `PAY`, `CSH`, `FIP`, `OTH`|Type of the POS device. PAY=Payment Terminal; CSH=Cash Drawer; FIP=Fiscal Printer; OTH=Other.|
|[Device_Registration_No](#device_registration_no)|`nvarchar` |The unique registration number of the device, assigned by the manufacturer. NULL means the number is unknown or N/A.|
|[Protocol_Name](#protocol_name)|`nvarchar` Allowed: `ERPNET_FP`|The name of the protocol, which can be used to communicate with the device. NULL means that the protocol is unknown and programmatic communication with the device would not be performed.|
|[Electronic_Address](#electronic_address)|`nvarchar` |The absolute address (Internet or other) which can be used for electronic communication with the device. The address should contain communication protocol/type, colon, space, then the actual address. Addresses, which are local to a specific computer, should also include the computer name. For example: "COM: PC_WORK1:COM1", "HTTP: https://<addr>", etc.|
|[Settings_Json](#settings_json)|`nvarchar` |Settings and operator access codes for the POS device. The data is stored as Json, encrypted for the current application server instance. NULL means that there are no settings for this device.|
|[Is_Active](#is_active)|`bit` |Indicates whether the device is currently active and can be choosen from drop-downs in new records.|
|[Pos_Location_Id](#pos_location_id)|`uniqueidentifier` ||
|[Pos_Terminal_Code](#pos_terminal_code)|`nvarchar` |Unique (within the location) code of the POS terminal.|
|[Pos_Terminal_Name](#pos_terminal_name)|`nvarchar` `ML`|The multi-language name of the terminal, like "Cash 1", "Self-checkout 5", etc.|
|[Pos_Terminal_Is_Active](#pos_terminal_is_active)|`bit` |Represents whether the POS terminal is active and can be chosen from drop-downs for new records.|
|[Default_Fiscal_Printer_Pos_Device_Id](#default_fiscal_printer_pos_device_id)|`uniqueidentifier` |The POS Fiscal Device which is set by default in documents when the POS Terminal is selected.|
|[Enterprise_Company_Id](#enterprise_company_id)|`uniqueidentifier` |The enterprise company of the POS location.|
|[Enterprise_Company_Location_Id](#enterprise_company_location_id)|`uniqueidentifier` |The enterprise company location of the POS location. Currently, only one POS location is allowed for each company location.|
|[Pos_Location_Code](#pos_location_code)|`nvarchar` |Unique (with the enterprise company) code of this POS location.|
|[Pos_Location_Is_Active](#pos_location_is_active)|`bit` |Indicates whether the POS location is currently active and can be chosen in drop-downs, etc.|

## Columns

### Pos_Device_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Pos_Terminal_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Device_Type

| Property | Value |
| - | - |
|Type|nvarchar|

### Device_Registration_No

| Property | Value |
| - | - |
|Type|nvarchar|

### Protocol_Name

| Property | Value |
| - | - |
|Type|nvarchar|

### Electronic_Address

| Property | Value |
| - | - |
|Type|nvarchar|

### Settings_Json

| Property | Value |
| - | - |
|Type|nvarchar|

### Is_Active

| Property | Value |
| - | - |
|Type|bit|

### Pos_Location_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Pos_Terminal_Code

| Property | Value |
| - | - |
|Type|nvarchar|

### Pos_Terminal_Name

| Property | Value |
| - | - |
|Type|nvarchar|

### Pos_Terminal_Is_Active

| Property | Value |
| - | - |
|Type|bit|

### Default_Fiscal_Printer_Pos_Device_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Enterprise_Company_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Enterprise_Company_Location_Id

| Property | Value |
| - | - |
|Type|uniqueidentifier|

### Pos_Location_Code

| Property | Value |
| - | - |
|Type|nvarchar|

### Pos_Location_Is_Active

| Property | Value |
| - | - |
|Type|bit|

