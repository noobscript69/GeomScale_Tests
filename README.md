# Monte Carlo Integration
*Easy*
---
Task: Easy: compile and run volesti. Read the CRAN package [documentation](https://cran.rstudio.com/web/packages/volesti/volesti.pdf), generate a random H-polytope and compute its volume.

- Compiled and ran volesti tests in C++ interface using cmake, make and ctest. Also installed all package dependencies like Rcpp, RcppEigen, BH etc and used devtools to install volesti Rcpp Package
- Generated a random H-polytope and computed its volume 

*Code*
```R
library(volesti)
P = gen_rand_hpoly(10, 50, generator = list(constants = "sphere"))
volumes <- list()
for (i in 1:10) {
volumes[[i]] <- volume(P) # default parameters
}
options(digits=10)
summary(as.numeric(volumes))
```
# *Medium*
---
Medium: Use the R package [cubature](https://cran.r-project.org/web/packages/cubature/index.html) to compute the integral of f(x) = exp^{-a||x||^2} over the cube [-1,1]^n, for various values of a and dimension n until it crashes.

- Installed R package ``cubeture`` and used ``cubeture`` library to compute the integral of f(x) = exp^{-a||x||^2} over the cube [-1,1]^n.
- I tried varios values of a=[0,1,2,3] and the values of n incrementing by 1 stating from the number 1.
- At the value of n=24 the program got crashed due to the higher dimention used showing the result 0.
- Ovserving this we can say this package is way more less efficient than `volesti` package. using volesti approximation we can compute up to a few hundreds of dimensions. 

*Code*
```R

library(cubature) # load the package "cubature"
testFnWeb <- function(x) {
  exp(-a * sum(x^2))
}
hcubature(testFnWeb, rep(-1,n), rep(1,n), tol=1e-4)

```
