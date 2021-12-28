![image](https://user-images.githubusercontent.com/36400060/147608297-472147c9-2e1c-4c76-b2ce-c3bac19237d7.png)
![image](https://user-images.githubusercontent.com/36400060/147608319-f2a2bb34-28c2-4fd5-9afa-9cf8b064b578.png)
Explanation of table-
B : Basis and contains the basic variables. Simplex algorithm starts with those variables which form an indentity matrix. In the above eg x4 and x3 forms a 2×2 identity matrix.
CB : Its the coefficients of the basic variables in the objective function. The objective functions doesn’t contain x4 and x3, so these are 0.
XB : The number of resources or we can say the RHS of the constraints.
yi : The complete Matrix A.
Simplex Algorithm
1. Start with the initial basis associated with identity matrix.
2. Calculate the relative profits. 

For MAX problem-
If all the relative profits are less than or equal to 0, then the current basis is the optimal one. STOP.
Else continue to 3.

For MIN problem 
If all the relative profits are greater than or equal to 0, then the current basis is the optimal one. STOP.
Else continue to 3.

3. Find the column corresponding to max relative profit. Say column k has the max 
Rel. profit. So xk will enter the basis.

4. Perform a min ratio test to determine which variable will leave the basis.
    min ratio test:  XBr/y_{rk} = min\{XB_i/y_{ik}\}  
Index of the min element i.e 'r' will determine the leaving variable.
The basic variable at index r, will leave the basis. 
NOTE: Min ratio test is always performed on positive elements.

5. It's evident that the entered variable will not form an identity matrix, so 
we will have to perform row operations to make it identity again.
Find the pivot element. The element at index (r, k) will be the pivot element and 
row r will be the pivot row. 

6. Divide the rth row by pivot to make it 1. And subtract c*(rth row) from other 
rows to make them 0, where c is the coefficient required to make that row 0.
Table at Iteration 1


Table at iteration 1

![image](https://user-images.githubusercontent.com/36400060/147608434-5e6f97dc-cc12-46d6-afff-316db97ac9bf.png)


Calculation of relative profits – (Cj – Zj), where Cj is the coefficient in Z and Zj is yi*CB
C1 – Z1 = 1 – (1*0 + 2*0)
C2 – Z2 = 1 – (1*0 + 1*0)
C3 – Z3 = 0 – (0*0 + 1*0)
C4 – Z4 = 0 – (1*0 + 0*0)

So Relative profits are- 1, 1, 0, 0 (As shown in the table)
Clearly not all the relative profits are less or equal to 0. So will perform the next iteration.
Determination of entering variable and leaving variable.
Max relative profit 1 at index 1. So x1 will enter the basis.
   min ratio test:  XBr/y_{rk} = min\{8/1, 10/2\}  
Min of (8, 5) is 5 which is at index 2. So x3 will leave the basis.

Since x1 entered perform required row operations to make an identity matrix.

Pivot index = [2, 4]
Pivot element = 2

Divide the 2nd row by pivot element i.e 2 to make it 1.
And subtract 1*R2 from R1 to make it 0
See the next table.

Table At Iteration 2
![image](https://user-images.githubusercontent.com/36400060/147608471-8bd63eb9-05c7-44bd-a02f-ac90b9abfc9f.png)


Table at iteration 2

Relative profits = 0, 1/2, -1/2, 0
Pivot index = [1, 5]
Pivot element = 1/2
Perform necessary row operations.
See next table


Table At iteration 3

![image](https://user-images.githubusercontent.com/36400060/147608504-1b39e945-c540-4453-94a7-87eb9d989c13.png)

Relative profits = 0, 0, 0, -1
Since all relative profits are less than or equal to 0. So optimality is reached.
This will be the final simplex table and the optimal one.
Value of Z at optimality = 6*1 + 2*1 = 8


source: https://www.geeksforgeeks.org/simplex-algorithm-tabular-method/

