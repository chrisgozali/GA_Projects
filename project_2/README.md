# Project 2 - Ames Housing Dataset
# Executive Summary

Abc network intends to launch a new docu-series on property flipping called "house hunters". The show's target audience is Americans who are passionate about transforming homes and reselling them at a profit. Its unique selling point is taking a data driven approach to property flipping. The first season of the series will feature houses in Ames, Iowa. I have been hired as a data scientist to  then idenfity features that are the best predictors of sale prices.

By analysing the housing dataset from Ames, Iowa Assessor’s Office containing individual property sales from 2006 - 2010, I have created a predictive model using linear regression with Ridge regularization.  A baseline model describing the average sale price of the entire dataset was used as a benchmark to beat when building the model. To verify that our model works well, we have been provided with a test sample with similar features to the dataset to test on kaggle.

This analyses is split in two parts. The first part is for exploratory data anlysis and the second part for model construction and regularization.

The model includes a total of 1 features:
- 4 continuous
- 3 nominal
- 3 discrete
- 2 ordinal
- 2 polynomial

## Problem Statement

The primary stakeholders of this analyses is the team in charge of "house hunters" at abc and the secondary stakeholders are American TV viewers who are keen on property flipping. Hence the analyses aims to deconstruct the dataset into digestible information and reduce the features to handful which most strongly predict sale prices, while uncovering interesting relationships between features and sale prices which would help in developing strategies for property flipping.

# Data Dictionary

