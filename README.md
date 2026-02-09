# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: G.SANTHIYA
RegisterNumber: 25017564
'''
import numpy as np
def qr_decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)
```

## Output

<img width="1465" height="472" alt="Screenshot 2026-02-09 185955" src="https://github.com/user-attachments/assets/a0adb627-6c7f-4e55-b4d2-f578a4d30478" />
<img width="1470" height="603" alt="Screenshot 2026-02-09 190007" src="https://github.com/user-attachments/assets/eda64045-e174-437b-bf21-dc5cd4229cae" />
<img width="1484" height="667" alt="Screenshot 2026-02-09 190016" src="https://github.com/user-attachments/assets/ce4fb38c-c756-45de-af35-9ed09ebbfe1a" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
