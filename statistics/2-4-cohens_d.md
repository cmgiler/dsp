[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

### Code:

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import nsfg
import first
import thinkstats2
import thinkplot

# Load data according to Chapter 2 lessons
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

# Plot data (also from Chapter 2 lessons)
first_hist = thinkstats2.Hist(firsts.prglngth)
other_hist = thinkstats2.Hist(others.prglngth)

width = 0.45
plt.figure(figsize=(12,8))
thinkplot.PrePlot(2)
thinkplot.Hist(first_hist, align='right', width=width)
thinkplot.Hist(other_hist, align='left', width=width)
thinkplot.Show(xlabel='weeks', ylabel='frequency')

# Function for Cohen Effect Size calculation (Chapter 2)
def CohenEffectSize(group1, group2):
    import math
    diff = group1.mean() - group2.mean()
    
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    
    pooled_var = (n1*var1 + n2*var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d
    
# Calculate Cohen's d
d_totalwgt = CohenEffectSize(firsts.totalwgt_lb,
                             others.totalwgt_lb)
d_prglngth = CohenEffectSize(firsts.prglngth,
                             others.prglngth)
print('Cohen d for total weight: \t%0.4f' % (d_totalwgt))
print('Cohen d for pregnancy length: \t %0.4f' % (d_prglngth))
```
---
### Output:

>> Cohen d for total weight: 	-0.0887

>> Cohen d for pregnancy length: 	 0.0289

As a general guideline, a **Cohen's d** value less than 0.2 indicates a small effect size. With the value calculated for both total weight and pregnancy length, **d** is much lower than 0.2, so we can infer that the difference is trivial, even if it is found to be statistically significant.