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
STEP 3: Further estimation and hypothesis testing
**********************************************************************************************************************


Wald Test

Plot

Residuals:

Obtaining residuals is easy. Residuals from each model are stored and can be accessed in model estimation 
by calling "res_eq_<model number>". For example residuals from the first eq_1 are accessed by the variable "res_eq_1".

Likewise, a Hausman test can be performed as follows:

Say eq_1 is:

        y c gdp cap
        
After this model is estimated, a Hausman test can be performed as:

        res_eq_1^2 c gdp cap

