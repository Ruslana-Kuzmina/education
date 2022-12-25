# Matrices and Operations

## Matrices. Addition, Subtraction, and Scalar Multiplication

Each element of a matrix, denoted aij , has two indices: the first index i indicates
the row where the element is located, and the second index j indicates the column.
That is, the element aij is the number in the i row and the j column. In compact
form, he matrix A can be written as A = |aij|, i = 1, ... j = 1....

Depending on dimensions, the following types of matrices are distinguished:

- A Square Matrix
  A matrix A is a square matrix if it has the same number of rows and columns;
  that is, if m = n

- A Row Matrix
  A matrix A is a row matrix if it consists of one row.

- A Colomn Matrix
  A matrix  is a column matrix if it consists of one column.

### Addition of Matrices

To add two matrices, you need to add their corresponding elements. However, to
perform this operation, the dimensions of the matrices must be the same. Otherwise,
the sum of the matrices will be undefined.

  Cij = aij + bij

Properties of Matrix Addition:

If we suppose that the matrices A, B, and C are of equal size, then the following
properties of matrix addition can be formulated:

- Matrix addition is commutative.

A + B = B + A

- Matrix addition is associative.

(A + B) + C = A + (B + C)

For a matrix A, there exists a zero matrix of similar dimensions, denoted by 0,
or additive identity, such that

A + 0 = A

A zero matrix is a matrix where all the elements are zero.

- For a matrix A, there exists a matrix -A, or additive inverse, such that

A + (- A) = 0

### Subtraction of Matrices

To subtract two matrices, you need to subtract their corresponding elements. As
in addition, matrices must be of the same dimensions. Otherwise, the difference
of the matrices will be undefined.

Cij = aij - bij

### Scalar Multiplication of Matrices

To multiply a matrix by a real number, or a scalar, you need to multiply each
element of the matrix by a scalar.

cA = caij

Properties of Scalar Multiplication:

To formulate the properties of scalar multiplication, let us introduce equal sized
 matrices A and B, and scalars c and d. Then, we have the following:

- Scalar multiplication is distributive over matrix addition.

c(A + B) = cA + cB

- Scalar multiplication is distributive over scalar addition.

(c + d)A = cA + dA

- Scalar multiplication is associative.

c(dA) = (cd)A

- Multiplication by 1.

1A = A

## Matrix Multiplication and Transpose

The first thing that should be mentioned is that multiplication of two matrices
is possible only when the number of columns of the first matrix is equal to the
number of rows of the second matrix. Otherwise, the product is undefined.

Consider a matrix A of the size m*n and a matrix B of the size n*p.

The number of columns of A matches the number of rows of B. Therefore, the product
AB is defined and is a matrix of the size m*p.

(m*n)(n*p) = (m*p)

To obtain the element ab12 of AB, multiply the first row of A by the second column
of B element-wise, and add.

Properties of Matrix Multiplication:

- Matrix multiplication is associative.

(AB)C = A(BC)

- Matrix multiplication is distributive.

C(A+B) = CA + CB
(A+B)C = AC + BC

- Matrix multiplication is not commutative.

AB =/ BA

### Transpose

To take the transpose of a matrix you need to transform the original matrix so
that the rows become columns. In other words, the first column of the transposed
matrix is the first row of the original matrix, the second column of the transposed
matrix is the second row of the original matrix, and so on.

A = [123
     456
     789]

A^T = [147
       258
       369]

Let us introduce two scalars c and d, and two matrices A and B of the size that
allows to perform the specified operations.

Properties of the Transpose of a Matrix:

(A^T)^T = 1
(AB)^T = B^TA^T
(cA + dB)^T = cA^T + dB^T

## Augmented Matrix

This system of equations can be represented as a matrix called **augmented matrix**.

An augmented matrix consists of a **coefficient matrix**, whose elements are the
coefficients of the system, and a **constant matrix**, whose elements are the
constants of the system. These matrices are separated from each other by a vertical
line.

In an augmented matrix, each row corresponds to a particular equation in the
system. For example, the first row
|a11 a12 ... a1n|b1|

corresponds to the first equation a11x1 + a12x2 + ... + a1nxn = b1

