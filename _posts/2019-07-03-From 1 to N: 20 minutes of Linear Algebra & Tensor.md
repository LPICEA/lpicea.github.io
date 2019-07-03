---
layout: post
title: Introduction to Linear Algebra and More
tags: markdown

---

Linear algebra has been widely used in a variety of fields in mathematics and science. Starting from the simple questions of solving linear equations, the methods and ideas in linear algebra are also applied in some advanced topics of math, such as group representation theory and differential equations. Here in this article, I am trying to give a brief introduction to linear algebra and its basic application with simplest languages and hopefully least number of equations.

<!--more-->

Generally, linear algebra is the branch of mathematics to **deal with the elements in linear spaces - vectors and their transformations**.  If you want a minimum introduction, this sentence already covers 80% of the content. However, it is still hard for beginners to understand the terms "linear spaces" or "transformations". Do not worry, here comes the explanation.

First of all, linear algebra must be linear. This is a useful sentence without any information -- seemingly. The word "**linear**" itself indicates a set of properties in mathematics, which gives us the very basic ideas to start with. 

Linear, in our discussion of linear algebra, means that:

- the set has **addition** and **number product** operations defined on it. 
- in the content of a map $M$, linear means $nM(x)=M(nx)$ and $M(a+b)=M(a)+M(b)$

Leaving alone all strict definitions in mathematics, there are actually many examples of linear space.  A well-known example is the points on a plane(x,y), which can be represented as vectors $\vec{r}$. The set of all such vectors(forms the whole plane, of course) then gives us a vector space of dimension 2. Spaces with higher dimensions are hard to imagine, but can give higher-dimensional linear spaces in a similar way, and as a special case the members of dimension-1 linear space are just numbers or scalars Starting from vector spaces, we can add mathematics step by step, and finally build the whole framework called **tensor algebra** : the generalized version of linear algebra.

As mentioned above, linear algebra deals with **vectors** and their **transformations**. Since we have already known what vectors are, now it is the time to deal with transformations. A transformation is of course a mapping between two sets. A simplest case of transformations is the mapping between vectors:
$$
M(\vec r)=\vec{r_1}
$$
It can be proofed that, linear transformations between vectors are just the same thing as **matrices**. I will not show the details here, but this conclusion is useful when we generalize such transformations to higher orders. 

One thing to notice is that, the transform $M$ does not need to turn $\vec r$ into a vector with the same dimension. Thus, if a matrix transforms **n-dimensional** vectors to **m-dimensional** vectors, it is called a $m\times n$ matrix:
$$
\vec {r^1_m} =M_{m\times n} \ \vec{r^0_n}
$$
![g1033](https://raw.githubusercontent.com/LPICEA/lpicea.github.io/master/screenshots/g1033.png)

As a special case, one can also transform a vector into a scalar, which can be done with a $1\times n$ matrix, or **row vector**. Accordingly, the $n\times 1$ matrices then turn scalars into vectors, and are called **column vectors**. The $m\times n$ matrices can thus be regarded as $m$ **row vectors in a column**, or $n$ **column vectors in a row**.

![g1033](https://raw.githubusercontent.com/LPICEA/lpicea.github.io/master/screenshots/g1249.png)

Then, the generale rule of matrix product comes out: the product of two matrices is just like doing one transform after another. The resulting matrix of $M_{m\times n} P_{n\times q}$ is a new matrix $Z_{m\times q}$ . Note that:

- The $n$ must be same, or the two transform fail to link together.
- Just use the rows of $M$ to multiply columns of $P$

**Vectors** and **Matrices** take up all the discussions in ordinary linear algebra books, and most of these books will contain the following aspects of mathematical problems:

1. Finding the zero space of a transform $M$ : by solving $M \vec r =0$ (the kernel space)
2. Find a set of mutually orthogonal vectors based on some given vectors (Schmidt orthogonalization)
3. For a given set of vectors, what is the volume of the shape formed by them? (determinant)
4. For a given transformation, is there any vectors whose direction will not change under the transformation? (diagonalization)

Now, here comes the question: where can I **use** them if I know everything of such cool linear algebra? The answer is: almost **everything** as long as it is linear! 

Let's look at some examples:

- The zero space problem is the same as solving a set of linear equations, and conclusions related to this topic can be applied to differential equations if they are also linear.
- Determinant can be used to calculate areas and volumes, and its value is useful in the remaining types of problems.
- Diagonalization gives a set of vectors with constant directions under transformation. It is useful when doing with rotations, where we are looking for the axis of rotation. Diagonalization is almost the central part in solving quantum mechanics problems too. 

------

As it is told that matrices are transforms between vectors, a good students should always use matrices to deal with vectors, which means they can stop right here. 

However, we are quite bad ones and we **do not** follow the rules. We want to perform matrix $\times$ vectors in a different way:

![g1136](https://raw.githubusercontent.com/LPICEA/lpicea.github.io/master/screenshots/g1136.png)

Now, it seems that we are in trouble: what will the result be if we flip the order of multiply?

——Just take it easy. The basic rule of "rows times columns" still applies in this case. Here you may ask, how can I put the 1-element row and 2-element column together??

NO, you CAN NOT, at least if you still stick to matrices. However, if we ascend to higher orders, there comes the solution: multiply to each row and put the results together in the way the rows are ordered. Such approach is called "tensor product":

![g3846](https://raw.githubusercontent.com/LPICEA/lpicea.github.io/master/screenshots/g3846.png)

A 3-order tensor can be regarded as a 3-d grid of elements, and it has an algebraic meaning: just recall that 2-tensors or matrices are transformations between vectors, 3-tensors are thus transformations of matrices!

Following the rules of tensor products, we can further construct 4-tensors or even N-tensors. 

------

So far, everything about tensors just looks like an elegant game of math, but indeed we can find tensors in reality. There are objects in physics or other fields of science that do behave like matrices or tensors, which encourage us to express them as tensors though the linear space of tensors and vectors are in fact isomorphic.

If you have learned about physics of rotation, there is one strange thing: the moment of inertia. In college physics courses, the textbook will tell you that moment of inertia is neither a scalar nor a vector. For students whose major are not physics this is a quite confusing expression. Indeed moment of inertia is a 2-tensor, which gives the property of rotation with its rotating axis.

Another application of tensors lies in general relativity, where the curvature of space is expressed with tensors.

Recently, it has been reported that tensors can be used to simplify high-dimensional linear systems. The basic idea is: for a very-high dimensional vector of the system, it is possible to turn it into tensors since their spaces are isomorphic. Then, we can further simplify the system by hiding some of its elements with tensor product, and some properties of the system can be extracted after that.

---

Another interesting topic about linear algebra is: how does linear algebra link with other part of mathematics? 

One thing related to LA is the group theory. Matrices equipped matrix product operation can form a group, and reversely we can represent a finite group by mapping its elements to a set of matrices. Such representation of groups gives a algebraic correspondence to abstract math objects like groups. With the representation, it is also possible to study the groups with algebraic or geometric tools. Such content can be found in "group cohomology".