## From original Dataset
|     Feature     |   Datatype   |                               Description                              |
|:---------------:|:--------:|:----------------------------------------------------------------------:|
| id              |   int64  |                                          Unique indentification number |
| pid             |   int64  |                                          Parcel indentification number |
| ms_subclass     | category |                   Identifies the type of dwelling involved in the sale |
| ms_zoning       |  object  |              Identifies the general zoning classification of the sale. |
| lot_frontage    |  float64 |                            Linear feet of street connected to property |
| lot_area        |   int64  |                                                Lot size in square feet |
| street          |  object  |                                         Type of road access to propert |
| alley           |  object  |                                       Type of alley access to property |
| lot_shape       |  object  |                                              General shape of property |
| land_contour    |  object  |                                               Flatness of the property |
| utilities       |  object  |                                            Type of utilities available |
| lot_config      |  object  |                                                      Lot configuration |
| land_slope      |  object  |                                                      Slope of property |
| neighborhood    |  object  |                             Physical locations within Ames city limits |
| condition_1     |  object  |                                        Proximity to various conditions |
| condition_2     |  object  |          Proximity to various conditions (if more than one is present) |
| bldg_type       |  object  |                                                       Type of dwelling |
| house_style     |  object  |                                                      Style of dwelling |
| overall_qual    |   int64  |                    Rating for overall material and finish of the house |
| overall_cond    |   int64  |                             Ratiing for overall condition of the house |
| year_built      |   int64  |                                             Original construction date |
| 3year_remod_add  |   int64  | Remodel date (same as construction date if no remodeling or additions) |
| roof_style      |  object  |                                                           Type of roof |
| roof_matl       |  object  |                                                          Roof material |
| exterior_1st    |  object  |                                             Exterior covering on house |
| exterior_2nd    |  object  |                 Exterior covering on house (if more than one material) |
| mas_vnr_type    |  object  |                                                    Masonry veneer type |
| mas_vnr_area    |  float64 |                                     Masonry veneer area in square feet |
| exter_qual      |  object  |                  Evaluates the quality of the material on the exterior |
| exter_cond      |  object  |        Evaluates the present condition of the material on the exterior |
| foundation      |  object  |                                                     Type of foundation |
| bsmt_qual       |  object  |                                           Evaluates height of basement |
| bsmt_cond       |  object  |                        Evaluates the general condition of the basement |
| bsmt_exposure   |  object  |                                Refers to walkout or garden level walls |
| bsmtfin_type_1  |  object  |                                       Rating of basement finished area |
| bsmtfin_sf_1    |  float64 |                                    Type 1 basement area in square feet |
| bsmtfin_type_2  |  object  |                   Rating of basement finished area (if multiple types) |
| bsmtfin_sf_2    |  float64 |                                     Type 2 basement area in square fee |
| bsmt_unf_sf     |  float64 |                                Unfinished basement area in square feet |
| total_bsmt_sf   |  float64 |                                     Total square feet of basement area |
| heating         |  object  |                                                        Type of heating |
| heating_qc      |  object  |                                          Heating quality and condition |
| central_air     |  object  |                                               Central air conditioning |
| electrical      |  object  |                                                      Electrical system |
| 1st_flr_sf      |   int64  |                                        First floor area in square feet |
| 2nd_flr_sf      |   int64  |                                       Second floor area in square feet |
| low_qual_fin_sf |   int64  |                       Low quality finished in square feet (all floors) |
| gr_liv_area     |   int64  |                           Above grade (ground) living area square feet |
| bsmt_full_bath  |  float64 |                                                Basement full bathrooms |
| bsmt_half_bath  |  float64 |                                                Basement half bathrooms |
| full_bath       |   int64  |                                             Full bathrooms above grade |
| half_bath       |   int64  |                                                 Half baths above grade |
| bedroom_abvgr   |   int64  |              Bedrooms above grade (does NOT include basement bedrooms) |
| kitchen_abvgr   |   int64  |                                                   Kitchens above grade |
| kitchen_qual    |  object  |                                                        Kitchen quality |
| totrms_abvgrd   |   int64  |                   Total rooms above grade (does not include bathrooms) |
| functional      |  object  |    Home functionality (Assume typical unless deductions are warranted) |
| fireplaces      |   int64  |                                                   Number of fireplaces |
| fireplace_qu    |  object  |                                                      Fireplace quality |
| garage_type     |  object  |                                                        Garage location |
| garage_yr_blt   |  float64 |                                                  Year garage was built |
| garage_finish   |  object  |                                          Interior finish of the garage |
| garage_cars     |  float64 |                                                    Garage car capacity |
| garage_area     |  float64 |                                          Size of garage in square feet |
| garage_qual     |  object  |                                                         Garage quality |
| garage_cond     |  object  |                                                       Garage condition |
| paved_drive     |  object  |                                                         Paved driveway |
| wood_deck_sf    |   int64  |                                          Wood deck area in square feet |
| open_porch_sf   |   int64  |                                         Open porch area in square feet |
| enclosed_porch  |   int64  |                                     Enclosed porch area in square feet |
| 3ssn_porch      |   int64  |                                 Three season porch area in square feet |
| screen_porch    |   int64  |                                       Screen porch area in square feet |
| pool_area       |   int64  |                                               Pool area in square feet |
| pool_qc         |  object  |                                                           Pool quality |
| fence           |  object  |                                                          Fence quality |
| misc_feature    |  object  |                  Miscellaneous feature not covered in other categories |
| misc_val        |   int64  |                                    Value of miscellaneous feature in $ |
| mo_sold         |   int64  |                                                        Month Sold (MM) |
| yr_sold         |   int64  |                                                       Year Sold (YYYY) |
| sale_type       |  object  |                                                           Type of sale |
| saleprice       |   int64  |                                            Sale price of property in $ |

## From selected model features
| Feature                  | Datatype | Description                                                                              |
|--------------------------|----------|------------------------------------------------------------------------------------------|
| gr_liv_area              | int64    | Above grade (ground) living area square feet                                             |
| total_bsmt_sf            | int64    | Total square feet of basement area                                                       |
| garage_area              | int64    | Size of garage in square feet                                                            |
| mas_vnr_area             | float64  | Masonry veneer area in square feet                                                       |
| overall_qual             | int64    | Rating for overall material and finish of the house                                      |
| fireplace_qu             | int64    | Fireplace quality                                                                        |
| age                      | int64    | Age of property since original construction date                                         |
| since_reno               | int64    | Number of years since last remodeled                                                     |
| tot_baths                | float64  | Total number of bathrooms including basement bathrooms                                   |
| ms_new                   | int64    | Binary feature, 1 indicating houses built in newer styles                                |
| neighbor_h               | int64    | Binary feature, 1 indicating that the property is located in an upper class neighborhood |
| neighbor_l               | int64    | Binary feature, 1 indicating that the property is located in a lower class neighborhood  |
| garage_type_a            | int64    | Binary feature, 1 indicating that the garage is attached or built in to the house.       |
| gr_liv_area overall_qual | int64    | Polynomial feature                                                                       |
| garage_area overall_qual | int64    | Polynomial feature                                                                       |
| saleprice                | int64    | Sale price of property in $                                                              |
