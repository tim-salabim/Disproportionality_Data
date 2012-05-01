# Gallagher Electoral Disproportionality Data
## 121 Countries, 1945-2011

Christopher Gandrud </br>
Data Updated 24 March 2012
README Updated 1 May 2012

## What is it?

This is a <strong>.csv</strong> formatted data set of the Least Squares Index of electoral disproportionality for 121 countries between 1945 and 2011. The Least Squares Index is also commonly referred to as the Gallagher Index. The data set combines Michael Gallagher's recently updated data (<a href = http://www.tcd.ie/Political_Science/staff/michael_gallagher/ElSystems/Docts/ElectionIndices.pdf>here</a>) with some holes (see below) filled in with data made available by John Carey and Simon Hix (<a href = http://www.dartmouth.edu/~jcarey/Data_Archive.html>here</a>).

## Why did I make this?

There is currently no complete and recently updated Gallagher Index data freely available in a format that is easy to do statistical analysis on. The data on Michael Gallagher's <a href = http://www.tcd.ie/Political_Science/staff/michael_gallagher/ElSystems/Docts/ElectionIndices.pdf>website</a> has been recently updated (the one I used was from 21 February 2012). However it is only available in PDF format; not exactly the easiest format to merge into an R or Stata file. 

So, after going through the somewhat painstaking work of entering all of this data into a .csv file (and filling in some holes with Carey and Hix's data) I decided to make my efforts publicly available. Hopefully, this will free up some research time for more productive endeavours than copying and pasting data from a PDF file.

## Import into R

To import the file directly into **R** simply use the following set of commands:

```r
library(RCurl)
library(foreign)

url <- "https://raw.github.com/christophergandrud/Disproportionality_Data/master/Disproportionality.csv"

disproportionality.data <- getURL(url)                
                            
disproportionality.data <- read.csv(textConnection(disproportionality.data))
```

## More details on the Gallagher Index

The Least Squares or Gallagher Index of electoral disproportionality basically uses the standard least squares method for comparing the relationship between two samples. It compares parties' votes to the legislative seats they are given. Higher numbers on the Gallagher Index indicate that there is a greater disparity between votes and seats, i.e. elections have produced more disproportional outcomes. A Gallagher score of 0 would indicated that the election produced perfectly proportional outcomes.

For more information see: 

Gallagher, Michael. 1991. “Proportionality, Disproportionality, and Electoral Systems.” Electoral Studies 10(1): 33–41.

or

Carey, John M, and Simon Hix. 2011. “The Electoral Sweet Spot: Low-Magnitude Proportional Electoral Systems.” American Journal of Political Science 55(2): 383–397.

## More details on the data.

These notes give specific details about how I combined the two data sets into the one .csv file.

Data is for national overall disproportionality. 

I did not include Northern Ireland, Scotland, Wales, Turkish Cyprus, or Palestine.

### All data is from Gallagher's PDF mentioned with the following exceptions. </br>
Data for these countries was taken from Hix and Carey (see their notes for further details):

Benin </br>
Dominican Republic </br>
Ecuador </br>
Guatemala before 2011 </br>
India before 2004 </br>
Indonesia for 1999 </br>
Macedonia 2004 </br>
Mauritius before 2010 </br>
Mongolia </br>
Nepal </br>
Papua New Guinea </br>
Philippines </br>
South Korea before 2004 </br>
Sri Lanka before 2000 </br> 
Taiwan 1998 </br>
Thailand before 2011 </br>
Turkey before 2003 </br>
Ukraine before 2003 </br>
Venezuela before 2001 </br>

### For years when there were two elections in one country I kept the latter one. This included:
Fiji uses September election for 1977 (previous election was in September) </br>
France uses November election for 1946 (previous election was in June) </br>
Greece uses November election for 1989 (previous election was in June) </br>
Iceland uses October election for 1959 (previous election was in June) </br>
Ireland uses November Election for 1983 (previous election was in February) </br>
Moldova uses July elections for 2009 (previous election was in April) </br>
St Lucia uses April 30 for 1987 (previous election was in April 6) </br>
United Kingdom uses October Election for 1974 (previous election was in February) 

<br>
The United States data is for House elections. I did not included data on executive disproportionality, though Gallagher includes this in his PDF file.
</br>

### See Gallagher and Carey & Hix for further notes.













