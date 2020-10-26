# Big-Mart-Sales

### Objective

We want to analyze how sales vary by outlet type (Grocery store versus Supermarket Type 1, 2, or 3) and city type (Tier 1, 2 and 3)

### Data

2013 sales data for 1559 products across 10 stores in different cities

Source: https://code.datasciencedojo.com/tshrivas/dojoHub/tree/a152a17dee24dcfcc10bb75c77c2e88cdcf90212/Big%20Mart%20Sales%20DataSet

Attributes:

- **Item_Weight**: Weight of the product
- **Item_Fat_Content**: Low Fat or Regular
- **Item_Visibility**: Percentage of total display area of all products in a store allocated to this product
- **Item_Type**:	Dairy, Soft Drinks, Meat, Fruits and Vegetables, Household, Baking Goods, Snack Foods, Frozen Foods, Breakfast, Health and Hygiene, Hard Drinks, Canned, Breads, Starchy Foods, Others, Seafood
- **Item_MRP**:	Maximum Retail Price (list price) of the product
- **Outlet_ID**:	Unique store ID
- **Outlet_Year**:	Year in which store was opened
- **Outlet_Size**:	Store size**: [High, Medium, Small]
- **City_Type**:	Size of city where store is located [Tier 1, Tier 2, Tier 3]
- **Outlet_Type**:	Grocery Store, Supermarket Type1, Supermarket Type2, Supermarket Type3
- **Item_Sales**:	Sales of product in this store

# Variable selection for Mixed Level Analysis

#' Dependent variable: Item_Sales

#' Lower (item) level variables that affect item sales:
#'   Item_ID:          Unit of analysis (will not be included in model)
#'   Item_Visibility:  More visible products should sell more
#'   Item_Type:        Certain item types such as dairy or vegetables may sell more
#'   Item_MRP:         Pricier items may sell less

#' Upper (store) level Variables that affect item sales
#'   Outlet_ID:        Unit of analysis for upper-level (must be included in model)
#'   Outlet_Type:      First part of analysis: how sales vary by outlet type
#'   City_Type:        Second part of analysis: how sales vary by city type
#'   Outlet_Age:       New variable; 2013 - Outlet_Year

#' Note: Outlet_year (year of founding of outlet) doesn't make sense as a predictor,
#' but older outlets may have more established clientale and may sell more compared
#' to new ones. We measure Outlet_Age as current year (2013) - year of founding
