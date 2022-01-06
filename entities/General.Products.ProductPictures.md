---
uid: General.Products.ProductPictures
---
# General.Products.ProductPictures Entity

**Namespace:** [General.Products](General.Products.md)  

Pictures of products. Entity: Gen_Product_Pictures

## Default Visualization
Default Display Text Format:  
_{Product.Name:T}_  
Default Search Members:  
_Product.Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Comments](General.Products.ProductPictures.md#comments) | string (254) __nullable__ | Comments for this ProductPicture. 
| [Id](General.Products.ProductPictures.md#id) | guid |  
| [IsDefault](General.Products.ProductPictures.md#isdefault) | boolean | True=This is the default picture for the product and the size class; false=otherwise. `Required` `Default(false)` `Filter(eq)` 
| [LastUpdateTime](General.Products.ProductPictures.md#lastupdatetime) | datetime __nullable__ | The exact server time, when the picture was last updated. Set automatically. `Filter(ge;le)` `ReadOnly` 
| [ObjectVersion](General.Products.ProductPictures.md#objectversion) | int32 |  
| [Picture](General.Products.ProductPictures.md#picture) | byte[] __nullable__ | The actual product picture. Can be null if we insert only some comments. 
| [PictureNo](General.Products.ProductPictures.md#pictureno) | int32 | Unique picture number within the product. Also used for sorting. `Required` `Filter(eq;like)` 
| [PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) | [PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) __nullable__ | Specifies the relative picture size and usage. S=Small picture (thumbnail), L=Large picture (full size), null=unspecified. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](General.Products.ProductPictures.md#product) | [Products](General.Products.Products.md) | The <see cref="Product"/> to which this ProductPicture belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Comments

Comments for this ProductPicture.

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsDefault

True=This is the default picture for the product and the size class; false=otherwise. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

_Front-End Recalc Expressions:_  
`( obj.Product.Pictures.Take( 2).Count( ) == 1)`
### LastUpdateTime

The exact server time, when the picture was last updated. Set automatically. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Picture

The actual product picture. Can be null if we insert only some comments.

_Type_: **byte[] __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### PictureNo

Unique picture number within the product. Also used for sorting. `Required` `Filter(eq;like)`

_Type_: **int32**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.Product.Pictures.Select( c => c.PictureNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Product.Pictures.Select( c => c.PictureNo).DefaultIfEmpty( 0).Max( ) + 10)`
### PictureSizeClass

Specifies the relative picture size and usage. S=Small picture (thumbnail), L=Large picture (full size), null=unspecified.

_Type_: **[PictureSizeClass](General.Products.ProductPictures.md#picturesizeclass) __nullable__**  
Allowed values for the `PictureSizeClass`(General.Products.ProductPictures.md#picturesizeclass) data attribute  
_Allowed Values (General.Products.ProductPicturesRepository.PictureSizeClass Enum Members)_  

| Value | Description |
| ---- | --- |
| SmallPictureThumbnail | SmallPictureThumbnail value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'SmallPictureThumbnail' |
| LargePictureFullSize | LargePictureFullSize value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'LargePictureFullSize' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Product

The <see cref="Product"/> to which this ProductPicture belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Products](General.Products.Products.md)**  
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

[!list limit=1000 erp.entity=General.Products.ProductPictures erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductPictures erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Products_ProductPictures?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Products_ProductPictures?$top=10>

