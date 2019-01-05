[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)
```
‌import numpy as np
import pandas
import nsfg
import first
import math

preg = nsfg.ReadFemPreg()
resp = nsfg.ReadFemResp()

weight_order = pandas.DataFrame(preg['totalwgt_lb'])
weight_order['pregordr'] = preg['pregordr']

weight_order_first = weight_order.query('pregordr == 1')
weight_order_other = weight_order.query('pregordr > 1')

mean1, mean2 = weight_order_first['totalwgt_lb'].mean(), weight_order_other['totalwgt_lb'].mean()
len1, len2 = len(weight_order_first), len(weight_order_other)
var1, var2 = weight_order_first['totalwgt_lb'].var(), weight_order_other['totalwgt_lb'].var()

diff = mean1 - mean2
pooled_var = (len1 * var1 + len2 * var2) / (len1 + len2)
d = diff / math.sqrt(pooled_var)

print(d)
```
The Cohen’s D for the weight of first babies vs non-first babies is -0.06911825348820934.

This suggests that though first babies do tend to be slightly lighter than other babies, the effect size is very small and likely insignificant. 
