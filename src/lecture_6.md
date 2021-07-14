# Lecture 6

### Continuous Random Variables

<div class="def">

**Continuous Random Variable**: *A random variable \\(X\\) is called **continuous** if its porbability law can be described in terms of a nonnegative function \\(f_X\\), called the **probability density function** of \\(X\\), or **PDF** for short.*
</div>

A PDF satisfies
\\[
    P(X \in B) = \int_B {f_X(x)}dx
\\]

for every subset \\(B\\) of the real line. In particular, the probability that the value of \\(X\\) falls within an interval is
\\[
    P(a \leq X \leq b) = \int_a^b{f_X(x)}dx
\\]

Note:
\\[
    P(a \leq X \leq b) = P(a < X < b) = P(a \leq X < b) = P(a < X \leq b)
\\]
<div class="idea">

**Big Idea**: *The probability at an individual point on a continuous distribution is 0, so the equality of \\(a\\) or \\(b\\) is unimportant.*
</div>


Note that to qualify as a PDF, a function \\(f_X\\) must be nonnegative, i.e. \\(f_X(x) \geq 0\\) for every \\(x\\), and mus talso satisfy the normalization equation
\\[
    \int_{-\infty}^\infty{f_X(x)}dx = P(-\infty < X < \infty) = 1
\\]

### Continuous Uniform Random Variable

