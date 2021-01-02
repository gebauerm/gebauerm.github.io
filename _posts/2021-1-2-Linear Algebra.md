---
layout: post
title: Linear Algebra
---

This chapter is devoted to revising some basic linear algebra.

## Determinants

### Number Fields

$K$ is a number field, so to say a set of numbers, which follows the following aritmethic operations.

#### Addition and Substraction

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

#### Multiplication and Division

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


### Systems of Linear Equations

A system of linear equations can be seen here:

$$\begin{aligned}
a_{1,1} x_1 + a_{1,2}x_2 +  ... + a_{1, n}x_n = b_1 \\
a_{2,1} x_1 + a_{2,2}x_2 +  ... + a_{2, n}x_n = b_2 \\
... \\
a_{n,1} x_1 + a_{n,2}x_2 +  ... + a_{n, n}x_n = b_n
\end{aligned}$$

####  Terminoligy
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

### Determinate of Order n

Given a square matrix of order $n$, hence a matrix with $n^2$ numbers $a_{i,j}$ from $i,j = (1, 2, ..., n)$

$$\begin{bmatrix}
    a_{1,1} & a_{1,2} & ... & a_{1,n} \\
    a_{2,1} & a_{2,2} & ... & a_{2,n} \\
    ... & ... & ... & ... \\
    a_{n,1} & a_{n,2} & ... & a_{n,n}
\end{bmatrix}$$

The number of columns and rows is called order. The first index indicates the row the second one the column.

From here on we will start to define the determinant. Before stating the definition we need to make some assumptions.

#### Assumtpions

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