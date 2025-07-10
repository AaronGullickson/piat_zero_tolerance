# Data Source Description

The data we will use include most Oregon school districts in 2013. We use 2013 rather than a more recent year, because the Oregon legislature eliminated most zero tolerance policies in 2015. The data we use come from two different sources. For data on school expulsion rates, I gathered data from the [Civil Rights Data Collection](https://ocrdata.ed.gov/) (CRDC), which collects a variety of administrative data, including data on expulsions based on zero tolerance policies, across all school districts in the US. It is organized by the Office for Civil Rights in the US Department of Education. The remaining data comes from [American Community Survey](https://www.census.gov/programs-surveys/acs) (ACS). The ACS is an annual survey of the US population conducted by the US Census Bureau. Here we use data from 2011-2015 that is aggregated to the level of school districts. Data were extracted from the [Social Explorer](https://www.socialexplorer.com) website. Note that the ACS data is for all residents in the school district, not just the students enrolled in school.

From the full data, I have extracted and recoded the following variables for our use as an analytical dataset. To load this dataset in R, you just need to run the setup code chunk in the full_report.Rmd R Markdown document. The name of the dataset in R is `districts`. 

* **district_id**: The id for the school district.
* **district_name**: The name of the school district.
* **pct_dropout**: The percent of individuals aged 16-19 who were not either enrolled in school or graduated. This is an indirect measure of the dropout rate for the school district (i.e. not based on school administrative records). This is the key dependent variable.
* **rate_expulsion**: The number of school expulsions per 1000 students for any reason. Note that because this rate is for any reason, it is **not** the key independent variable. However, it can serve as a useful control to make sure our key independent variable is not just picking up school districts where behavior is more of a problem. 
* **rate_expulsion_zero_tolerance**: The number of school expulsions per 1000 students based on zero tolerance policies only. This is the key independent variable.
* **pct_nonwhite**: The percent of residents in the school district who are non-white.
* **pct_college**: The percent of residents in the school district over age 25 who have a four-year college degree or more.
* **pct_unemployed**: The percent of the labor force population in the school district that is unemployed.
* **pct_child_poverty**: The percent of children under 18 in the school district that reside in a household with an income below the poverty line.
* **median_family_inc**: The median family income in the school district in 2015 dollars.
* **gini**: A measure of income inequality among residents in the school district. A score of zero would indicate no income inequality (eg. everyone makes the same income) and a score of 100 would indicate maximum income inequality (eg. one person made all the income and everyone else made none). 
* **urban**: A categorical measure of the urbanicity of the school. This is based on population density (number of people per square mile). A population density of greater than 1000 people per square mile is considered urban. 
