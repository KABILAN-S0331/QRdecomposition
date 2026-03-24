# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1. Start the program and import required libraries (numpy).
2. Input matrix A from the user and convert it into a NumPy array.
3. Initialize matrices Q and R with appropriate dimensions (Q as zero matrix of size n×m, R as m×m).
4. Apply Gram-Schmidt process
5. For each column of A, compute orthogonal vectors and normalize them to form Q.
6. Compute corresponding elements of R using dot products and norms.
7.Display matrices Q and R and stop the program.



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: KABILAN S
RegisterNumber: 212225230119
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np

def QR_Decomposition(A):
    n, m = A.shape
    
    Q = np.zeros((n, m))
    R = np.zeros((m, m))
    
    for i in range(m):
        u = A[:, i]
        
        for j in range(i):
            R[j, i] = np.dot(Q[:, j], A[:, i])
            u = u - R[j, i] * Q[:, j]
        
        R[i, i] = np.linalg.norm(u)
        Q[:, i] = u / R[i, i]
    
    print("The Q Matrix is\n", Q)
    print("The R Matrix is\n", R)


a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output

<img width="1919" height="852" alt="image" src="https://github.com/user-attachments/assets/acd7c78d-b306-48b8-9fa0-4b1f557176d1" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
