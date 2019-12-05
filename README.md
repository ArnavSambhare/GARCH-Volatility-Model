# GARCH-Volatility-Model
This contains the code for GARCH(1,1) model coefficients.

The GARCH model (Generalized AutoRegressive Conditional Heteroskedasticity) is used to model the volatilities of stocks.

Its general equation is:
<a href="https://www.codecogs.com/eqnedit.php?latex=(\sigma_{t})^{2}&space;=&space;\omega&space;&plus;&space;\alpha*r_{t}^{2}&space;&plus;&space;\beta*(\sigma_{t-1})^{2}" target="_blank"><img src="https://latex.codecogs.com/png.latex?(\sigma_{t})^{2}&space;=&space;\omega&space;&plus;&space;\alpha*r_{t}^{2}&space;&plus;&space;\beta*(\sigma_{t-1})^{2}" title="(\sigma_{t})^{2} = \omega + \alpha*r_{t}^{2} + \beta*(\sigma_{t-1})^{2}" /></a>


We need to estimate the values of <a href="https://www.codecogs.com/eqnedit.php?latex=\omega" target="_blank"><img src="https://latex.codecogs.com/png.latex?\omega" title="\omega" /></a> , <a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/png.latex?\alpha" title="\alpha" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/png.latex?\beta" title="\beta" /></a>.

This is done by using the SLSQP optimizer in the scipy library to minimize the loss function.
<a href="https://www.codecogs.com/eqnedit.php?latex=Loss&space;Function&space;=&space;\sum&space;(log(\sigma^{2})&space;&plus;&space;(r^{2}/\sigma^{2}))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Loss&space;Function&space;=&space;\sum&space;(log(\sigma^{2})&space;&plus;&space;(r^{2}/\sigma^{2}))" title="Loss Function = \sum (log(\sigma^{2}) + (r^{2}/\sigma^{2}))" /></a>


The constraints in this problem are:
1. <a href="https://www.codecogs.com/eqnedit.php?latex=\omega&space;&plus;&space;\alpha&space;&plus;&space;\beta&space;=&space;1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\omega&space;&plus;&space;\alpha&space;&plus;&space;\beta&space;=&space;1" title="\omega + \alpha + \beta = 1" /></a> 
2. <a href="https://www.codecogs.com/eqnedit.php?latex=\alpha&space;&plus;&space;\beta&space;<&space;1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha&space;&plus;&space;\beta&space;<&space;1" title="\alpha + \beta < 1" /></a>
