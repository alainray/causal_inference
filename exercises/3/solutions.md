## Solutions to Chapter 3 of "Elements of Causal Inference" by Jonas Peters, Dominik Janzing and Bernhard Schölkopf

### 3.6

We know that:

E = 4C + $N_Y$ and the right hand side distributes like ~ N(0, 17)

We want to understand the distributions of 4C and N_Y when their sum is 2.

The distributions of the distributions that form a conditional distribution of a Gaussian follow this result: 
https://stats.stackexchange.com/questions/9071/intuitive-explanation-of-contribution-to-sum-of-two-normally-distributed-random

4C ~ N(2*16/17, 16/17) 
N_Y ~ N(2*1/17, 1/17)

Thus C ~ N(2*16/(4*17), 16/(16*17)) --> N(8/17, 1/17)

### 3.7

Given that there's only two possible solutions: 

* X --> Y
* Y --> X

We can do an independence test between X and Y over the intervention X:= N(0,1) 

If we find correlation between X and Y then the model X --> Y is appropriate. If not, it's the other.

The only problem is since we do not know the means and variances of the models we are trying to intervene, we could be unlucky and choose exactly the values that correspond to the observational distribution. Thus, we would need to do at least three interventions over the same variable to make sure we didn't randomly choose the correct distribution.


### 3.8

a) This is just solving a linear system:

alpha * N_X + beta * N_y = 2 * gamma * N_X + 2 * delta * N_Y + N_X
gamma * N_X + delta * N_Y = 2 * alpha * N_X + 2 * beta + N_Y + N_Y

There are four variables for two equations, so it seems we are in trouble. However, it's easy to come up with four equations for this, since parameters for N_Y and N_Y must match for both equations. Thus:

alpha = 2 * gamma + 1
beta = 2 * delta
gamma = 2 * alpha
delta = 2 * beta + 1

Solving the equations we get that:

alpha = -1/3 , beta = -2/3 , gamma = -2/3 , delta = -1/3 

Thus our final model is:

X:= 2/3 * N_X -2/3 * N_Y 
Y:= -2/3 * N_X + 2/3 * N_Y


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







