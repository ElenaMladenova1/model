---
uid: Systems.Core.ObjectFiles
---
# Systems.Core.ObjectFiles Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains files attached to objects. Entity: Sys_Object_Files

## Default Visualization
Default Display Text Format:  
_{FileName}_  
Default Search Members:  
_PurposeCode; FileName_  
Code Data Member:  
_PurposeCode_  
Name Data Member:  
_FileName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  
Aggregate Root:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | [ContentLocation](Systems.Core.ObjectFiles.md#contentlocation) | The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link. `Required` `Default("EMB")` `Filter(multi eq)` `Introduced in version 20.1` 
| [CreationTimeUtc](Systems.Core.ObjectFiles.md#creationtimeutc) | datetime | Time (in UTC), when the file was created. `Required` `Default(NowUtc)` `Introduced in version 20.1` 
| [DisplayText](Systems.Core.ObjectFiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EmbeddedFileContents](Systems.Core.ObjectFiles.md#embeddedfilecontents) | byte[] __nullable__ | Contains the contents of the file, when it is embedded in the database. null for linked files. 
| [FileName](Systems.Core.ObjectFiles.md#filename) | string (254) | The file name of the linked or embedded file. `Required` `Filter(eq;like)` 
| [FileSizeBytes](Systems.Core.ObjectFiles.md#filesizebytes) | int32 __nullable__ | The file size in bytes. If empty the file size is unknown. `Introduced in version 22.1.5.46` 
| [Id](Systems.Core.ObjectFiles.md#id) | guid |  
| [LastUpdateTimeUtc](Systems.Core.ObjectFiles.md#lastupdatetimeutc) | datetime | Time (in UTC), when the file was last updated. `Required` `Default(NowUtc)` `Introduced in version 20.1` 
| [LinkedFilePath](Systems.Core.ObjectFiles.md#linkedfilepath) | string (1024) __nullable__ | When the file is linked, contains the full path (including the file name) to the linked file. null for embedded files. `Filter(eq;like)` 
| [MediaHeight](Systems.Core.ObjectFiles.md#mediaheight) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1` 
| [MediaType](Systems.Core.ObjectFiles.md#mediatype) | string (128) __nullable__ | For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). null for non-media files. `Introduced in version 20.1` 
| [MediaWidth](Systems.Core.ObjectFiles.md#mediawidth) | int32 __nullable__ | Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1` 
| [Notes](Systems.Core.ObjectFiles.md#notes) | string (max) __nullable__ | User notes for the file attachment. 
| [ObjectVersion](Systems.Core.ObjectFiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PurposeCode](Systems.Core.ObjectFiles.md#purposecode) | string (32) __nullable__ | Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects. `Filter(eq)` 
| [Section](Systems.Core.ObjectFiles.md#section) | string (64) __nullable__ | A section name used to group files. `Introduced in version 21.1.1.84` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Systems.Core.ObjectFiles.md#creationuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who created the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1` |
| [LastUpdateUser](Systems.Core.ObjectFiles.md#lastupdateuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who performed the last update to the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1` |
| [Object](Systems.Core.ObjectFiles.md#object) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object to which the file is attached. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ContentLocation

The location of the file contents. EMB=Embedded in the database; URL=Internet URL; FSL=File system link. `Required` `Default("EMB")` `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[ContentLocation](Systems.Core.ObjectFiles.md#contentlocation)**  
Allowed values for the `ContentLocation`(Systems.Core.ObjectFiles.md#contentlocation) data attribute  
_Allowed Values (Systems.Core.ObjectFilesRepository.ContentLocation Enum Members)_  

| Value | Description |
| ---- | --- |
| Embedded | The content is stored in the database. Stored as 'EMB'. <br /> _Database Value:_ 'EMB' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Embedded' |
| InternetUrl | Internet resource location. Stored as 'URL'. <br /> _Database Value:_ 'URL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InternetUrl' |
| FileSystemLink | Path to the file in the local file system. Stored as 'FSL'. <br /> _Database Value:_ 'FSL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FileSystemLink' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Embedded**  

### CreationTimeUtc

Time (in UTC), when the file was created. `Required` `Default(NowUtc)` `Introduced in version 20.1`

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### EmbeddedFileContents

Contains the contents of the file, when it is embedded in the database. null for linked files.

_Type_: **byte[] __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### FileName

The file name of the linked or embedded file. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### FileSizeBytes

The file size in bytes. If empty the file size is unknown. `Introduced in version 22.1.5.46`

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LastUpdateTimeUtc

Time (in UTC), when the file was last updated. `Required` `Default(NowUtc)` `Introduced in version 20.1`

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  

### LinkedFilePath

When the file is linked, contains the full path (including the file name) to the linked file. null for embedded files. `Filter(eq;like)`

_Type_: **string (1024) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **1024**  

### MediaHeight

Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1`

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### MediaType

For media files, contains the Media Type as per the IANA registry (formerly known as the MIME Type). null for non-media files. `Introduced in version 20.1`

_Type_: **string (128) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  

### MediaWidth

Used (non-null) only for media files. Specifies the width for displaying the media. `Introduced in version 20.1`

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Notes

User notes for the file attachment.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### PurposeCode

Code, designating the usage purpose of the file. The meaning of each code is up to the application with the exception of 'default/image', which is standartised as the default image for many types of objects. `Filter(eq)`

_Type_: **string (32) __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  

### Section

A section name used to group files. `Introduced in version 21.1.1.84`

_Type_: **string (64) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  


## Reference Details

### CreationUser

The user, who created the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### LastUpdateUser

The user, who performed the last update to the file record. null if it is unknown. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Object

The object to which the file is attached. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


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

[!list limit=1000 erp.entity=Systems.Core.ObjectFiles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ObjectFiles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_ObjectFiles?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_ObjectFiles?$top=10>