Also, note that each column of the coefficient matrix includes the coefficients of
a particular variable in each equation. That is, the first column includes the
coefficients of x1, the second column includes the coefficients of x2, and so on.
If some variable is missed in the equation, the corresponding element in the
coefficient matrix will be 0.

### Row-echelon Form and Row Operations

Now that we have already discussed how to write an augmented matrix when given a
system of equations, we should consider **row operations** that can be performed
on the matrix. It is important to note that row operations on an augmented matrix
do not affect the solution of the corresponding system of equations. Row operations
are equivalent to operations on equations and are used to transform the original
matrix to a **row-equivalent matrix** in a simpler form. Despite the fact that in
this module we will not go deeper into solving systems of equations using matrices,
knowledge of the operations that can be performed on the rows of matrices and what
row-echelon form of the matrix is will be a bonus for you in further study.

Row operations include the following:

- Swapping two rows
- Multiplying a row by a nonzero number
- Adding a row multiplied by a number to another row

To solve a system of equations using an augmented matrix, we need to convert the
matrix to **row-echelon form**. A matrix in row-echelon form is a matrix that meets
the following conditions:

- In each row, the leading element is 1. The leading element is the first nonzero
  element in a row when reading the row from left to right
- Any leading element is to the right of the leading element above it
- All rows containing all zero-elements are at the bottom of the matrix
- In any column, all elements below the leading one are zeros

ROW ECHELON FRM

[1 a12 a13
 0  1  a23
 0  0   1 ]

## Inverse and Identity Matrices

The **identity matrix** is a square matrix I which has all 1's along the main
diagonal and 0's for all other entries. It is generally accepted to denote the
identity matrix to be of the size n*n by In.

The term the **main diagonal** usually refers to a square matrix. In a square
matrix A = |aij|, i,j = 1 ... n , the main diagonal is the elements aij for which
i = j.

The matrix I is called the identity matrix because multiplication by it leaves a
matrix unchanged.

AIn = InA = A

### Inverse of a Matrix

A square n*n matrix A has an inverse A^-1 if and only if

AA^-1 = A^-1A = In

The matrix A in this case is called invertible.

Note that not all square matrices have an inverse. However, if an inverse exists,
then it is unique.

#### Uniqueness of Inverse

If A is an n*n matrix and it has an inverse A^-1, then A^-1 is unique. That is,
provided that AB = BA = I, B = A^-1.

##### Finding the Inverse of a Matrix Using a Formula

If we are asked to find the inverse of a 2*2 matrix, we can use a special formula
instead of matrix multiplication.

Consider a 2*2 matrix A that has the following form

A = [ab
     cd]

The inverse of A can be determined by the formula

A^-1 = 1 / ad - bc * [d -b]
                     [-c a]

where ad-bc =/0. If ad-bc = 0, the matrix A does not have an inverse.

## The Determinant of a Matrix

In this section, we will consider a concept of the determinant of a matrix.
Determinants are used for determining whether a matrix is invertible, for solving
systems of linear equations, for calculating area or volume, and even in cryptography.

The determinant of the matrix A, denoted by det(A) or |A|, is a real number determined
as

det(A) = |ab| = ad - cb
         |cd|

Pay attention that a matrix is enclosed in parentheses while a determinant is
enclosed in vertical lines.

It is also important to note here that the concept of a determinant applies only
to square matrices.

A matrix has an inverse if and only if its determinant is not equal to zero.

### Finding the Determinant of a 3*3 Matrix

Calculating the determinant of a 3*3 matrix is not as straightforward as for
a 2*2 matrix. We will consider how to calculate the determinant using **cofactor**
**expansion** or **Laplace expansion**. But first, let us introduce the necessary
definitions.

The ijth minor of a 3*3 matrix A, denoted by Mij, is the determinant of a smaller
square matrix obtained by removing the ith row and jth column from A.

You need to delete row and column by number

The ijth cofactor of a 3*3 matrix A, denoted by Cij, is a signed minor Mij.

Cij = (-1)^i+j*Mij

Here, the multiplier (-1)^i+j is the sign defined by the position of the element
aij in the matrix.















