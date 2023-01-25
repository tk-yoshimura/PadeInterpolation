# PadeInterpolation

## Benchmark
![fitting benchmark](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/fitting_benchmark.svg)  

## Define
Padé interpolation is the best rational function that minimizes that the squared distance to multiple points.  

When the explanatory and objective variables are *x* and *y*,  
a rational function with maximum coefficients *m* and *n* in the numerator and denominator is defined by the following equation:

![pade define](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_define.svg)  

The error for a single point is defined by the following equation:  

![pade error](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_error.svg)  

The weighted squared error for multiple points is given by the following equation in the definition.   
If it is not weighted, it can be interpreted as if all *w* were 1.

![pade error sum](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_error_sum.svg)  

## Solve
The parameter that minimizes the error is the point at which the partial derivative of each parameter is 0.  
Fortunately, it can be solved as a linear problem.

![pade partial p0](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_partial_p0.svg)  
![pade partial pk](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_partial_pk.svg)  
![pade partial qk](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_partial_qk.svg)  

The matrix representation is as follows. Note that the matrix is symmetric.  

When the *y*-intercept is not fixed:  
![pade matrix with intercept](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_matrix_with_intercept.svg)  

When the *y*-intercept(*p*<sub>0</sub>=*a*) is fixed:  
![pade matrix without intercept](https://github.com/tk-yoshimura/PadeInterpolation/blob/main/figures/pade_matrix_without_intercept.svg)  

## Implement
See below for an example implementation.  
Since this is a calculation that produces many digit loss, the double precision does not produce the expected results.  
[MultiPrecisionCurveFitting](https://github.com/tk-yoshimura/MultiPrecisionCurveFitting)

## See Also
[PadeApproximation](https://github.com/tk-yoshimura/PadeApproximation)