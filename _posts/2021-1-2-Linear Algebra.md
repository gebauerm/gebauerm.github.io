---
layout: post
title: Linear Algebra - Determinantes
---

This chapter is part of a series that revisits some basic linear algebra.
In this chapter well summarize basic concepts revolving around determinantes.

## Number Fields

$K$ is a number field, so to say a set of numbers, which follows the following aritmethic operations.

### Addition and Substraction

1. Commutative

    $$
    \alpha + \beta = \beta + \alpha
    $$

2. Associative

    $$
    (\alpha + \beta) + \gamma = \alpha + ( \beta + \gamma)
    $$

3. Number Zero

    There exists a Number $0$ such that

    $$
    0 + \alpha = \alpha,
    $$

<p style="text-align: center;"> for every $\alpha$ in $K$ </p>

4. Negative Element

    For every $\alpha$ in $K$ there exists a negative element $\gamma$ such that:

    $$
    \alpha + \gamma = 0
    $$

The 4th rule enables us to carry out rules for substraction.

### Multiplication and Division

1. Commutative

    $$
    \alpha \beta = \beta \alpha
    $$

2. Associative

    $$
    (\alpha \beta ) \gamma = \alpha (\beta \gamma) 
    $$

3. Multiplication with 1

    $$
    1 * \alpha = \alpha
    $$

4. Reciprocal Element

    For every $\alpha  \neq 0$ there exists a number $\gamma$ in $K$ so that:

    $$
    \alpha \gamma = 1
    $$

5. Multiplication over Addition

    $$
    \alpha(\beta + \gamma) = \alpha \beta + \alpha \gamma
    $$

Operation of devision is carried out by the solvability of the 4th operation.

### Isomorphism

Two fields $K$ and $K'$ are isomorphic if, there is a one-to-one relation between both, such that every number and its product and sum is associated with the corresponding number and its product and sum. The same accounts for its differences or quotient.


## Systems of Linear Equations

A system of linear equations can be seen here:

$$\begin{aligned}
a_{1,1} x_1 + a_{1,2}x_2 +  ... + a_{1, n}x_n = b_1 \\
a_{2,1} x_1 + a_{2,2}x_2 +  ... + a_{2, n}x_n = b_2 \\
... \\
a_{n,1} x_1 + a_{n,2}x_2 +  ... + a_{n, n}x_n = b_n
\end{aligned}$$

###  Terminoligy
$a_{1,1}, a_{2, 1}, ... , a_{n,n}$ - coefficient from $K$

$x_1, x_2, ... , x_n$ - Unknown elements, to be determined from $K$

$b_1, b_2, b_n$ - constant terms from $K$

__Goal:__ Search for $c_i$ in $K$ to replace $x_i$, that all equations are turned into identities ($b_1 = b_1$).

Some systems may not have a solution at all. For example:

$$\begin{aligned}
2x_1 + 3x_2 = 5 \\
2x_1 + 3x_2 = 6
\end{aligned}$$

These systems are called incompatible. Compatible systems have at least one solution. Compatible systems with multiple solutions are called indeterminate. An Example is this one:

$$\begin{aligned}
2x_1 + 3x_2 = 0 \\
4x_1 + 6x_2 = 6
\end{aligned}$$

<p style="text-align: center;">  $
x_1^{(1)} = 0, x_2^{(1)} = 0, x_1^{(2)} = 3, x_2^{(2)} = -2
$ </p>


The solutions are marked with a subscript in paranthesis.

Systems with only one solution are called determinate.
When studying these systems some basic problems arise, which need to be tackled. We want to know at first, if a system has at least one solution at all. When it has at least one, we want to know, whether that solution is the only one. If not we want to find out all solutions possible. If it has only one solution, we want to find out only that single one. A summary can be seen in the graph below.

![linear_algebra_problems]({{ site.baseurl }}/images/linear_algeb_problems.png)

A basic mathmatical tool for studying these problems is the determinate. It helps us solving these problems.

## Determinate of Order n

Given a square matrix of order $n$, hence a matrix with $n^2$ numbers $a_{i,j}$ from $i,j = (1, 2, ..., n)$

