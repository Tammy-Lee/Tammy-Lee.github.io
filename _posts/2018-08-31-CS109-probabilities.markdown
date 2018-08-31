# A First Course in Probability

# Table of Content

[TOC]

# Chapter 1-Combinatorial analysis

> The mathematical theory of counting formally known as combinatorial analysis.

计数的数学理论正式叫法为组合分析。

（"黑板上排列组合，你舍得解开吗？"，就是这个组合）

## The Basic Principle of Counting

> Suppose that two experiments are to be performed. Then if experiment 1 can result in any one of m possible coutcomes and if, for each outcome of experiment 1, there are n possible outcomes of experiment 2, then together there are mn possible outcomes of the two experimens.

假设进行两个实验，如果实验1有m种可能的结果，对于实验1的每种结果，实验2都有n种可能的结果，那么，两个实验一共有mn种可能的结果。

## The generalized basic principle of counting

> If $$r$$ experiments that are to be performed are such that the first one may result in any of $$n_1$$ possible outcomes; and if, for each of these $$n_1$$ possible outcomes, there are $$n_2$$ possible outcomes of the second experiment; and if, for each of the possible outcomes of the first two experiments, there are $$n_3$$ possible outcomes of the third experiment; and if ..., then there is a total of $$n_1 · n_2 ··· n_r $$ possible outcomes of the r experiments.

如果要进行$$r$$个实验，第一个实验有$$n_1$$个可能结果；对于这$$n_1$$个中的每一个可能结果，第二个实验有$$n_2$$个可能结果；对于前两个实验的每一种可能结果，第三个实验有$$n_3$$个可能结果，以此类推，$$r$$个实验总共有 $$n_1 · n_2 ··· n_r $$ 个可能结果。

## Permutations

（"黑板上排列组合，你舍得解开吗？"，就是这个排列）

> Suppose we have $$n$$ objects. There are $$n(n-1)(n-2)	···3·2·1 = n!$$  different permutations of the n objects.

假设有$$n$$个物品，那么它们有$$n!$$种不同的排列方式。$$n_!$$读作n factorial，其中，$$0! = 1$$

> There are 
> $$
> \frac{n_!}{n_1!n_2!···n_r!}
> $$
> different permutations of $$n$$ objects, of which $$n_1$$ are alike, $$n_2$$ are alike, ... , $$n_r$$ are alike.

这里的alike应该是指这些不区分这些结果。比如说排列PEPPER六个字母，三个P，两个E都是alike的，那么所有的排列结果中，都会有重复。以排列成PEPPER这种，就有12个重复结果，而六个字母如果视作不同的六个，则有6！种结果，最后，共有$$\frac{6!}{3!2!}$$种结果。

## Combinations

（"黑板上排列组合，你舍得解开吗？"，就是这个组合）

> In general, as $$n(n-1)···(n-r+1)$$ represents the number of different ways that a group of $$r$$ items could be selected from $$r$$ items when the order of selection is relevant, and as each group of $$r$$ items will be counted in this count, it follows that the number of different groups of $$r$$ items that could be formed from a set of $$n$$ items is 
> $$
> \frac{n(n-1)···(n-r+1)}{r!} = \frac{n!}{(n-r)!r!}
> $$
>

从$$n$$ 个物品中一次性抽取$$r$$个的可能组合的数量。组合不需要排列，所以要把组合之间的排列去除掉。

### Notation and terminology

> we define $$\binom{n}{r}$$ , for $$r \leqslant n$$, by
> $$
> \binom{n}{r} = \frac{n!}{(n-r)!r!}(Equation 1.1)
> $$
> and say that $$\binom{n}{r}$$ (read as " $$n$$ choose $$r$$") represents the number of possible combinations of $$n$$ objects taken $$r$$ at a time.

