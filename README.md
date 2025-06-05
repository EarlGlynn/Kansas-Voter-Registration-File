# Technical Analysis of Kansas Voter Registration File

** under development **

# 1. First Look

RStudio computational notebook with analysis of voter registration file from Kansas Secretary of State:

**Kansas-First-Look-Edited.html** (results of processing)

Shows

* Problems with raw data file

* Problems fixed with certain district assignments in certain counties or districts

* Creation of additonal fields for use in analysis

* Stats by state / county / precinct

* Metastats for data fields

* Household estimates, including summaries with many voters at some household addresses

* Election code stats

## Metadata

Descriptive stats about each data field (treated as character strings), including:

* field width quantiles

* number of missign values

* number of unique values

* number of counties using the filed

**Kansas-Field-Length-Summary-yyyy-mm-dd-Edited.xlsx**


## Descriptive summary stats by region

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

**Summary files:**

* State:  Kansas-Counts-State-yyyy-mm-dd.xlsx

* County:  Kansas-Counts-County-yyyy-mm-dd.xlsx

* Precinct: Kansas-Counts-Precinct-yyyy-mm-dd.xlsx

## Age issues

* < 18 years old:  Kansas-Age-Too-Young-yyyy-mm-dd-Edited.xlsx

* > 105 years old:  Kansas-Age-Too-Old-yyyy-mm-dd-Edited.xlsx

* Kansas-Crosstab-BirthYear-by-BirthMonth-yyyy-mm-dd.xlsx

* Kansas-Crosstab-RegisterYear-by-RegisterMonth-yyyy-mm-dd.xlsx

## Household issues

Top 0.1% number of voters at household (sorted in descending order):

* Kansas-Households-Address-to-Explore-for-Many-Voters-yyyy-mm-dd.xlsx

* Kansas-Households-Mail-to-Explore-for-Many-Voters-yyyy-mm-dd.xlsx


## Election Codes

Counts of numbers of voters and counties using election codes (sorted in descending order):

Kansas-Election-Code-Summary-yyyy-mm-dd.xlsx


## `Counts` folder

File by data field with frequency counts of values.

Some files with PHI have been withheld. Some very large files are not included.


# 2. Age-Gender-Party breakdown

Parametric RStudio report files to create graphics for each geography (GEONAME).

* Age-Gender-Party-Driver.html (results of processing)

* Age-Gender-Party-Driver.Rmd

* Age-Gender-Party-Template.Rmd

## Kansas statewide

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-PercentRegisteredAgeInterval-1.png "Percent Registered of Voting Age - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-Voters-by-Age-Gender-Census-1.png "Registered Voters by Age Interval and Gender - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Kansas/Plot-Voters-by-Age-Gender-Party-Democratic-1.png "Registered Democratic Party Voters by Age Interval and Gender - Kansas statewide")

## Johnson County

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-PercentRegisteredAgeInterval-1.png "Percent Registered of Voting Age - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-Voters-by-Age-Gender-Census-1.png "Registered Voters by Age Interval and Gender - Kansas statewide")

![alt text](2025-05-02/2-Age-Gender-Party/GEONAME/Johnson/Plot-Voters-by-Age-Gender-Party-Democratic-1.png "Registered Democratic Party Voters by Age Interval and Gender - Kansas statewide")

See files for certain other counties.

# Active-Inactive Voters

Map-Kansas-Inactive-Voters.html (results of processing)

![alt text](2025-05-02/3-Active-Inactive/Kansas-State-1.png "Kansas: Percent 'Inactive' Voters by County")


Notes:

* "Edited" in a filename indicates some personal identifiable information (PHI) has been removed.

* Most filenames end with time stamp (yyyy-mm-dd) of voter file release (which enables comparisons of multiple versions in Excel).
