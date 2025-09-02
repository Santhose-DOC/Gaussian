# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Accept the size of the augmented matrix, n.

Step 2: Create an n×(n+1) augmented matrix a and a solution vector x.

Step 3: Populate the augmented matrix a with user inputs.

Step 4: Ensure no diagonal element in the matrix is zero; exit if a zero is detected to avoid division by zero.

Step 5: a. For each pivot row i, normalize the pivot row. b. Subtract a scaled version of the pivot row from rows below to make the elements below the pivot zero.

Step 6: Calculate the value of the last variable, x n−1, using the last row.

Step 7: a. For each row from n−2 to 0, calculate the corresponding variable by subtracting contributions from previously solved variables. b. Divide by the diagonal coefficient to find the solution for the current variable.

Step 8: Divide each solution by its corresponding diagonal coefficient to ensure accuracy.

Step 9: Print the values of all variables

Step 10: Display the results with formatting to two decimal places.End of the program


## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Santhose Arockiaraj J
RegisterNumber: 212224230248
'''
import numpy as np
import sys

# Reading the number of unknown
n=int(input())

# Creating the Augumented matrix of 3 X 4 and each element is filled with zeroes
a=np.zeros((n,n+1))

# Creating the Solution Matrix and each element is filled with zeroes
x=np.zeros(n)

# Reading Augumented Matrix Coeffient
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
# Applying the Gauess Elmination
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]

# Back Substitution
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]

# Display The solution 
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")


 
```

## Output:

<img width="1296" height="2026" alt="Screenshot 2025-09-02 144710" src="https://github.com/user-attachments/assets/8a442b95-5cf1-4934-9fd7-f04b279aa5f1" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

