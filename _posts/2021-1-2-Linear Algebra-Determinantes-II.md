---
layout: post
title: Linear Algebra - Determinantes II
---

This chapter is part of a series that revisits some basic linear algebra. In this chapter well summarize basic concepts revolving around determinantes. 
This chapter continues [Linear Algebra - Determinantes I]({{ site.baseurl }}/Linear-Algebra-Determinants-I).

## Properties of Determinantes

### Transpose

A Transpose of a matrix can be defined as the following.

<div class="def" id="transpose">
Transpose
A matrix $A$ transpose $A^T$ is the flipping of an original matrix along its diagonal. Hence:

$$
\begin{bmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
\end{bmatrix}
=
\begin{bmatrix}
    a_{1,1} & a_{2,1} & a_{3,1} \\
    a_{1,2} & a_{2,2} & a_{3,2} \\
    a_{1,3} & a_{2,3} & a_{3,3}
\end{bmatrix}^T
$$

The <a href="{{ site.baseurl }}/Linear-Algebra-Determinants-I/#determinant"> determinant </a> of a matrix transpose has the same value.
$$
det||A|| = det || A^T||
$$
Hence there is equivalence among rows and columns of a determinant.

</div>

### Antisymmetry property

When columns of a determinant change the detminant changes signs. In the example below terms that were negative before became positive and vice versa.

__Normal__

$$
\begin{vmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
\end{vmatrix}
\begin{aligned}
= 
&a_{1,1}*a_{2,2}*a_{3,3} -a_{1,1}*a_{3,2}*a_{2,3} - a_{2,1}*a_{1,2}*a_{3,3} \\
&+ a_{2,1}*a_{3,2}*a_{1,3} + a_{3,1}*a_{1,2}*a_{2,3} - a_{3,1}*a_{2,2}*a_{1,3} 
\end{aligned}
$$

__Changed__

In this example one column is changed with another.

$$
\begin{vmatrix}
    a_{1,1} & a_{1,3} & a_{1,2} \\
    a_{2,1} & a_{2,3} & a_{2,2} \\
    a_{3,1} & a_{3,3} & a_{3,2}
\end{vmatrix}
\begin{aligned}
= 

&-a_{1,1}*a_{2,2}*a_{3,3} +a_{1,1}*a_{3,2}*a_{2,3} + a_{2,1}*a_{1,2}*a_{3,3} \\
&- a_{2,1}*a_{3,2}*a_{1,3} - a_{3,1}*a_{1,2}*a_{2,3} + a_{3,1}*a_{2,2}*a_{1,3} 
\end{aligned}
$$

### Determinantes with identical columns

If a column $j$ and $k$ ($j<k$) are interchanged, it requires $2m+1$ changes to make, while $m$ is the distance of the columns to each other. The sign of the determinant is defined by $2m+1$ being odd (negative) or even (positive).

_Determinantes with identical columns vanish ($D(A) = 0$)_

### Linear Property of Determinantes

<div class="theorem">
If all elements of the jth column of a determinant $D$ are "linear combinations" of two numbers:

$$
a_{i,j} = \lambda b_i+\mu c_i (i = 1, 2, ..., n)
$$

, where $\lambda$ and $\mu$ are fixed numbers, than $D$ is equal to a linear combination of determinantes.

$$
D = \lambda D_1 + \mu D_2
$$

Hence $D_1$ and $D_2$ re the same cols except for the jth column.

Can also be written as:

$$
D(\lambda b_i + \mu c_i) = \lambda D_j(b_i) + \mu D_j(c_i)
$$
</div>

$D_j(b_i) \sim$ determinant to be received, when the jth column is replaced with values of $b_i$

<div class="proof">
$$
D_j(\lambda b_i + \mu c_i) =
\begin{vmatrix}
    a_{1,1} & \lambda b_1 + \mu c_1 & a_{1,3} \\
    a_{2,1} & \lambda b_2 + \mu c_2 & a_{2,3} \\
    a_{3,1} & \lambda b_3 + \mu c_3 & a_{3,3}
\end{vmatrix}
$$
$$
\begin{aligned}
= 
&a_{1,1} * (\lambda b_2 + \mu c_2) * a_{3,3} - a_{1,1} * (\lambda b_3 + \mu c_3 ) * a_{2,3} \\
&-a_{2,1} * (\lambda b_1 + \mu c_1) * a_{3,3} + a_{2,1} * (\lambda b_3 + \mu c_3) * a_{1,3} \\
&-a_{3,1}*(\lambda b_2 + \mu c_2 )*a_{1,3} + a_{3,1}*(\lambda b_1 + \mu c_1 )*a_{2,3}
\end{aligned}
$$

Solving for one, applies for all:

$$
a_{1,1} * (\lambda b_2 + \mu c_2) * a_{3,3} = \lambda a_{1,1}* b_2 * a_{3,3} + \mu a_{1,1}*c_2 * a_{3,3}
$$

Hence for the first and thus also for the second determinante:
$$
\begin{aligned}
\lambda D_j(b_i)
=& \lambda(a_{1,1}*b_2*a_{3,3} -a_{1,1}*b_3*a_{2,3} - a_{2,1}*b_1*a_{3,3} \\
&+ a_{2,1}*b_3*a_{1,3} + a_{3,1}*b_1*a_{2,3} - a_{3,1}*b_2*a_{1,3}) 
\end{aligned}
$$

$$
\begin{aligned}
\mu D_j(c_i)
=& \mu(a_{1,1}*c_2*a_{3,3} -a_{1,1}*c_3*a_{2,3} - a_{2,1}*c_1*a_{3,3} \\
&+ a_{2,1}*c_3*a_{1,3} + a_{3,1}*c_1*a_{2,3} - a_{3,1}*c_2*a_{1,3}) 
\end{aligned}
$$

</div>
<br>

### Addition of another arbitrary column to another column

<div class="theorem" id="same-col-relation">
The value of a determinant is not changed by adding the elements of one column multiplied by an arbitrary number to the corresponding elements of another column

$$
a_{i,j} = a_{i,j} + \lambda a_{i,k}
$$
$$

D(a_j) = D(a_{i,j}) + \lambda D(a_{i,k})
$$

$D(a_{i,k})$ changes to zero, because to identical columns are present. Hence:

$$
D(a_{i,j} + \lambda a_{i,k}) = D(a_{i,j})
$$
</div>

## Cofactors and Minors

<div class="def" id="cofactor">
Cofactor

Suppose $a_{i,j}$ is an element of the jth column. Given a determinant of a matrix:

$$
D=\sum{(-1)^{N(\alpha_1, \alpha_2, ..., \alpha_n)}* a_{\alpha_1, 1} *a_{\alpha_2, 2}* ... * a_{\alpha_n, n}}
$$

We factor out all $a_{i,j}$, what remains is called the cofactor of $a_{i,j}$, denoted as $A_{i,j}$.
</div>

#### Example

$$
\begin{vmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
\end{vmatrix}
\begin{aligned}
= 
&a_{1,1}*a_{2,2}*a_{3,3} -a_{1,1}*a_{3,2}*a_{2,3} - a_{2,1}*a_{1,2}*a_{3,3} \\
&+ a_{2,1}*a_{3,2}*a_{1,3} + a_{3,1}*a_{1,2}*a_{2,3} - a_{3,1}*a_{2,2}*a_{1,3}
\end{aligned}
$$
$$
\begin{aligned}
&= a_{1,1}(a_{2,2}*a_{3,3} - a_{3,2}*a_{2,3}) + a_{2,1}(a_{3,2}*a_{1,3} - a_{1,2}*a_{3,3}) + a_{3,1}(a_{1,2}*a_{2,3} - a_{2,2}*a_{1,3}) \\
&= a_{1,1}A_{1,1} + a_{2,1}A_{2,1}+ a_{3,1}A_{3,1}
\end{aligned}
$$

<div class="theorem">
The sum of all elements, where a column or row is replaced with a cofactor of the corresponding row or column is equal to the original determinant of the respective matrix.

$$
a_{1, j}A_{1,j} + a_{2,j}A_{2,j}+ ... + a_{n,j}A_{n,j} = D
$$
</div>


With the definition of a [cofactor](#cofactor) we can determine determinantes, before we do we need to make some additional claims.

If we replace $a_{i,j}$ with any other element, and apply this to the entire column (or row) we would have identical columns (or rows) again and the determinant would vanish to zero, according to prior definitions.

<div class="theorem">
The determinant of a matrix over its columns (or row) $k$ with cofactors of a column (or row) $j$ is zero.

$$
a_{1, k}A_{1,j} + a_{2,k}A_{2,j}+ ... + a_{n,k}A_{n,j} = 0
$$
</div>


<div class="def" id="minor">
Minor

If we delete a column $j$ and a row $i$ deleted of a Matrix $A$ and calculate the detminant of thiss matrix, we get the Minor $M_{i,j}$ of a original Matrix $A$.
</div>

<div class="theorem" id="minor-cofactor">
For a minor the following relation holds:

$$
A_{i,j} = (-1)^{i+j}M_{i,j}
$$
</div>

<div class="proof">
$$
\begin{vmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
\end{vmatrix}
= a_{1,1}A_{1,1} + a_{2,1}A_{2,1}+ a_{3,1}A_{3,1}
$$
$$
A_{1,1} = a_{2,2}*a_{3,3} - a_{3,2}*a_{2,3} = M_{1,1}
$$

As you can see this corresponds to the definition of a [Minor](#minor).

It also applies for any other element within the matrix A. We would move any element in the matrix to the upper left corner in $i=1, j=1$. Every interchange would cause a change in sign of the determinant to change, according to the antisymmetrie propery. Therefore, the sign of the minor is determined by the number of interchanges.

</div>
<br>
![minor]({{ site.baseurl }}/images/minor.png)

#### Examples

1. 
    A third order determinant can be decomposed into:

    $$
    \begin{vmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
    \end{vmatrix} = a_{1,1}
    \begin{vmatrix}
    a_{2,2} & a_{2,3} \\
    a_{3,2} & a_{3,3}
    \end{vmatrix}
    - a_{1,2}
    \begin{vmatrix}
    a_{2,1} & a_{2,3} \\
    a_{3,1} & a_{3,3}
    \end{vmatrix}
    + a_{1,3}
    \begin{vmatrix}
    a_{2,1} & a_{2,2} \\
    a_{3,1} & a_{3,2}
    \end{vmatrix}
    $$

2. Triangular Matrix

    $$
    \begin{aligned}
    D &=
    \begin{vmatrix}
    a_{1,1} & 0 & 0 \\
    a_{2,1} & a_{2,2} & 0 \\
    a_{3,1} & a_{3,2} & a_{3,3}
    \end{vmatrix} \\
    &= a_{1,1}
    \begin{vmatrix}
    a_{2,2} & 0 \\
    a_{3,2} & a_{3,3}
    \end{vmatrix}
    - 0 * 
    \begin{vmatrix}
    a_{2,1} & 0 \\
    a_{3,1} & a_{3,3}
    \end{vmatrix}
    + 0 *
    \begin{vmatrix}
    a_{2,1} & 0 \\
    a_{3,1} & a_{3,2}
    \end{vmatrix} \\
    &=
    a_{1,1}D_{n-1} \\
    &= a_{1,1}*a_{2,2}*a_{3,3}
    \end{aligned}
    $$

3. Vandermonde Determinant

    $$
    W(x_1, x_2, ..., x_n) = 
    \begin{vmatrix}
    1 & 1 & ... & 1 \\
    x_1 & x_2 & ... & x_n \\
    x_1 & x_2^2 & ... & x_n^2 \\
    ... & ... & ... & ... \\
    x_1^{n-1} & x_2^{n-1} & ... & x_n^{n-1}
    \end{vmatrix} 
    $$

    The determinant can be defined by seeing $W(x_1, x_2, ..., x_n)$ as a polynomial. In that case, if we manage to find a root of the polynomial, we can describe it by multiplying it with $(x_i - root)$.
    This is also known as the [factor theorem](https://www.adelaide.edu.au/mathslearning/system/files/media/documents/2019-09/mt1-polynomials-book.pdf).

    __Example:__

    $$
    p(x) = x^3 +2x^2-3x-6
    $$

    $$
    p(x=-2) = 8 - 8 + 6 - 6 = 0
    $$

    We can write:

    $$
    p(x) = (x-2)(x^2 -3)
    $$
    
    Luckily $W(x_1, x_2, ..., x_n)$ is equal to zero, once we have identical columns or rows, according to <a href="#same-col-relation"> same column property </a>. Meaning $x_j - x_{\neg {j}}$ for $j = (1, 2,n)$ is a factor of $W$.

    Hence, 

    $$
    W(x_1, x_2, ..., x_n) = a(x_1, x_2, ..., x_{n-1})* \prod_{k=1}^{n-1}{(x_n-x_k)}
    $$

    Whereby $a(x_1, x_2, x_{n-1})$ is a polynomials itself, of order $n-1$. When you calculate it, you will see that it is actually $W(x_1, x_2, ..., x_{n-1})$
    Hence, because $W(x_1)=1$ it simplifies to:

    $$
    W(x_1, x_2, ..., x_n) = \prod_{1 \leq i < m \leq n }{x_m - x_i}
    $$


## Practical Evaluation of determinantes

The formula of cofactors:

$$
D = a_{1,j}A_{1,j} + a_{2,j}A_{2,j} + ... + a_{n,j}A_{n,j}
$$

takes a simpler form, if all elements except one in a column vanish. Then:

$$
D = a_{k,j}A_{k,j}
$$

The calculation of the determinant of order $n$ is than reduced to a calculation of a determinant of order $n-1$.
We can achieve this, by changing any row or column $j$ of a determinant by substracting or adding multiples of another row or column $k$ to to $j$. As we know from <a href="#same-col-relation"> same column property </a> this does not change the determinant. And in the end we can evaluate it according to the above formula.

#### Example

$$

D=
\begin{vmatrix}
-2 & 5 & 0 & -1 & 3 \\
1 & 0 & 3 & 7 & -2 \\
3 & -1 & 0 & 5 & -5 \\
2 & 6 & -4 & 1 & 2 \\
0 & -3 & -1 & 2 & 3
\end{vmatrix}

$$


## References

* https://www.adelaide.edu.au/mathslearning/system/files/media/documents/2019-09/mt1-polynomials-book.pdf
* https://cosmathclub.files.wordpress.com/2014/10/georgi-shilov-linear-algebra4.pdf

