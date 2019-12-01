## Solutions to chapter 4

### 4.16

There is a typo on what the proof is, the correct proof is:

Prove that:

![f(x) = E\[Y | X = x \] - \mu_{Y}](https://render.githubusercontent.com/render/math?math=f(x)%20%3D%20E%5BY%20%7C%20X%20%3D%20x%20%5D%20-%20%5Cmu_%7BY%7D)

Solution is:

![E_{Y|X}\[Y\] = E_{Y|X}\[f(X)\] + E_{Y|X}\[\N_{Y}\]](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5BY%5D%20%3D%20E_%7BY%7CX%7D%5Bf(X)%5D%20%2B%20E_%7BY%7CX%7D%5B%5CN_%7BY%7D%5D)

By definition:

![E_{Y|X}\[f(X)\] = \int_{-\infty}^{\infty} f(x) p(y | x) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20f(x)%20p(y%20%7C%20x)%20dy)

![E_{Y|X}\[\N_{Y}\] = \int_{-\infty}^{\infty} N_{Y} p(y | x) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5B%5CN_%7BY%7D%5D%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20N_%7BY%7D%20p(y%20%7C%20x)%20dy)

But f(X) does not depend on y, thus we can take it out of the integral:

![E_{Y|X}\\[f(X)\\] = f(x) \int_{-\infty}^{\infty} p(y | x) dy](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5C%5Bf(X)%5C%5D%20%3D%20f(x)%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7D%20p(y%20%7C%20x)%20dy)

The remaining integral is that of a probability distribution over its entire support, which integrates to 1:

![E_{Y|X}\[f(X)\] = f(x) ](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5Bf(X)%5D%20%3D%20f(x)%20)

And ![N_y](https://render.githubusercontent.com/render/math?math=N_y) is independent of X, thus ![E_{Y|X}\[N_{Y}\] = E\[N_{Y}\] = \mu_{Y}](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5BN_%7BY%7D%5D%20%3D%20E%5BN_%7BY%7D%5D%20%3D%20%5Cmu_%7BY%7D)

Finally:

![E_{Y|X}\[Y\] = f(x) + \mu_{Y}](https://render.githubusercontent.com/render/math?math=E_%7BY%7CX%7D%5BY%5D%20%3D%20f(x)%20%2B%20%5Cmu_%7BY%7D)

Rearraging terms:

![f(x) = E_{Y|X}\[Y\]  - \mu_{Y}](https://render.githubusercontent.com/render/math?math=f(x)%20%3D%20E_%7BY%7CX%7D%5BY%5D%20%20-%20%5Cmu_%7BY%7D)
