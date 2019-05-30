# Non-linear correlation

To find possible non-linear correlation we might use the well-known Hessian matrix.

## Multivariate Taylor expansion

In sufficient vicinity of **x**:

    f(**x** + d**x**) = f(**x**) + (NABLA f) d**x** + 1/2(d**x**)^T H (d**x**) + ...

    Where 

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




