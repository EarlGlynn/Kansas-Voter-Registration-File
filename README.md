# Technical Analysis of Kansas Voter Registration File

** under development **

# 1. First Look

An RStudio computational notebook shows results of analyzing a voter registration file from Kansas Secretary of State:

File:  `Kansas-First-Look-Edited.html` (results of processing)

Shows

* Problems with raw data file

* Problems with certain district assignments in Osage, Scott and Wilson counties.

* Creation of additonal fields for use in analysis

* Stats by state / county / precinct

* Metastats for data fields

* Household estimates, including summaries with many voters at some household addresses

* Election code stats

## Metadata

File:  `Kansas-Field-Length-Summary-yyyy-mm-dd-Edited.xlsx`

Descriptive stats about each data field (treated as character strings), including:

* field width quantiles

* number of missing values

* number of unique values

* number of counties using the field

The `cde_name_title` field is missing for over 2 million voters but is defined for some in 70 counties.

The `text_res_carrier_rte` is missing for over 2 million voters but is defined for some in 30 counties.

School district `district_sd` is not defined for 332 voters.


## Descriptive summary stats by region

**Files**

* State:  `Kansas-Counts-State-yyyy-mm-dd.xlsx`

* County:  `Kansas-Counts-County-yyyy-mm-dd.xlsx`

* Precinct: `Kansas-Counts-Precinct-yyyy-mm-dd.xlsx`

Stats include

* region name (county or precinct files)

* total voters

* age quantiles

* district numbers (county or precinct files), number of districts (state file)

* city, zip and precinct counts

* counts of email addresses, phone numbers

* estimates of number of households

* counts and percentages by gender

* counts and percentages by political party

* counts and percentages by active/inactive status


## Age issues

* $$\lt$$ 18 years old:  `Kansas-Age-Too-Young-yyyy-mm-dd-Edited.xlsx`

* $$\ge$$ 105 years old:  `Kansas-Age-Too-Old-yyyy-mm-dd-Edited.xlsx`

* `Kansas-Crosstab-BirthYear-by-BirthMonth-yyyy-mm-dd.xlsx`

Birth years before ~1915 are suspect (e.g., 1054 should be 1954).

* `Kansas-Crosstab-RegisterYear-by-RegisterMonth-yyyy-mm-dd.xlsx`

Registration years before 1960 are suspect. One registration in the future is an error.

## Household issues

A "household" is a common address shared by a group of voters, often families but sometimes dormitories.

Lists below show households with the top 0.1% number of voters (descending sort).

### Street Addresses

* `Kansas-Households-Address-to-Explore-for-Many-Voters-yyyy-mm-dd.xlsx`

Top 10

![alt text](2025-05-02/1-First-Look/Top-10-Household-Street-Addresses.PNG "Top 10 Kansas Voter Street Households")

"1501 N Ford St" is the address of the Hutchinson Community College, where at least 385 students no longer reside.

### Mailing Addresses

* `Kansas-Households-Mail-to-Explore-for-Many-Voters-yyyy-mm-dd.xlsx`

Top 10

![alt text](2025-05-02/1-First-Look/Top-10-Household-Mailing-Addresses.PNG "Top 10 Kansas Voter Mailing Households")

"PO Box 340" in Liberal is the Seward County Community College.


## Election Codes

Voter history is recorded with a code

Counts of numbers of voters and counties using election codes (sorted in descending order):

File:  `Kansas-Election-Code-Summary-yyyy-mm-dd.xlsx`

Top 10

![alt text](2025-05-02/1-First-Look/Top-10-Election-Codes.PNG "Kansas voter history election codes")

Note: the 11th most common code shows one county still has not reported voter history for the 2024 primary election!


## `Counts` folder

Each data field has a file with frequency counts of values.

Some files with PHI have been withheld. Some very large files are not included.

Note:

* `004-text_name_first.csv` shows 8 people without first names.
* `020-cde_res_state.csv` shows 17 Kansas voters have a zip code split with Nebraska

# 2. Age-Gender-Party breakdown

Parametric RStudio report files to create graphics for each geography (GEONAME).

* `Age-Gender-Party-Driver.html` (results of processing)

* `Age-Gender-Party-Driver.Rmd`

* `Age-Gender-Party-Template.Rmd`

## Kansas statewide

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-PercentRegisteredAgeInterval-1.png "Percent Registered of Voting Age - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-Voters-by-Age-Gender-Census-1.png "Registered Voters by Age Interval and Gender - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-Voters-by-Age-Gender-Party-Democratic-1.png "Registered Democratic Party Voters by Age Interval and Gender - Kansas statewide")

## Johnson County

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-PercentRegisteredAgeInterval-1.png "Percent Registered of Voting Age - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-Voters-by-Age-Gender-Census-1.png "Registered Voters by Age Interval and Gender - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-Voters-by-Age-Gender-Party-Democratic-1.png "Registered Democratic Party Voters by Age Interval and Gender - Kansas statewide")

Currently charts are only available for Kansas statewide and four counties (Douglas, Johnson, Sedgwick, Shawnee).

Eventually all 105 counties will have separate directories.

# Active-Inactive Voters

`Map-Kansas-Inactive-Voters.html` (results of processing)

List of 105 counties with total voters and active and inactive counts:

`Kansas-Active-Inactive-Voters.xlsx`

County Map

![alt text](2025-05-02/3-Active-Inactive/Kansas-State-1.png "Kansas: Percent 'Inactive' Voters by County")

Recent article: [Kansas had over 140,000 inactive voters in Jan. 2024 but only 113,000 in Jan. 2025. Inactive rates in some counties are still fairly high.](https://watchdoglab.substack.com/p/kansas-has-27000-fewer-inactive-voters)

<hr>

Notes:

* "Edited" in a filename indicates some personal identifiable information (PHI) has been removed.

* Most filenames end with time stamp (yyyy-mm-dd) of voter file release (which enables comparisons of multiple versions in Excel).
