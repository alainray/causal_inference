## Solutions to Chapter 3 of "Elements of Causal Inference" by Jonas Peters, Dominik Janzing and Bernhard Schölkopf

### 3.6

We know that:

![E = 4C + N_Y](https://render.githubusercontent.com/render/math?math=E%20%3D%204C%20%2B%20N_Y) and the right hand side distributes like ~ N(0, 17)

We want to understand the distributions of 4C and N_Y when their sum is 2.

The distributions of the distributions that form a conditional distribution of a Gaussian follow this result: 
https://stats.stackexchange.com/questions/9071/intuitive-explanation-of-contribution-to-sum-of-two-normally-distributed-random

![4C ~ N(2*\frac{16}{17}, \frac{16}{17})](https://render.githubusercontent.com/render/math?math=4C%20~%20N(2*%5Cfrac%7B16%7D%7B17%7D%2C%20%5Cfrac%7B16%7D%7B17%7D))
![N_Y ~ N(2*\frac{1}{17}, \frac{1}{17})](https://render.githubusercontent.com/render/math?math=N_Y%20~%20N(2*%5Cfrac%7B1%7D%7B17%7D%2C%20%5Cfrac%7B1%7D%7B17%7D))

Thus:

![C ~ N(\frac{2*16}{(4*17)}, \frac{16}{(16*17)}) \xrightarrow{} N(\frac{8}{17}, \frac{1}{17})](https://render.githubusercontent.com/render/math?math=C%20~%20N(%5Cfrac%7B2*16%7D%7B(4*17)%7D%2C%20%5Cfrac%7B16%7D%7B(16*17)%7D)%20%5Cxrightarrow%7B%7D%20N(%5Cfrac%7B8%7D%7B17%7D%2C%20%5Cfrac%7B1%7D%7B17%7D))


### 3.7

Given that there's only two possible solutions: 

* ![X \xrightarrow{} Y](https://render.githubusercontent.com/render/math?math=X%20%5Cxrightarrow%7B%7D%20Y)
* ![Y \xrightarrow{} X](https://render.githubusercontent.com/render/math?math=Y%20%5Cxrightarrow%7B%7D%20X)

We can do an independence test between X and Y over the intervention X:= N(0,1) 

If we find correlation between X and Y then the model X --> Y is appropriate. If not, it's the other.

The only problem is since we do not know the means and variances of the models we are trying to intervene, we could be unlucky and choose exactly the values that correspond to the observational distribution. Thus, we would need to do at least three interventions over the same variable to make sure we didn't randomly choose the correct distribution.


### 3.8

a) This is just solving a linear system:

![\alpha N_X + \beta N_y = 2\gamma N_X + 2\delta N_Y + N_X](https://render.githubusercontent.com/render/math?math=%5Calpha%20N_X%20%2B%20%5Cbeta%20N_y%20%3D%202%5Cgamma%20N_X%20%2B%202%5Cdelta%20N_Y%20%2B%20N_X)

![\gamma N_X + \delta N_Y = 2\alpha N_X + 2 \beta + N_Y + N_Y](https://render.githubusercontent.com/render/math?math=%5Cgamma%20N_X%20%2B%20%5Cdelta%20N_Y%20%3D%202%5Calpha%20N_X%20%2B%202%20%5Cbeta%20%2B%20N_Y%20%2B%20N_Y)


There are four variables for two equations, so it seems we are in trouble. However, it's easy to come up with four equations for this, since parameters for N_Y and N_Y must match for both equations. Thus:

![\alpha = 2\gamma + 1](https://render.githubusercontent.com/render/math?math=%5Calpha%20%3D%202%5Cgamma%20%2B%201)
![\beta = 2\delta](https://render.githubusercontent.com/render/math?math=%5Cbeta%20%3D%202%5Cdelta)
![\gamma = 2\alpha](https://render.githubusercontent.com/render/math?math=%5Cgamma%20%3D%202%5Calpha)
![\delta = 2\beta + 1](https://render.githubusercontent.com/render/math?math=%5Cdelta%20%3D%202%5Cbeta%20%2B%201)

Solving the equations we get that:

![\alpha = \frac{-1}{3} , \beta = \frac{-2}{3} , \gamma = \frac{-2}{3} , \delta = \frac{-1}{3}](https://render.githubusercontent.com/render/math?math=%5Calpha%20%3D%20%5Cfrac%7B-1%7D%7B3%7D%20%2C%20%5Cbeta%20%3D%20%5Cfrac%7B-2%7D%7B3%7D%20%2C%20%5Cgamma%20%3D%20%5Cfrac%7B-2%7D%7B3%7D%20%2C%20%5Cdelta%20%3D%20%5Cfrac%7B-1%7D%7B3%7D)


Thus our final model is:

![X:= \frac{2}{3}N_X -\frac{2}{3}N_Y ](https://render.githubusercontent.com/render/math?math=X%3A%3D%20%5Cfrac%7B2%7D%7B3%7DN_X%20-%5Cfrac%7B2%7D%7B3%7DN_Y%20)

![Y:= \frac{-2}{3}N_X + \frac{2}{3}N_Y](https://render.githubusercontent.com/render/math?math=Y%3A%3D%20%5Cfrac%7B-2%7D%7B3%7DN_X%20%2B%20%5Cfrac%7B2%7D%7B3%7DN_Y)

b)

Trying to solve the equation if we replace X and Y we get:

X = X + N_Y + N_X
Y = Y + N_X + N_Y

Any of these equations leads to:

N_Y = -N_X 

Which is impossible if N_X and N_Y are independent.

To come up with candidate X, Y, N_X, N_Y:

Assuming N_X = -N_Y, we can solve:

X = alpha*N_X
Y = beta*N_X

alpha * N_X = beta * N_X + N_X
beta * N_X = alpha * N_X - N_X

alpha = beta + 1
beta = alpha - 1

Both equations give the same information:

alpha = beta + 1 

Thus we can choose alpha = 2, beta= 3 and it will be a valid vector:

Thus:

N_X := N(0,1)
N_Y := -N_X
X:= 2* N_X
Y:= 3* N_X

Is a valid solution.







