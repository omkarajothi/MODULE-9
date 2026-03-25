## MODULE - 9
# EXP 41: List Comprehension-Generates all even numbers between 200 and 300
##  AIM:
To write a Python class-based program that generates all even numbers between 200 and 300 using **list comprehension**, and stores them in a list.


##  ALGORITHM:

1. **Start**
2. Create a class named `program`
3. Create variables `a`, `b`, and `c` to represent:
   - `a`: Lower limit
   - `b`: Step value
   - `c`: Upper limit
4. Initialize the values using a constructor `__init__`
5. Define a method `display()` that uses **list comprehension** to store even numbers
6. Print the resulting list of even numbers
7. **Stop**


##  PROGRAM:
```
class program:
    def __init__(self):
        self.a = 200      
        self.b = 1        
        self.c = 300      # 
        
    def display(self):
        even_numbers = [i for i in range(self.a, self.c + 1, self.b) if i % 2 == 0]
        print("Even numbers between", self.a, "and", self.c, ":")
        print(even_numbers)

obj = program()
obj.display()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/6fd2fe23-966e-4876-92e2-a3e67d49c72e)

## RESULT:
Thus, the program is verified successfully.

---

# EXP 42 - List Comprehension:Transpose of Matrix 

## AIM:
To write a Python program to compute the **transpose** of a matrix using **list comprehension**.


##  ALGORITHM:

1. **Start**
2. Create variables `r` and `c` to represent the number of rows and columns of the matrix.
3. Get the values of `r` and `c` from the user.
4. Define a function `create(r, c)` to create the matrix by reading the elements from the user.
5. Use **list comprehension** to calculate the transpose of the matrix.
6. Print the transposed matrix.
7. **Stop**


##  PROGRAM:
```
def read_matrix(r,c):
    matrix = [[0]*c for row in range(r)]
    for i in range(r):
        lines = list(map(int, input().split()))
        for j in range(c):
            matrix[i][j] = lines[j]
    return matrix
def print_matrix(M):
    print("Matrix:")
    for i in range(len(M)):
        for j in range(len(M[0])):
            print(M[i][j],end=" ")
        print()
def transpose(M):
    result = [[0]*len(M) for rows in range(len(M[0]))]
    for i in range(len(M)):
        for j in range(len(M[0])):
            result[j][i] = M[i][j]
    return result

r,c=input().split()
M=read_matrix(int(r),int(c))
print_matrix(M)
print_matrix(transpose(M))
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/ae3e0326-45bf-4442-81a8-f8acd77f31a0)

## RESULT:
Thus, the program is verified successfully.

---

# EXP 43: Matrix Operations-Diagonal Matrix Elements Printer 

This Python program reads a matrix of any size from the user and prints **only the diagonal elements**, leaving other elements blank in the output.

##  Aim

To write a Python program that prints only the diagonal elements of a given matrix.

##  Algorithm

1. Read the number of rows and columns from the user.
2. Initialize an empty matrix of size `rows × columns`.
3. Populate the matrix with user input.
4. Display the full matrix.
5. Iterate through the matrix and:
   - If `i == j`, print the element (main diagonal).
   - Else, print a blank space.
6. Print a newline after each row.

##  Program
```
rows = int(input())
columns = int(input())
matrix = [[0]*columns for row in range(rows)]
for i in range(rows):
    lines = list(map(int, input().split()))
    for j in range(columns):
        matrix[i][j] = lines[j]
print(matrix)
for i in range(rows):
    for j in range(columns):
        if(i==j):
            print(matrix[i][j],end=" ")
        else:
            print(' ',end=" ")
    print()
```

## Output:
![image](https://github.com/user-attachments/assets/071bd08a-fc35-4dc2-87e5-7467c96b1372)

## Result
Thus, the program is verified successfully.

---

# EXP 44: Matrix Operations-Matrix Subtraction in Python

##  AIM:
To write a Python program that reads two matrices from the user and performs matrix subtraction.


##  ALGORITHM:

1. **Start**
2. Create variables `r` and `c` for rows and columns
3. Get the values of `r` and `c` from the user
4. Define a function `create_matrix(n, m)` to:
   - Prompt user for each matrix element
   - Append each row to form a complete matrix
5. Call the `create_matrix()` function twice to read two matrices `A` and `B`
6. Define a loop to subtract the elements of matrix `B` from matrix `A`
7. Store the result in a new matrix `C`
8. Print the resulting matrix `C`
9. **Stop**


##  PROGRAM:
```
def create_matrix(n, m):
    matrix = []
    for i in range(n):
        row = []
        for j in range(m):
            val = int(input())
            row.append(val)
        matrix.append(row)
    return matrix

r = int(input())
c = int(input())

A = create_matrix(r, c)
B = create_matrix(r, c)

C = []
for i in range(r):
    row = []
    for j in range(c):
        row.append(A[i][j] - B[i][j])
    C.append(row)

for row in C:
    print(*row)

```
## OUTPUT:
![image](https://github.com/user-attachments/assets/4de928cd-b0b1-4fa7-ba05-1d2e95f0d3e6)

## RESULT:
Thus, the program is verified successfully.

---

# EXP 45 - SORTING ALGORITHMS: Insertion Sort Using a Class

This program demonstrates how to implement the **Insertion Sort algorithm** using a Python class. It allows the user to input a list of numbers, sorts them using the insertion sort technique, and displays the sorted list.


##  Aim

To develop a Python class with functions to:
- Create a list of integers
- Sort it using the **Insertion Sort** algorithm
- Display the sorted list


##  Algorithm

1. **Start the program**
2. **Define a class** `InsertionSorter`
3. Inside the class:
   - `create_list()`:
     - Read number of elements
     - Store them in a list
   - `insertion_sort()`:
     - Iterate from the second element to the end
     - Move elements greater than the key to one position ahead
     - Insert the key at the correct position
   - `print_list()`:
     - Print the sorted list
4. **Create an object** of the class
5. **Call** the methods in order: `create_list()`, `insertion_sort()`, and `print_list()`
6. **End the program**


##  PROGRAM:
```
class InsertionSorter:
    def create_list(self):
        n = int(input())
        self.lst = [int(input()) for _ in range(n)]
        
    def insertion_sort(self):
        for i in range(1, len(self.lst)):
            key = self.lst[i]
            j = i - 1
            while j >= 0 and self.lst[j] > key:
                self.lst[j + 1] = self.lst[j]
                j -= 1
            self.lst[j + 1] = key
            
    def print_list(self):
        print(*self.lst)

sorter = InsertionSorter()
sorter.create_list()
sorter.insertion_sort()
sorter.print_list()

```

## OUTPUT:
![image](https://github.com/user-attachments/assets/f66afcf1-6563-4e37-82ff-181570be2dc2)

## RESULT:
Thus, the program is verified successfully.
