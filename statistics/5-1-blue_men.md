[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

### Code:

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import nsfg
import first
import thinkstats2
import thinkplot

from scipy.stats import norm

# Given Data
mu_men = 178
sigma_men = 7.7
dist_men = norm(loc=mu_men, scale=sigma_men)

print("For Men:")
print("--------")
print("Mean: %0.1f" % dist_men.mean())
print("StdDev: %0.1f" % dist_men.std())

# Find percentage of men between 177.80 and 185.42
min_height = 177.80
max_height = 185.42

below_min = dist_men.cdf(min_height)
below_max = dist_men.cdf(max_height)

print("Percentage of Men Within Range (5'10\" to 6'1\"): %0.2f%%" % ((below_max-below_min)*100))
```

### Output:

> For Men:
> 
> ---
> 
> Mean: 178.0
> 
> StdDev: 7.7
> 
> Percentage of Men Within Range (5'10" to 6'1"): 34.27%