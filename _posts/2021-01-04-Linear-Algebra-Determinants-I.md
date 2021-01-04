---
layout: post
title: Linear Algebra - Determinantes I
---


This chapter is part of a series that revisits some basic linear algebra.
In this chapter well summarize basic concepts revolving around determinantes.

This chapter continues in: [Linear Algebra - Determinantes II]({{ site.baseurl }}/Linear-Algebra-Determinantes-II).


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

<div class="def" id="determinant">
Determinant
The determinant $D$ of the matrix (10) is:

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
</div>

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

The sign of a term within the [determinant](#determinant) can be defined by a simple rule.
Elements of the product can be connected via a line within the matrix. This line has a slope. If the left element is lower than the right element, it has a negative slope. If the left element is higher than the right element, than it has a positive slope. This term shall not be confused with the slope of a function or similar expressions.
For every product, only egative slopes shall be defined within the matrix. If the
number of lines is odd - than the sign before the term is a minus, if the amount of negative slopes is event, the factor of the product within the determinant has a positive sign.


For $a_{2,1} * a_{1,2} * a_{3,3}$ we have a __negative__ sign because there is one negative slope:

![first_example]({{ site.baseurl }}/images/slope_negative_determinant_2.png)

For $a_{3,1} * a_{1,2} * a_{2,3}$ the sign is __positive__ because of two negative slopes:

![first_example]({{ site.baseurl }}/images/slope_negative_determinant.png)


## References

* https://cosmathclub.files.wordpress.com/2014/10/georgi-shilov-linear-algebra4.pdf