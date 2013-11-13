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

3.1 Wald Test

The FOMLRP allows for simple hypothesis testing via the Wald Test. Testing can be performed by entering the restrictions
in the appropriate model's Wald Test text area, separating individual restrictions with commas.

        var_1 = value_1, var_2 = value_2, ...

For example, assume the following model is estimated:

        y c gdp cap
        
The followign Wald Tests are all admissible:

        gdp=0, cap=0

        gdp=0

        c=0, gdp=0, cap=0

        c=0
        
3.2 Plot

The actual series and fitted model series can be plotted. Simply click on the Plot button in the appropriate model window
and you're done!

3.3 Residuals:

Obtaining residuals is easy. Residuals from each model are stored and can be accessed in model estimation. 
For example residuals from the first eq_1 are accessed by the variable "res_eq_1", and from the second estimated equation
by calling "res_eq_2".

Likewise, a Hausman test can be performed as follows:

Say eq_1 is estimated as:

        y c gdp cap
        
After estimation, the residuals are available and a Hausman test can be performed by estimating:

        res_eq_1^2 c gdp cap