$$\begin{bmatrix}
    a_{1,1} & a_{1,2} & ... & a_{1,n} \\
    a_{2,1} & a_{2,2} & ... & a_{2,n} \\
    ... & ... & ... & ... \\
    a_{n,1} & a_{n,2} & ... & a_{n,n}
\end{bmatrix}$$

The number of columns and rows is called order. The first index indicates the row the second one the column.

From here on we will start to define the determinant. Before stating the definition we need to make some assumptions.

### Assumtpions

* We take the product of every element, but every factor in the product needs to be an element from a different row and column from the matrix.

* We take elements in an ascending order of columns, to reduce complexity.

* We define the product as such:
   
    $ a_{\alpha_1, 1} * a_{\alpha_2, 2} * ... * a_{\alpha_n, n}$

* $\alpha$ represents different rows and can appear in different permutations of $1, 2, ..., n$

* To order all $\alpha_i$ in an ascending order, we perform inversions. E.g. with $\alpha_1 = 2, \alpha_2=1, \alpha_3=3$ we would write $N(2, 1, 3) = 1$, meaning that this sequence needs one inversion to be ordered in an ascending order.

Now we can define the Determinant.
<dl>
<dt>Determinant</dt>
<dd>The determinant $D$ of the matrix (10) is:

$$
D=\sum{(-1)^{N(\alpha_1, \alpha_2, ..., \alpha_n)}* a_{\alpha_1, 1} *a_{\alpha_2, 2}* ... * a_{\alpha_n, n}}
$$

$$
D=
\begin{vmatrix}
    a_{1,1} & a_{1,2} & ... & a_{1,n} \\
    a_{2,1} & a_{2,2} & ... & a_{2,n} \\
    ... & ... & ... & ... \\
    a_{n,1} & a_{n,2} & ... & a_{n,n}
\end{vmatrix} = det ||a_{i,j} ||
$$
</dd>
</dl>

#### Example

$$
\begin{vmatrix}
    a_{1,1} & a_{1,2} & a_{1,3} \\
    a_{2,1} & a_{2,2} & a_{2,3} \\
    a_{3,1} & a_{3,2} & a_{3,3}
\end{vmatrix}= 
$$

$$
\begin{aligned}

&(-1)^{N(1,2,3)}*a_{1,1}*a_{2,2}*a_{3,3} + (-1)^{N(1,3,2)}*a_{1,1}*a_{3,2}*a_{2,3} +\\
&(-1)^{N(2,1,3)}*a_{2,1}*a_{1,2}*a_{3,3} + (-1)^{N(2,3,1)}*a_{2,1}*a_{3,2}*a_{1,3} +\\
&(-1)^{N(3,1,2)}*a_{3,1}*a_{1,2}*a_{2,3} + (-1)^{N(3,2,1)}*a_{3,1}*a_{2,2}*a_{1,3} 
\end{aligned}
$$

<p style="text-align: center;">
$=$
</p>

$$
\begin{aligned}
&a_{1,1}*a_{2,2}*a_{3,3} -a_{1,1}*a_{3,2}*a_{2,3} - a_{2,1}*a_{1,2}*a_{3,3} \\
&+ a_{2,1}*a_{3,2}*a_{1,3} + a_{3,1}*a_{1,2}*a_{2,3} - a_{3,1}*a_{2,2}*a_{1,3} 
\end{aligned}
$$

### Role of Determinantes to solve linear equations

The following linear equations can be used to illustrate how finding their solution is tied to the determinant.

$$
\begin{aligned}
a_{1,1}x_1 + a_{1,2}x_2 = b_1
a_{2,1}x_1 + a_{2,2}x_2 = b_2
\end{aligned}
$$

$$
x_1=\frac{b_1a_{2,2} - b_2a_{1,2}}{a_{1,1}a_{2,2} - a_{2,1}a_{1,2}},
x_2=\frac{b_2a_{1,1} - b_1a_{2,1}}{a_{1,1}a_{2,2} - a_{2,1}a_{1,2}}
$$

This can be represented as second order determinates.

$$
\begin{aligned}
a_{1,1}a_{2,2} - a_{2,1}a_{1,2} &=
\begin{vmatrix}
a_{1,1} & a _{1,2} \\
a_{2,1} & a_{2,2}
\end{vmatrix}
\\
\\
b_1a_{2,2} - b_2a_{1,2} &=
\begin{vmatrix}
b_1 & a _{1,2} \\
b_2 & a_{2,2}
\end{vmatrix}
\\
\\
a_{1,1}b_2 - a_{2,1}b_1 &=
\begin{vmatrix}
a_{1,1} & b_1 \\
a_{2,1} & b_2
\end{vmatrix}
\end{aligned}
$$

