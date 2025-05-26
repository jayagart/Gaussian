# Gaussian Elimination
## NAME: Jayagar.T
## REG.NO: 212224220042
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the number of variables:
   - Read an integer 'n' representing the number of equations and unknowns.

2. Initialize matrices:
   - Create an augmented matrix 'a' of size n x (n+1) to store both coefficients and constants.
   - Create a solution vector 'x' of size n and initialize all elements to 0.

3. Read the augmented matrix:
   - For each row i from 0 to n-1:
       For each column j from 0 to n:
           - Read the value a[i][j] (coefficients and constants).

4. Forward Elimination (Gaussian Elimination):
   - For each pivot row i from 0 to n-1:
       a. Check if a[i][i] == 0:
           - If true, terminate the program with an error ("Divide by zero detected").
       b. For each row j below the pivot (from i+1 to n-1):
           - Compute ratio = a[j][i] / a[i][i]
           - For each column k from 0 to n:
               - Update a[j][k] = a[j][k] - ratio * a[i][k]

5. Back Substitution:
   - Start solving from the last row up to the first.
   - x[n-1] = a[n-1][n] / a[n-1][n-1]
   - For i from n-2 down to 0:
       a. Set x[i] = a[i][n]
       b. For j from i+1 to n-1:
           - x[i] -= a[i][j] * x[j]
       c. x[i] /= a[i][i]

6. Output the solution:
   - Print x[0], x[1], ..., x[n-1] with two decimal places.
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Jayagar.T
RegisterNumber: 212224220042
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))

x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected')
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
        
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')
```

## Output:
![gaussian elimination]()

![image](https://github.com/user-attachments/assets/b31ea263-b0d1-4c68-89d5-f7b08f42087d)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