Consider a random variable \\(X\\) that takes values in an interval \\([a, b]\\) and assume that all subintervals of the same length are equally likely. We refer to this type of random variable as uniform or uniformly distributed. Its PDF has the form
\\[
    f_X(x) =
    \\begin{cases}
        c \text{ if } a \leq x \leq b\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

This means that we can calculate the value of c via the following:
\\[
    1 = \int_a^b{c}dx = c\int_a^b{dx} = c(b-a)
\\]
In other words,
\\[
    c = \frac{1}{b-a}
\\]

### Piecewise Constant PDF

<div class="ex">
<details>
<summary>
<strong>Example:</strong> Alvin's driving time to work is between 15 and 20 minutes if the day is sunny, and between 20 and 25 minutes if the day is rainy, with all times being equally likely in each case.

Assume that a day is sunny with probability \\(\tfrac{2}{3}\\) and rainy with probability \\(\tfrac{1}{3}\\).

What is the PDF of the driving time viewed as a random variable \\(X\\)?
</summary>

We interpret the statement that "all times are equally likely" in the sunny and rainy cases to mean that the PDF of \\(X\\) is constant in each of the intervals \\([15, 20]\\) and \\([20, 25]\\).

Furthermore, since these two intervals contain all possible driving times, the PDF should be zero everywhere else.

\\[
    f_X(x) =
    \\begin{cases}
        c_1 \text{ if } 15 \leq x \leq 20\\\\
        c_2 \text{ if } 20 \leq x \leq 25\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

where \\(c_1, c_2\\) are some constants.

We can determine these constants by using the probabilities of a sunny and of a rainy day.

\\[
    \\begin{align}
        \frac{2}{3} &= P(\text{sunny day}) = \int_{15}^{20}{f_X(x)}dx = \int_{15}^{20}{c_1}dx = 5c_1\\\\
        \frac{1}{3} &= P(\text{rainy day}) = \int_{20}^{25}{f_X(x)}dx = \int_{20}^{25}{c_2}dx = 5c_2\\\\ 
    \\end{align}
\\]

So that
\\[
    c_1 = \frac{2}{15}\quad c_2 = \frac{1}{15}
\\]


</details>
</div>

### A PDF can be arbitrarily large

Consider a random variable \\(X\\) with PDF
\\[
    f_X(x) = 
    \\begin{cases}
        \tfrac{1}{2\sqrt{x}} \text{ if } 0 < x \leq 1\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

Even though \\(f_X(x)\\) becomes infinitely large as \\(x\\) approaches zero, this is still a valid PDF because
\\[
    \int_{-\infty}^\infty{f_X(x)}dx = \int_0^1{\frac{1}{2\sqrt{x}}}dx = \sqrt{x}\Big|_0^1 = 1
\\]

### Summary of PDF Properties

Let \\(X\\) be a CRV with PDF \\(f_X\\).
\\[
    \\begin{gather}
        f_X(x) \geq 0 \text{ for all } x\\\\\\\\
        \int_{-\infty}^\infty{f_X(x)}dx = 1\\\\\\\\
        \text{If } \delta \text{ is very small, then } P(|x, x+\delta|) \approx f_X(x) \cdot \delta\\\\\\\\
        \text{For any subset } B \text{ of the real line, } P(X \in B) = \int_B{f_X(x)}dx
    \\end{gather}
\\]

### Expectation

The **expected value** or **mean** of a CRV \\(X\\) is defined by
\\[
    E[X] = \int_{-\infty}^\infty{xf_X(x)}dx
\\]
We also have
\\[
    E[g(X)] = \int_{-\infty}^\infty{g(x)f_X(x)}dx
\\]
The variance of \\(X\\) is defined by
\\[
    \text{var}(X) = E[(X - E[X])^2] = \int_{-\infty}^\infty{(X - E[X])^2f_X(x)}dx
\\]
We have
\\[
    0 \leq \text{var}(X) = E[x^2] - (E[X])^2
\\]
If \\(Y=ax+b\\) where \\(a\\) and \\(b\\) are given scalars, then
\\[
    E[Y] = aE[X] + b \quad \text{var}(Y) = a^2\text{var}(X)
\\]

### Cumulative Distribution Functions

The CDF of a random variable \\(X\\) is denoted by \\(F_X\\) and provides the probability \\(P(X \leq x)\\). In particular, for every \\(x\\) we have

\\[
    F_X(x) = P(X \leq x) = 
    \\begin{cases}
        \sum_{k \leq x}{p_X(k)} \text{ if } X \text{ discrete}\\\\\\\\
        \int_{-\infty}^x{f_X(t)}dt \text{ if } X \text{ continuous}
    \\end{cases}
\\]

### CDF Properties

The CDF \\(F_X\\) of a random variable \\(X\\) is defined by
\\[
    F_X(x) = P(X \leq x) \text{ for all x}
\\]
* \\(F_X\\) is monotonically nondecreasing: if \\(x \leq y\\), then \\(F_X(x) \leq F_X(y)\\)

* \\(F_X(x)\\) tends to 0 as \\(x \to -\infty\\), and to 1 as \\(x \to \infty\\).

* If \\(X\\) is discrete, then \\(F_X\\) has a piecewise constant and staircase-like form.

* If \\(X\\) is continuous, then \\(F_X\\) has a continuously increasing form.

* If \\(X\\) is discrete and takes integer values, the PMF and the CDF can be obtained from each other by summing or differencing:
\\[
    \\begin{gather}
        F_X(k) = \sum_{t=-\infty}^{k}{p_X(i)}\\\\\\\\
        p_X(k) = P(X \leq k) - P(X \leq k-1) = F_X(k) - F_X(k-1)
    \\end{gather}
\\]
for all integers \\(k\\).

### Conditional PDF and Expectation

The conditional PDF \\(f_{X|A}\\) of a continuous random variable \\(X\\) given an event \\(A\\) with \\(P(A) > 0\\) satisfies
\\[
    P(X \in B|A) = \int_{B}{f_{X|A}(x)}dx
\\]

If \\(A\\) is a subset of the real line with \\(P(X \in A) > 0\\), then
\\[
    P(X \in B|X \in A) = \frac{P(X \in B \cap X \in A)}{P(X \in A)} = \frac{\int_{A \cap B}{f_X(x)}dx}{P(X \in A )}
\\]

The resulting formula is
\\[
    f_{X|A}(x) = 
    \\begin{cases}
        \frac{f_X(x)}{P(X \in A)} \text{ if } x \in A\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

and
\\[
    P(X \in B|X \in A) = \int_{B}{f_{X|A}(x)}dx
\\]

for any set \\(B\\).

The corresponding conditional expectation is defined by
\\[
    E[X|A] = \int_{-\infty}^\infty{xf_{X|A}(x)}dx
\\]

The expected value rule remains valid:
\\[
    E[g(X)|A] = \int_{-\infty}^\infty{g(x)f_{X|A}(x)}dx
\\]

If \\(A_1, A_2, \dots, A_n\\) are disjoint events with \\(P(A_i) > 0\\) for each \\(i\\) that form a partition of the sample space, then
\\[
    f_X(x) = \sum_{i=1}^{n}P(A_i)f_X|A(x)
\\]

Law of total expectation:
\\[
    \\begin{align}
        E[X] &= \sum_{i=1}^{n}{P(A_i)E[X|A_i]}\\\\
        E[g(X)] &= \sum_{i=1}^{n}{P(A_i)E[g(X)|A_i]}
    \\end{align}
\\]

### Multiple Continuous Random Variables

Two continuous random variables associated with a common experiment are jointly continuous and can be described in terms of a joint PDF \\(f_{X,Y}\\) if \\(f_{X,Y}\\) is a nonnegative function that satisfies
\\[
    P((X, Y) \in B) = \int_{(x, y) \in B}{\int{f_{X,Y}(x, y)}dx}dy
\\]

For every subset \\(B\\) of the two-dimensional plane.

If \\(B\\) is a rectangle of the form \\(B = [a, b] \times [c, d]\\), we have
\\[
    P(a \leq X \leq b, c \leq Y \leq d) = \int_{c}^{d}{\int_{a}^{b}{f_{X,Y}(x, y)}dx}dy
\\]

We have the normalization property
\\[
    \int_{-\infty}^\infty{\int_{-\infty}^\infty{f_{X,Y}(x, y)}dx}dy = 1
\\]

### Marginal Distributions

Given the joint random variable \\(f_{x, y}(x, y)\\), the marginals are:
\\[
    \\begin{align}
        f_X(x) = \int_{-\infty}^\infty{f_{X,Y}(x, y)}dy\\\\
        f_Y(y) = \int_{-\infty}^\infty{f_{X,Y}(x, y)}dx\\\\
    \\end{align}
\\]

Given the joint random variables of three variables \\(f_{X,Y,Z}(x, y, z)\\), the marginals are:
\\[
    \\begin{align}
        f_X(x) = \int_{-\infty}^\infty{\int_{-\infty}^\infty{f_{X,Y,Z}(x,y,z)}dy}dz\\\\
        f_Y(y) = \int_{-\infty}^\infty{\int_{-\infty}^\infty{f_{X,Y,Z}(x,y,z)}dx}dz\\\\
        f_Z(z) = \int_{-\infty}^\infty{\int_{-\infty}^\infty{f_{X,Y,Z}(x,y,z)}dx}dy\\\\
    \\end{align}
\\]

### Expectation

If \\(X\\) and \\(Y\\) are jointly continuous random variables, and \\(g\\) is some function, then \\(Z = g(X, Y\\) is also a random variable.
\\[
    E[g(X, Y)] = \int_{-\infty}^\infty{\int_{-\infty}^\infty{g(x,y)f_{X,Y}(x,y)}dx}dy
\\]

As an important special case, for any scalars \\(a, b\\), we have
\\[
    E[aX + bY] = aE[X] + bE[Y]
\\]

### Conditioning

Let \\(X\\) and \\(Y\\) be continuous random variables with joint PDF \\(f_{X,Y}\\). For any fixed \\(y\\) with \\(f_Y(y) > 0\\), the conditional PDF of \\(X\\) given that \\(Y=y\\) is defined by
\\[
    f_{X|Y}(x|y) = \frac{f_{X|Y}(x|y)}{f_Y(y)}
\\]

The variable \\(y\\) is usually a fixed number and \\(f_{X|Y}(x|y)\\) is a function of the single variable \\(x\\).

Note:
\\[
    \int_{-\infty}^\infty{f_{X|Y}(x|y)}dx = 1
\\]

So for any fixed \\(y\\), \\(f_{X|Y}(x|y)\\) is a legitimate PDF.

Conditional Expectation:
\\[
    \\begin{align}
        E[X|Y = y] &= \int_{-\infty}^\infty{xf_{X|Y}(x|y)}dx\\\\
        E[g(X)|Y=y] &= \int_{-\infty}^\infty{g(x)f_{X|Y}(x|y)}dx
    \\end{align}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong>

Let \\(X\\) be exponentially distributed with mean 1. Once we observe the experimental value \\(x\\) of \\(X\\), we generate a normal random variable \\(Y\\) with zero mean and variance \\(x+1\\). What is the joint PDF of \\(X\\) and \\(Y\\)?
</summary>
We have:

\\[
    f_X(x) = e^{-x} \text{ for } x \geq 0 \text{ and } f_{Y|X}(y|x) = \frac{1}{\sqrt{2\pi(x+1)}}e^\frac{{-y^2}}{2(x+1)}
\\]

The joint distribution is
\\[
    f_{X,Y}(x,y) = f_X(x)f_{Y|X}(y|x) = e^{-x}\frac{1}{\sqrt{2\pi(x+1)}}e^\frac{{-y^2}}{2(x+1)}
\\]
for all \\(x \geq 0\\) and all \\(y\\).

</details>
</div>

### Discrete Uniform Random Variable

In many situations, we have a model of an underlying but unobserved phenomenon represented by a random variable \\(X\\) with PDF \\(f_X\\), and we make noisy measurements \\(Y\\) which is \\(f_{Y|X}\\).

Once the experimental value of \\(Y\\) is measured, what information does this provide on the unknown value of \\(X\\)?

Recall that when we used Bayes' rule for discrete distributions, we can go in both directions.

\\[
    f_Xf_{Y|X} = f_{X,Y} = f_Yf_{X|Y}
\\]

We have the expression
\\[
    f_Xf_{Y|X} = \frac{f_X(x)f_{Y|X}(y|x)}{\int_{-\infty}^\infty{f_X(t)f_{Y|X}(y|t)}dt}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong>

A lightbulb is known to have an exponentially distributed lifetime \\(Y\\). However, the company has been experiencing quality control problems. On any given day, the parameter \\(\lambda\\) of the PDF of \\(Y\\) is actually a random variable, uniformly distributed in the interval \\([1, \tfrac{3}{2}]\\). We test a lightbulb and record the experimental value \\(y\\) of its lifetime. What can we say about the underlying parameter \\(\lambda\\)?
</summary>

We model the parameter \\(\lambda\\) as a uniform random variable \\(\Lambda\\) with PDF:
\\[
    f_\Lambda(\lambda) = 2 \text{ for } 1 \leq \lambda \leq \tfrac{3}{2}
\\]
All available information about \\(\Lambda\\) is contained int he conditional PDF \\(f_{\Lambda|Y}(\lambda|y)\\), which is given by:

\\[
    f_{\Lambda|Y}(\lambda|y) = \frac{2\lambda e^{-\lambda y}}{\int_{1}^{\frac{3}{2}}{2te^{-ty}}}dt \text{ for } 1 \leq \lambda \leq \frac{3}{2}
\\]


</details>
</div>
