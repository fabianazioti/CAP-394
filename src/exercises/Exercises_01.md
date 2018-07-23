Exercices
================

### Basic R Exercises

#### Understanding and Fixing Code

-   Fix the part of the code that shows the cold months in Baltimore so we know which are those months.

``` r
months <- c("Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec")
tempLo <- c(23.5,26.1,33.6,42.0,51.8,60.8,65.8,63.9,56.6,43.7,34.7,27.3)
tooCold <- (((5/9) * (tempLo - 32)) < 0)
tooCold
```

    ##  [1]  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ## [12]  TRUE

Show the months:

``` r
names(tooCold) <- months
tooCold
```

    ##   Jan   Feb   Mar   Apr   May   Jun   Jul   Aug   Sep   Oct   Nov   Dec 
    ##  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE

-   What would happen if we still had a NA on the vector for the temperatures in SJC?

Problems with some operators.

-   What happens if we try to run sjcTemps\["Jan":"Jul",c(1,3)\]? Why?

``` r
maxTempSJC <- c(29.7,30.1,29.5,27.3,25.1,24.3,24.1,26.2,27.2,27.3,28,28.7)
avgTempSJC <- c(22.2,22.4,21.6,19.6,17,16.1,15.6,17.1,18.8,19.4,20.3,21.4)
minTempSJC <- c(16.2,16.5,15.7,13.2,10.1,8.9,8.2,9.9,11.9,13.4,14.2,15.3)
months <- c("Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec")
sjcTemps <- data.frame(Max=maxTempSJC,Avg=avgTempSJC,Min=minTempSJC,row.names = months)
sjcTemps
```

    ##      Max  Avg  Min
    ## Jan 29.7 22.2 16.2
    ## Feb 30.1 22.4 16.5
    ## Mar 29.5 21.6 15.7
    ## Apr 27.3 19.6 13.2
    ## May 25.1 17.0 10.1
    ## Jun 24.3 16.1  8.9
    ## Jul 24.1 15.6  8.2
    ## Aug 26.2 17.1  9.9
    ## Sep 27.2 18.8 11.9
    ## Oct 27.3 19.4 13.4
    ## Nov 28.0 20.3 14.2
    ## Dec 28.7 21.4 15.3

An error occurred: *Error in "Jan":"Jul" : Argumento NA/NaN*

-   We can change Data Frames with sjcTemps3\["Aug",\] &lt;- c(1,2,3) and sjcTemps3\["Jul",\] &lt;- sjcTemps3\["Jul",\]+c(3,4) but we cannot change with sjcTemps3\["Jul",\] &lt;- c(3,4). Why?

Replacement has 2 items, need 3

-   Run some examples that show that the recycling rule reuses the smaller (shorter) vector

-   What does stringsAsFactors=FALSE in read.csv() do? Why do we need it?

To avoid problems delay re-encoding of strings by using stringsAsFactors = FALSE when creating data.frames

#### Baltimore Rainfall

The average monthly rainfall in Baltimore is, in inches: 3.47, 3.02, 3.93, 3.00, 3.89, 3.43, 3.85, 3.74, 3.98, 3.16, 3.12, 3.35

Write an R program that shows this in millimeters (one inch = 25.4 mm), add names to the vector, and calculates its average, minimum and maximum

``` r
avgBaltimore <- c(3.47, 3.02, 3.93, 3.00,   3.89,   3.43,   3.85,   3.74,   3.98,   3.16,   3.12,   3.35)
```

``` r
avgBaltimore <- avgBaltimore * 24.5
avgBaltimore
```

    ##  [1] 85.015 73.990 96.285 73.500 95.305 84.035 94.325 91.630 97.510 77.420
    ## [11] 76.440 82.075

``` r
months <- c("Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec")
names(avgBaltimore) <- months
avgBaltimore
```

    ##    Jan    Feb    Mar    Apr    May    Jun    Jul    Aug    Sep    Oct 
    ## 85.015 73.990 96.285 73.500 95.305 84.035 94.325 91.630 97.510 77.420 
    ##    Nov    Dec 
    ## 76.440 82.075

#### Tidy Data: The “hotdog” variable for the “Hot Dogs in Baltimore” example can be better defined.

#### Tidy Data: I prefer Pizza

#### Tidy Data: Get the name of the town for the “Hot Dogs in Baltimore” example

#### Tidy Data: Complete the Codebook for the “Hot Dogs in Baltimore” example
