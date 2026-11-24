# Fitting Poisson  distribution
# Program :
```


import numpy as np
import math
import scipy.stats
L=[int(i) for i in input().split()]
N=len(L)
M=max(L) 
X=[]
f=[]
for i in range (M+1):
    c = 0
    for j in range(N):
        if L[j]==i:
            c=c+1
    f.append(c)
    X.append(i)
Sff=np.sum(f)
p=[]
for i in range(M+1):
    p.append(f[i]/Sf) 
mean=np.inner(X,p)
p=[]
E=[]
xi=[]
print("X P(X=x) Obs.Fr Exp.Fr xi")
print("--------------------------")
for x in range(M+1):
    p.append(math.exp(-mean)*mean**x/math.factorial(x))
    E.append(p[x]*sf)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.3f %4.2f %3.2f %3.2f"%(x,p[x],f[x],E[x],xi[x]))
print("--------------------------")
cal_chi2_sq=np.sum(xi)
print(f"Calculated value of Chi square is {cal_chi2_sq:.2f}")
table_chi2=scipy.stats.chi2.ppf(1-.01,df=M)
print(f"Table value of chi square at 1 level is {table_chi2:.2f}")
if cal_chi2_sq<table_chi2:
    print("The given data can be fitted in poisson Distribution at 1% LOS")
else:
    print("The given data cannot be fitted in Poisson Distribution at 1% LOS")
```

# Output : 

![image](https://github.com/user-attachments/assets/719abda5-d439-4586-9326-0e31182496c7)

# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
