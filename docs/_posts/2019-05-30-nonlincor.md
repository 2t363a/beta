# Non-linear correlation

To find possible non-linear correlation we might use the well-known Hessian matrix.

## Multivariate Taylor expansion

In sufficient vicinity of **x**:

f(**x** + d**x**) = f(**x**) + (NABLA f) d**x** + 1/2(d**x**)^T H (d**x**) + ...

gWhere 

```
    NABLA f = GRAD(F)
    GRAD(F)(i) = df / dx_i
```
```          
               d^2 f 
    H(i, j) = ---------
               dx_i x_j
```

So when |H(i, j)| > EPS if i != j *suggests* correlation[1]


[1] Non-correlated function has H(i, j) = 0, i != j. However, H(i, j) = 0, i != j for *any* function is not sufficient
condition.


## Approximation of H(i, j)

It might be advisable to choose **h** = { h_1, h_2,..., h_n }.
And create a series of tests, consisting of:

1. Choose a **xc** point in the domain of f.

2. Perturb **xc** point for vector **dx**, which components are independent random variables with NORMAL(0, h_i).

3. Calculate the components of *H(i, j)* using formulas of numerical differentiation:

d2f/dx_i^2 = (f(**xc** + dx_i **e_i**) - 2 f(xc) + f(**xc** - dx_i **e_i**)) / dx_i / dx_i

d2f/dx_i dx_j = (f(**xc** + dx_i **e_i** + dx_j **e_j**) 
                 - f(**xc** - dx_i **e_i** + dx_j **e_j**) 
                 - f(**xc** + dx_i **e_i** - dx_j **e_j**)
                 + f(**xc** - dx_i **e_i** - dx_j **e_j**)
                ) / 4 / dx_i / dx_j

**e_i** - unit vector in *i*-th direction
**e_j** - unit vector in *j*-th direction

4. Averaging through *H(i, j)* values in different tests, one obtains an approximation of *H(i, j)* around point **xc**.

5. For 

**F = x1^2 + x2^2**

**xc** = { 0.5, 0.5 }

**h** = { 1 / 32, 1 / 32 }

N = 1024 tries

<H(1, 1)> = 2.000 +- 0.000 <H(1, 2)> = 0.000 +- 0.000

<H(2, 1)> = 0.000 +- 0.000 <H(2, 2)> = 2.000 +- 0.000


