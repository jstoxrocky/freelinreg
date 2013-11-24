LinReg
======

Free Online Multiple Linear Regression Package (FOMLRP)
Created by Joseph Stockermans 2013

Help:

**********************************************************************************************************************
STEP 1: Uploading your data
**********************************************************************************************************************

The FOMLRP only accepts data in .xls, .xlsx, or .csv files. 

**********************************************************************************************************************
STEP 2: Estimating your model
**********************************************************************************************************************

The FOMLRP accepts model specifications in the same way that EViews does. The dependent variable must always be first
in the model specificantions. The variable 'c' is always used as the constant term, and the variable 't' is always 
used as the time trend (the time trend currently does not support panel data). The position of 'c' and 't' do not matter,
as long as they do not appear first. Logarithms, exponents, and lags are currently supported (lags of variables do not 
support panel data).

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

        log(y) c log(y)(-1) log(gdp) t cap cap^2

        y c cap^7

**********************************************************************************************************************
STEP 3: Further estimation and hypothesis testing
**********************************************************************************************************************

3.1 Wald Test:

The FOMLRP allows for simple hypothesis testing via the Wald Test. Testing can be performed by entering the restrictions
in the appropriate model's Wald Test text area, separating individual restrictions with commas.

        var_1 = value_1, var_2 = value_2, ...

For example, assume the following model is estimated:

        log(y) c log(y)(-1) gdp^2 cap
        
The following Wald Tests are all admissible:

        log(y)(-1)=0, gdp^2=0, cap=0

        gdp^2=0

        c=0, gdp^2=0, cap=0
        
3.2 Plots:

The actual series and fitted model series can be plotted. Simply click on the 'Plot Actual, Fitted Series' button on 
the appropriate model window and you're done! Alternatively, the residual series can be plotted by clicking on the
'Plot Residual' button on the appropriate model window.

3.3 Obtaining Residuals Series:

Obtaining residuals is easy. Residuals from each model are stored and can be accessed during subsequent model estimation. 
For example residuals from the first model estimated (eq_1) are subsequently accessed using the variable "res_eq_1". 
Similalrly, residulas from the second estimated equation are accessed by calling "res_eq_2".

3.4 Hausman Test:

A Hausman Test can be performed using the residuals from a previously estimated equation. 

        res_eq_<equation number>^2 c gdp cap

If you model is estimated as:

        y c gdp cap
        
Post estimation, the residuals are available and a Hausman test can be performed by estimating:

        res_eq_<num>^2 c gdp cap


**********************************************************************************************************************
STEP 4: Donation
**********************************************************************************************************************

If you like this product, don't forget to donate!!
