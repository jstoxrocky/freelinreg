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

2.1 Cross-sectional and Time-series data:

The FOMLRP accepts model specifications in the same way that EViews does. The dependent variable must always be first
in the model specificantions. The variable 'c' is always used as the constant term, and the variable 't' is always 
used as the time trend. The position of 'c' and 't' do not matter, as long as they do not appear first. Logarithms, exponents, and lags are supported.

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
        
        y c gdp*cap

2.2 Panel and Pooled Cross-sectional data:

The FOMLRP supports estimation of panel and pooled cross-sectional in the following way. Estimation of models spanning accross time periods and cross sections can cause problems for time trends and lagged variables. For this reason, extra caution must be used when mixing these variable with this type of data. To let the FOMLRP know that you are using data spanning both time and cross sections, the number of time periods associated with cross sections must be specified in square brackets at the end of the model specification.

    y x1 x2 x3 ... [time_periods]

For example, using the above data set, assume we have data spanning 4 countries and 10 time periods for each country, and that we wish to estimate the following model:

    y c gdp cap t

To let the FOMLRP know that we would like the time trend 't' to range from 1-10 for each country (and not 1-40 accross all countries) we specify the model as follows:

    y c gdp cap t [10]
    
Similarly, when using lagged variables with Panel or Pooled Cross Sectional data, you must also specify the number of time periods:

    log(y) c gdp cap log(y)(-1) [10]
    
It is not necessary to specify the number of time periods when using pure time series data.

2.3 Interaction terms

Interaction terms are possible with the FOMLRP. Simply insert an asterix between two variable names to create a new interaction variable.

    y x1 x1*x2
    
For example, If our data set is as above, we can create an interaction term equal to the product of 'gdp' and 'cap' and use it in our model specifications:

    y c gdp*cap

**********************************************************************************************************************
STEP 3: Further estimation and hypothesis testing
**********************************************************************************************************************

3.1 Wald Test:

The FOMLRP allows for simple hypothesis testing via the Wald Test. Testing can be performed by entering the restrictions
in the appropriate model's Wald Test text area, separating individual restrictions with commas.

        x1 = <some value>, x2 = <some value>, x3 = <some value>, ...

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
For example residuals from the first model estimated, eq_1, are subsequently accessed using the variable "res_eq_1". 
Similalrly, residuals from the second estimated equation are accessed by calling "res_eq_2".

3.4 Hausman Test:

A Hausman Test can be performed using the residuals from a previously estimated equation. 

        res_eq_<equation number>^2 x1 x2 x3...

For example, if your first model is estimated as:

        y c gdp cap
        
Post estimation, the residuals are available and a Hausman test can be performed by estimating:

        res_eq_1^2 c gdp cap


**********************************************************************************************************************
STEP 4: Donation
**********************************************************************************************************************

If you like this product, please donate! I am unemployed!
