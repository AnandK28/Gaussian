# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import NumPy as np for matrix operations.

2. Input number of variables n using input() and convert to integer.

3. Initialize an n x (n+1) augmented matrix a using np.zeros () .

4. Initialize a solution vector x of size n using np.zeros() .

5. Take user input for all coefficients and constants into matrix a using nested for loops and input() 

6. For each row i, ensure diagonal element a[i][i] is not zero to avoid division by zero.

7. For rows below i, eliminate variable by computing ratio - a[j][i] / a[i][i].

8. Subtract ratio*a[i][k] from a[j][k] for each column to form upper triangular matrix.

9. Back-substitute from last row to first using x[i] = (a[i][n] - Σ a[i][j]*x[j]) / a[i][i]

10. Print solution vector x using a loop and formatted print() 

## Program:
``` python

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: ANAND K 
RegisterNumber: 212224040022

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
        sys.exit('Divide by zero detected!')
    
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio *a[i][k]
            
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] =a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![image](https://github.com/user-attachments/assets/0e718995-8f81-423e-9b50-2687751abb87)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

