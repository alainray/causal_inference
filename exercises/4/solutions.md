## Solutions to chapter 4

### 4.16

a) There is a typo on what the proof is, the correct proof is:

Prove that:

![f(x) = E\[Y | X = x \] - \mu_{Y}](https://render.githubusercontent.com/render/math?math=f(x)%20%3D%20E%5BY%20%7C%20X%20%3D%20x%20%5D%20-%20%5Cmu_%7BY%7D)

Having: 

![z ~ N(\mu_{Y}, \sigma_{Y}^2)](https://render.githubusercontent.com/render/math?math=z%20~%20N(%5Cmu_%7BY%7D%2C%20%5Csigma_%7BY%7D%5E2))

Solution is:

![E_{Y|X}\[Y\] = E_{Y|X}\[f(X)\] + E_{Y|X}\[z\]](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5BY%5D%20%3D%20E_%7BY%7CX%7D%5Bf(X)%5D%20%2B%20E_%7BY%7CX%7D%5Bz%5D)

By definition:

![E_{Y|X}\[f(X)\] = \int_{-\infty}^{\infty} f(x) p(y | x) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20f(x)%20p(y%20%7C%20x)%20dy)

![E_{Y|X}\\[z\] = \int_{-\infty}^{\infty} z p(y | x) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5C%5Bz%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20z%20p(y%20%7C%20x)%20dy)

We also know that:

P(y) = P(x,z)

But x and z are independent. Thus:

![P(y|x) = \frac{P(x)P(y)}{P(x)} = P(z)](https://render.githubusercontent.com/render/math?math=P(y%7Cx)%20%3D%20%5Cfrac%7BP(x)P(y)%7D%7BP(x)%7D%20%3D%20P(z))

Then these terms become:
![E_{Y|X}\[f(X)\] = \int_{-\infty}^{\infty} f(x) p(z) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20f(x)%20p(z)%20dy)

![E_{Y|X}\[z\] = \int_{-\infty}^{\infty} z p(z) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bz%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20z%20p(z)%20dy)

However, integral is in respect to y, not z. And we cannot take it out since z is a function of y. We do a change of variables. Since we are working conditioning on x, we can think of x as being constant. Thus:

![y = x + z](https://render.githubusercontent.com/render/math?math=y%20%3D%20x%20%2B%20z)

![dy = dz](https://render.githubusercontent.com/render/math?math=dy%20%3D%20dz)

To get the new bounds on the integral respective to z (assuming x is a constant), we replace values of y to get the new z. 

Upper bound:

![\infty - x = z \xrightarrow{} z = \infty](https://render.githubusercontent.com/render/math?math=%5Cinfty%20-%20x%20%3D%20z%20%5Cxrightarrow%7B%7D%20z%20%3D%20%5Cinfty)

Lower bound:

![-\infty - x = z \xrightarrow{} z = -\infty](https://render.githubusercontent.com/render/math?math=-%5Cinfty%20-%20x%20%3D%20z%20%5Cxrightarrow%7B%7D%20z%20%3D%20-%5Cinfty)

Replacing y we get:

![E_{Y|X}\[f(X)\] = \int_{-\infty}^{\infty} f(X) p(z) dz](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20f(X)%20p(z)%20dz)

![E_{Y|X}\[z\] = \int_{-\infty}^{\infty} z p(z) dz](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bz%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20z%20p(z)%20dz)

But f(X) does not depend on y, thus we can take it out of the integral:

![E_{Y|X}\\[f(X)\\] = f(X)\int_{-\infty}^{\infty} p(z) dz](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5C%5Bf(X)%5C%5D%20%3D%20f(X)%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20p(z)%20dz)

The remaining integral is that of a probability distribution over its entire support, which integrates to 1:

![E_{Y|X}\[f(X)\] = f(x) ](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20f(x)%20)

Regarding the other term, we see that it's just the definition of the expectation of z. Thus:

![E_{Y|X}\[z\] = E\[z\] = \mu_{Y}](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bz%5D%20%3D%20E%5Bz%5D%20%3D%20%5Cmu_%7BY%7D)

Finally:

![E_{Y|X}\[Y\] = f(x) + \mu_{Y}](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5BY%5D%20%3D%20f(x)%20%2B%20%5Cmu_%7BY%7D)

Rearranging terms:

![f(x) = E_{Y|X}\[Y\]  - \mu_{Y}](https://render.githubusercontent.com/render/math?math=f(x)%20%3D%20E_%7BY%7CX%7D%5BY%5D%20%20-%20%5Cmu_%7BY%7D)
