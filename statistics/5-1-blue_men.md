[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)
```
import numpy as np
import pandas
import scipy.stats

import first
import thinkstats2
import thinkplot
import brfss

df = brfss.ReadBrfss()
men = df.query('sex==1')
heights = men['htm3']

mu = heights.mean()
sigma = heights.std()

cdf_low = scipy.stats.norm.cdf(177.8, mu, sigma)
cdf_high = scipy.stats.norm.cdf(185.42, mu, sigma)

print(cdf_low)
print(cdf_high)

print(cdf_high - cdf_low)
```
The CDF lower bound is 0.48625170584113814 and the CDF upper bound is 0.829482582277679, which taking the difference means that the probability of a randomly selected man being eligible for Blue Man Group is 0.3432308764365409, or around 34%. 

Since CDF is a measure of the sum of the probability distribution up to a certain value, we can bound the two sides of the Blue Man Group eligibility probability distribution by converting the eligibility requirements from feet to centimeters and calculating the CDF for those two values. All values inside those bounds are eligible, and values outside of those bounds are not.  
