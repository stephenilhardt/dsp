[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)
```
import numpy as np
import pandas

import nsfg
import first
import thinkstats2
import thinkplot

resp = nsfg.ReadFemResp()

actual_dist = pandas.DataFrame(resp['numkdhh'])
actual_pmf = thinkstats2.Pmf(actual_dist['numkdhh'])

print(actual_pmf)

biased_pmf = actual_pmf.Copy()

for x, p in actual_pmf.Items():
    biased_pmf.Mult(x, x)

biased_pmf.Normalize()    

print(biased_pmf)

thinkplot.Pmfs([actual_pmf, biased_pmf])

print(actual_pmf.Mean())
print(biased_pmf.Mean())
```
The actual mean number of children under the age of 18 for the respondents was 1.024205155043831. The biased mean for under-18 respondents with one or more children under 18 in the family was 2.403679100664282.

This proves that statistics calculated from survey results can misrepresent the overall data depending on the bias of those surveyed. 