### Determining the sign of the Determinant

The sign of a term within the determinant can be defined by a simple rule.
Elements of the product can be connected via a line within the matrix. This line has a slope. If the left element is lower than the right element, it has a negative slope. If the left element is higher than the right element, than it has a positive slope. This term shall not be confused with the slope of a function or similar expressions.
For every product, only egative slopes shall be defined within the matrix. If the
number of lines is odd - than the sign before the term is a minus, if the amount of negative slopes is event, the factor of the product within the determinant has a positive sign.


For $a_{2,1} * a_{1,2} * a_{3,3}$ we have a __negative__ sign because there is one negative slope:

![first_example]({{ site.baseurl }}/images/slope_negative_determinant_2.png)

For $a_{3,1} * a_{1,2} * a_{2,3}$ the sign is __positive__ because of two negative slopes:

![first_example]({{ site.baseurl }}/images/slope_negative_determinant.png)


## Properties of Determinantes

### Transpose

A Transpose of a matrix can be defined as the following.

<dl>
<dt> Transpose </dt>
<dd> A matrix $A$ transpose $A^T$ is the flipping of an original matrix along its diagonal. Hence:

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

The determinant of a matrix transpose has the same value.
$$
det||A|| = det || A^T||
$$
Hence there is equivalence among rows and columns of a determinant.

</dd>
</dl>

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

<div class="theorem">
The value of a determinant is not chanhed by adding the elements of one column multiplied by an arbitrary number to the corresponding elements of another column

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

<dl> 
<dt>Cofactor</dt>
<dd>
Suppose $a_{i,j}$ is an element of the jth column. Given a determinant of a matrix:

$$
D=\sum{(-1)^{N(\alpha_1, \alpha_2, ..., \alpha_n)}* a_{\alpha_1, 1} *a_{\alpha_2, 2}* ... * a_{\alpha_n, n}}
$$

We factor out all $a_{i,j}$, what remains is called the cofactor of $a_{i,j}$, denoted as $A_{i,j}$.
</dd>
</dl>
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


With the definition of a cofactor we can determine determinantes, before we do we need to make some additional claims.

If we replace $a_{i,j}$ with any other element, and apply this to the entire column (or row) we would have identical columns (or rows) again and the determinant would vanish to zero, according to prior definitions.

<div class="theorem">
The determinant of a matrix over its columns (or row) $k$ with cofactors of a column (or row) $j$ is zero.

$$
a_{1, k}A_{1,j} + a_{2,k}A_{2,j}+ ... + a_{n,k}A_{n,j} = 0
$$
</div>


<dl>
<dt>Minor</dt>
<dd>
If we delete a column $j$ and a row $i$ deleted of a Matrix $A$ and calculate the detminant of thiss matrix, we get the Minor $M_{i,j}$ of a original Matrix $A$.
</dd>
</dl>

<div class="theorem">
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

As you can see this corresponds to the definition of a Minor.

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
    
    Luckily $W(x_1, x_2, ..., x_n)$ is equal to zero, once we have identical columns or rows, according to the properties of determinants. Meaning $x_j - x_{\neg {j}}$ for $j = (1, 2,n)$ is a factor of $W$.

    Hence, 

    $$
    W(x_1, x_2, ..., x_n) = a(x_1, x_2, ..., x_{n-1})* \prod_{k=1}^{n-1}{(x_n-x_k)}
    $$

    Whereby $a(x_1, x_2, x_{n-1})$ is a polynomials itself, of order $n-1$. When you divide it by $(x_n - root)$, you will see that it is actually $W(x_1, x_2, ..., x_{n-1})$
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
We can achieve this, by changing any row or column $j$ of a determinant by substracting or adding multiples of another row or column $k$ to to $j$. As we know from previous definition this does not change the determinant. And in the end we can evaluate it according to the above formula.

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

https://www.adelaide.edu.au/mathslearning/system/files/media/documents/2019-09/mt1-polynomials-book.pdf