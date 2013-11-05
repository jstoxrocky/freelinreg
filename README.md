LinReg
======

Free Online Multiple Linear Regression Package (FOMLRP)

Help:

**********************************************************************************************************************
STEP 1: Uploading your data
**********************************************************************************************************************

The FOMLRP can currently only accept data in the form of csv files. 
To convert excel (xls) files to csv, see this video: https://www.youtube.com/watch?v=SalyolC6jKM

**********************************************************************************************************************
STEP 2: Estimating your model
**********************************************************************************************************************

The FOMLRP accepts model specifications in the same way that EViews does. The variable 'c' is always used as the
constant term. Logarithms of data and exponents are currently supported. Lags are not currently supported.

For example, if your data looks like this:

        y  gdp  cap
    1   1    2    5
    2   2    3    9
    3   8    7    2
    4   3    4    7
    ...
    
any of the following specifications are admissible:

        y c gdp cap

        y gdp c cap

        y c log(gdp) cap cap^2

        y c cap^7

**********************************************************************************************************************
STEP 2: Further estimation and hypothesis testing
**********************************************************************************************************************