组合还可以用另外一个公式
$$
\binom{n}{r} = \binom{n-1}{r-1} + \binom{n-1}{r} ,  1  \leq r \leq n (Equation 1.2)
$$
怎么解释呢？从$$n$$个物品里拿出$$r$$个，$$n$$个物品中有一个记为$$object1$$，包不包含$$object1$$把抽取办法分成了两部分，把$$\binom{n-1}{r-1}$$当作从除了$$object1$$中的$$n-1$$个物品中抽取$$r-1$$个，第$$r$$个就是$$object1$$，因此这种抽法中包含了$$object1$$，而抽取的$$r$$个中没有包含$$object1$$的数量就是$$\binom{n-1}{r}$$ 种。

### The binomial theorem

> The value $$\binom{n}{r}$$ are often referred to as binomial coefficients because of their prominence in the binomial theorem.

由于在二项式定理中的突出位置，$$\binom{n}{r}$$值也被称为二项式系数。
$$
（x + y）^n=\sum_{k=0}^{n} \binom{n}{k}x^ky^{n-k}(Equation1.3)
$$
下面是二项式定理的两种证明，第一种是数学推导，第二种基于组合角度。

#### Proof of the binomial theorem by induction（这个还没懂！）

当 $$n=1$$时，公式1.3可以写为：


$$
x+y=\binom{1}{0}x^0y^1+\binom{1}{1}x^1y^0=y+x
$$
当循环到$$n-1$$时，公式1.3为：
$$
\begin{aligned}(x+y)^n&=(x+y)(x+y)^{n-1}\\&=(x+y)\sum_{k=0}^{n-1}\binom{n-1}{k}x^ky^{n-1-k}\\&=\sum_{k=0}^{n-1}\binom{n-1}{k}x^{k+1}y^{n-1-k}+\sum_{n-1}^{k}\binom{n-1}{k}x^ky^{n-k}\end{aligned}
$$
令第一个sum中的$$i=k+1$$，第二个sum中的$$i=k$$，则有：
$$
\begin{aligned}(x+y)^n&=\sum_{i=1}^{n}\binom{n-1}{i-1}x^iy^{n-i}+\sum_{i=1}^{n-1}\binom{n-1}{i}x^iy^{n-i}\\ &=x^n+\sum_{i=1}^{n-1}[\binom{n-1}{i-1}+\binom{n-1}{i}]x^iy^{n-i}+y^n\\ &=x^n + \sum_{i=1}^{n-1}\binom{n}{i}x^iy^{n-i}+y^n\\ &=\sum_{i=0}^{n}\binom{n}{i}x^iy^{n-i}\end{aligned}
$$

#### Combinatiorial proof of the binomial theorem

以下式子的展开式一共有$$2^n$$项，因为每一个$$(x_i+y_i)$$都会和其他$$(n-1)$$项中的$$x，y$$相乘，所以有$$2·2^{n-1}=2^n$$项。比如
$$
(x_1+y_1)(x_2+y_2)=x_1x_2+x_1y_2+y_1x_2+y_1y_2
$$
在$$2^n$$项中有多少项和$$x^k,y^{n-k}$$有关呢？由于$$x$$的幂数是$$k$$，即和$$k$$个$$(x_i+y_i)$$相乘，这就相当于从$$n$$个结果里抽出$$k$$个结果。(这里可以看做选出$$k$$个组合，和其中的$$x$$相乘，没有挑选的组合中和剩下的$$y$$相乘)

因此有
$$
(x+y)^n=\sum_{k=0}^{n}\binom{n}{k}x^ky^{n-k}
$$

#### Example

How many subsets are there of a set consisting of $$n$$ elements?

这一问题的解决方案可以用上面的公式来解决
$$
\sum_{k=0}^{n}\binom{n}{k}=(1+1)^2=2^n
$$
如果是非空子集的话，结果为$$2^n-1$$

## Multinomial Coefficients



# Refrences

[markdown公式技巧](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

[Stanford CS109课程](https://web.stanford.edu/class/cs109/schedule.html)













