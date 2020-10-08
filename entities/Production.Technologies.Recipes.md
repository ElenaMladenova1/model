# Production.Technologies.Recipes

Contains the characteristics of operations used to create products. Entity: Prd_Recipes

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.Recipes.md#Id) | guid |  
| [CreationTime](Production.Technologies.Recipes.md#CreationTime) | datetime (nullable) | Date and time when the Recipe was created. [Filter(ge;le)] [ReadOnly] 
| [CreationUser](Production.Technologies.Recipes.md#CreationUser) | string (nullable) | Login name of the user, who created the Recipe. [Filter(like)] [ReadOnly] 
| [ExpiryDate](Production.Technologies.Recipes.md#ExpiryDate) | datetime (nullable) | The last date, when the recipe should be used. null means that the recipe might still be in use. [Filter(ge;le)] 
| [IsDefault](Production.Technologies.Recipes.md#IsDefault) | boolean | Default for period: Release_Date - Expiry_Date. [Required] [Default(false)] [Filter(eq)] 
| [Notes](Production.Technologies.Recipes.md#Notes) | string (nullable) | User comments for the recipe. 
| [Price](Production.Technologies.Recipes.md#Price) | [Amount](../data-types/Amount.md) | The price for the specified Produce_Quantity. [Currency: Product.CostingCurrency] [Required] [Default(0)] 
| [PricePerLot](Production.Technologies.Recipes.md#PricePerLot) | [Amount](../data-types/Amount.md) | Price for one lot of the product (according to Lot_Size_Quantity_Base). [Currency: Product.CostingCurrency] [Required] [Default(0)] 
| [ProduceQuantity](Production.Technologies.Recipes.md#ProduceQuantity) | [Quantity](../data-types/Quantity.md) | Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(1)] 
| [Name](Production.Technologies.Recipes.md#Name) | string | The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation. [Required] [Filter(like)] 
| [ReleaseDate](Production.Technologies.Recipes.md#ReleaseDate) | datetime | The date, when the recipe was released to production. [Required] [Default(Today)] [Filter(ge;le)] 
| [ScrapRate](Production.Technologies.Recipes.md#ScrapRate) | decimal | The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe. [Required] [Default(0)] 
| [UpdateTime](Production.Technologies.Recipes.md#UpdateTime) | datetime (nullable) | Date and time when the Recipe was last updated. [Filter(ge;le)] [ReadOnly] 
| [UpdateUser](Production.Technologies.Recipes.md#UpdateUser) | string (nullable) | Login name of the user, who last updated the Recipe. [Filter(like)] [ReadOnly] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrencyDirectory](Production.Technologies.Recipes.md#CurrencyDirectory) | [General.CurrencyDirectories](General.CurrencyDirectories.md) (nullable) | Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product. [Filter(multi eq)] |
| [PrincipalRecipe](Production.Technologies.Recipes.md#PrincipalRecipe) | [Production.Technologies.PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable) | The prinicipal recipe, used to create this recipe. null means that this recipe was created without the help of principal recipe. [Filter(multi eq)] |
| [Product](Production.Technologies.Recipes.md#Product) | [General.Products.Products](General.Products.Products.md) (nullable) | The Id of the produced product. [Filter(multi eq)] |
| [Store](Production.Technologies.Recipes.md#Store) | [Logistics.Inventory.Stores](Logistics.Inventory.Stores.md) (nullable) | The store for which this technology is valid. The store is matched with the output store specified in the production order. When null, the technology is valid for all stores. [Filter(multi eq)] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Ingredients | [Production.Technologies.RecipeIngredients](Production.Technologies.RecipeIngredients.md) | List of [RecipeIngredient](Production.Technologies.RecipeIngredients.md) child objects, based on the [Production.Technologies.RecipeIngredient.Recipe](Production.Technologies.RecipeIngredients.md#Recipe) back reference 
| Operations | [Production.Technologies.RecipeOperations](Production.Technologies.RecipeOperations.md) | List of [RecipeOperation](Production.Technologies.RecipeOperations.md) child objects, based on the [Production.Technologies.RecipeOperation.Recipe](Production.Technologies.RecipeOperations.md#Recipe) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### CreationTime

> Date and time when the Recipe was created. [Filter(ge;le)] [ReadOnly]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### CreationUser

> Login name of the user, who created the Recipe. [Filter(like)] [ReadOnly]

_Type_: **string (nullable)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### ExpiryDate

> The last date, when the recipe should be used. null means that the recipe might still be in use. [Filter(ge;le)]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### IsDefault

> Default for period: Release_Date - Expiry_Date. [Required] [Default(false)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Notes

> User comments for the recipe.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Price

> The price for the specified Produce_Quantity. [Currency: Product.CostingCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### PricePerLot

> Price for one lot of the product (according to Lot_Size_Quantity_Base). [Currency: Product.CostingCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### ProduceQuantity

> Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(1)]

_Type_: **[Quantity](../data-types/Quantity.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### Name

> The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation. [Required] [Filter(like)]

_Type_: **string**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### ReleaseDate

> The date, when the recipe was released to production. [Required] [Default(Today)] [Filter(ge;le)]

_Type_: **datetime**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  

### ScrapRate

> The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe. [Required] [Default(0)]

_Type_: **decimal**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### UpdateTime

> Date and time when the Recipe was last updated. [Filter(ge;le)] [ReadOnly]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### UpdateUser

> Login name of the user, who last updated the Recipe. [Filter(like)] [ReadOnly]

_Type_: **string (nullable)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  


## Reference Details

### CurrencyDirectory

> Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product. [Filter(multi eq)]

_Type_: **[General.CurrencyDirectories](General.CurrencyDirectories.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### PrincipalRecipe

> The prinicipal recipe, used to create this recipe. null means that this recipe was created without the help of principal recipe. [Filter(multi eq)]

_Type_: **[Production.Technologies.PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Product

> The Id of the produced product. [Filter(multi eq)]

_Type_: **[General.Products.Products](General.Products.Products.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Store

> The store for which this technology is valid. The store is matched with the output store specified in the production order. When null, the technology is valid for all stores. [Filter(multi eq)]

_Type_: **[Logistics.Inventory.Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Production.Technologies.Recipes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Production.Technologies.Recipes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Production.Technologies.Recipes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Production_Technologies_Recipes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Production_Technologies_Recipes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Prd_Recipes?$top=10>
