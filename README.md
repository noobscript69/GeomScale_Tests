# Monte Carlo Integration
*Easy*
---
Task: Easy: compile and run volesti. Read the CRAN package [documentation](https://cran.rstudio.com/web/packages/volesti/volesti.pdf), generate a random H-polytope and compute its volume.

- Compiled and ran volesti tests in C++ interface using cmake, make and ctest. Also installed all package dependencies like Rcpp, RcppEigen, BH etc and used devtools to install volesti Rcpp Package
- Generated a random H-polytope and computed its volume 

*Code*
```R
library(volesti)
P = gen_cube(100,'H')
volumes <- list()
for (i in 1:10) {
volumes[[i]] <- volume(P) # default parameters
}
options(digits=10)
summary(as.numeric(volumes))
```
