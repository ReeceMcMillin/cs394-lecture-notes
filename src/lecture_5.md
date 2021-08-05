# Lecture 5 - Random Variables

### Random Variables

<div class="def">

*A random variable is a real-valued function of the outcome of an experiment.*
</div>

A function of a random variable defines another random variable.

We can associate with each random variable certain "averages" of interest, such as the mean and variance.

A random variable can be conditioned on an event or on another random variable.

There is a notion of independence of a random variable from an event or from another random variable.

### Discrete Random Variables

<div class="def">

*A random variable is called discrete if its range (the set of values that it can take) is either finite or countably infinite.*
</div>

A discrete random variable is a real-valued function of the outcome of an experiment that can take a finite or countably infinite number of values.

A discrete random variable has an associated probability mass function (PMF), which gives the probability of each numerical value that the random variable can take.

A function of a discrete random variable defines another discrete random variable, whose PMF can be obtained from the PMF of the original random variable.


### Probability Mass Functions
<div class="def">

*For a discrete random variable \\(X\\), we denote the PMF of \\(X\\) as \\(P_x\\).*
</div>

If \\(x\\) is any real number, the probability mass of \\(x\\), denoted \\(p_x(x)\\), is the probability of the event \\(\\{ X=x \\}\\) consisting of all outcomes that give rise to a value \\(X\\) equal to \\(x\\):
\\[
    p_x(x) = P(\\{ X = x \\})
\\]

For each possible value \\(x\\) of \\(X\\),
1. Collect all the possible outcomes that give rise to the event \\(\\{ X = x \\}\\).
2. Add their probabilities to obtain \\(p_x(x)\\).
3. Note that
\\[
    \sum_x{p_x(x)}=1
\\]
4. For any set \\(S\\) of possible values of \\(X\\), we have
\\[
    P(X \in S) = \sum_{x \in S}{p_x(x)}
\\]

For example, consider two tosses of a coin and let \\(X\\) be the number of heads.
\\[
    p_x(x) = 
        \begin{cases}
            \frac{1}{4} \text{ if } x \in \\{ 0, 2 \\}\\\\
            \frac{1}{2} \text{ if } x = 1\\\\
            0 \text{ otherwise}
        \end{cases}
\\]

If \\(X\\) is the number of heads obtained on two independent tosses of a fair coin, the probability of at least one head is
\\[
    P(X > 0) = \sum_{x=1}^{2}p_x(x) = \frac{1}{2}+\frac{1}{4}=\frac{3}{4}
\\]

### The Bernoulli Random Variable

Suppose that a trial/experiment has an outcome that can be classified as either a success or a failure.

Let \\(X\\) be \\(1\\) if the outcome is a success and let \\(X\\) be \\(0\\) if the outcome is a failure. The PMF is:
\\[
    \\begin{align}
        p(0) &= P[X=0]=1-p\\\\
        p(1) &= P[X=1]=p
    \\end{align}
\\]

### The Binomial Random Variable

Repeat the independent Bernoulli trials \\(n\\) times.

\\(X\\) is said to be binomial with parameters \\((n, p)\\).

The Bernoulli RV can be considered binomial \\((1, p)\\).

We use the binomial distribution to find \\(k\\) successes in \\(n\\) independent trials.

\\[
    p(k \text{ successes in } n \text{ trials}) = \binom{n}{k}p^k\left(1-p\right)^{n-k}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong> Flip a fair coin 10 times. What is the probability that 6 heads appear?
</summary>

\\[
    \\begin{align}
        p(6\text{ successes in } 10 \text{ trials}) &= \binom{10}{6}\left(\tfrac{1}{2}\right)^6\left(\tfrac{1}{2}\right)^4\\\\
        &=\binom{10}{6}\left(\tfrac{1}{2}\right)^{10}
    \\end{align}
\\]
</details>
</div>

### The Poisson Random Variable

Suppose the probability mass function of a random variable \\(X\\) is given by
\\[
    p_x(k) = \frac{c\lambda^k}{k!}, k = 0, 1, 2, \dots, \text{where } \lambda > 0
\\]

Knowing that all probabilities sum to 1, we must have
\\[
    c\sum_{k=0}^{\infty}\frac{\lambda^k}{k!}=1
\\]

Using the fact that the above property is the taylor series expansion of \\(e^\lambda\\), we know that \\(c=e^{-\lambda}\\).

Suppose we want to know \\(P(X=0)\\) and \\(P(X>2)\\).
\\[
    \\begin{align}
        P(X=0) &= e^{-\lambda}\\\\
        P(X>2) &= 1-P(X=0)-P(X=1)-P(X=2)\\\\
        &=1-e^{-\lambda}-\lambda e^{-\lambda}-\frac{\lambda^2e^{-\lambda}}{2}
    \\end{align}
\\]

We'll see that the Poisson RV is closely related to the Exponential RV. The parameter \\(\lambda\\) in the exponential RV is a rate (mean rate), whereas the parameter \\(\lambda\\) in the Poisson is typically a number (mean number). To alleviate the confusion, the Poisson RV parameter is frequently referred to as \\(\alpha\\).
\\[
    p_x(k) = e^{-\alpha}\frac{\alpha^k}{k!}, k = 0, 1, 2, \dots
\\]

### The Geometric Random Variable

The number of Bernoulli trials \\(k\\) required for a success is geometrically distributed.
\\[
    p_x(k) = (1-p)^{k-1}p, k=1, 2, \dots
\\]
<div class="ex">
<details>
<summary>
<strong>Example:</strong>

If the probability of a station transmitting a packet successfully is \\(\frac{1}{3}\\), what is the probability that 2 transmissions are needed?

</summary>

\\[
    p_x(2) = \left(1-\tfrac{1}{3}\right)\left(\tfrac{1}{3}\right)
\\]

</details>
</div>

### Modified Geometric Random Variable

Suppose that we wanted the number of failures *up until a success*.

This is the modified geometric RV.

\\[
    p_x(k) = (1-p)^kp, k=1, 2, \dots
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong>

If the probability of a station transmitting a packet successfully is \\(\tfrac{1}{3}\\), what is the probability that there were 4 failures before a success?
</summary>

\\[
    \left(\tfrac{2}{3}\right)^4\left(\tfrac{1}{3}\right) = \tfrac{16}{243}
\\]

</details>
</div>

### Functions of Random Variables

Given a random variable \\(X\\), one may generate other random variables by applying various transformations on \\(X\\).

Let the random variable \\(X\\) be the temperature in degrees Celsius and consider the transformation \\(Y = 1.8X + 32\\), which gives the temperature in degrees Fahrenheit.

In this example, \\(Y\\) is a linear function of \\(X\\) of the form
\\[
    Y = g(X) = aX + b
\\]
where \\(a\\) and \\(b\\) are scalars.

We may also consider nonlinear functions of the general form \\(Y = g(X)\\).

To obtain \\(p_Y(y)\\) for any \\(y\\), we add the probabilities of all values of \\(x\\) such that \\(g(x) = y\\):
\\[
    p_Y(y) = \sum_{\\{ x|g(x)=y \\}}{p_X(x)}
\\]

Let \\(Y = |X|\\) and let us apply the preceding formula for the PMF to the case where
\\[
    \\begin{cases}
        \frac{1}{9} \text{ if } x \in [-4, 4]\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

The possible values of \\(Y\\) are \\(y=0, 1, 2, 3, 4\\).

We have \\(p_Y(0) = p_X(0) = \frac{1}{9}\\).

Note that two values of \\(X\\) correspond to each \\(y=1, 2, 3, 4\\). For example:
\\[
    p_Y(1) = p_X(-1) + p_x(1) = \frac{2}{9}
\\]

Thus, the PMF of Y is
\\[
    p_Y(y) = 
    \\begin{cases}
        \frac{2}{9} \text{ if } y=1, 2, 3, 4\\\\
        \frac{1}{9} \text{ if } y=0\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

For another related example, let \\(Z = X^2\\).

To obtain the PMF of \\(Z\\), we can view it either as the square of the random variable \\(X\\) or as the square of the random variable \\(Y\\).

If we let \\(p_Z(z) = \sum{\\{ y|y^2=z \\}p_Y(y)}\\), we obtain
\\[
    p_Z(z) =
    \\begin{cases}
        \frac{2}{9} \text{ if } z=1, 4, 9, 16\\\\
        \frac{1}{9} \text{ if } z=0\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

### Expectation, Mean, and Variance

We define the expected value (also called the *expectation* or the *mean*) of a random variable \\(X\\) with PMF \\(p_X(x)\\) by
\\[
    E[X] = \sum_{x}{xp_X(x)}
\\]

Consider two independent coin tosses, each with a \\(\tfrac{3}{4}\\) probability of a head, and let \\(X\\) be the number of heads obtained. This is a binomial random variable with parameters \\(n = 2\\) and \\(p = \tfrac{3}{4}\\). Its PMF is
\\[
    p_X(k) =
    \\begin{cases}
        \begin{align}
        &\left(\tfrac{1}{4}\right)^2 &\text{if } k=0\\\\
        &2\cdot\left(\tfrac{1}{4}\right)\cdot\left(\tfrac{3}{4}\right) &\text{if } k=1\\\\
        &\left(\tfrac{3}{4}\right)^2 &\text{if } k=2\\\\
        &0 &\text{otherwise}\\\\
        \end{align}
    \\end{cases}
\\]

So, the mean is

\\[
    \\begin{align}
        E[X] &= 0 \cdot \left(\tfrac{1}{4}\right)^2 + 1 \cdot \left(2 \cdot \tfrac{1}{4} \cdot \tfrac{3}{4}\right) + 2 \cdot \left(\tfrac{3}{4}\right)^2\\\\
        &= \tfrac{24}{16}\\\\
        &= \tfrac{3}{2}
    \\end{align}
\\]

### Moments & Variance

The \\(n^{th}\\) moment of the random variable \\(X\\), denoted as \\(E[X^n]\\) is the expected value of the random variable \\(X^n\\).

The most important quantity associated with a random variable \\(X\\) other than the mean is its variance, which is denoted by \\(\text{var}(X)\\) and is defined as the expected value of the random variable \\(\left(X-E[X]\right)^2\\).

Note that this means the variance is *always* nonnegative.

THe variance provides a measure of dispersion of \\(X\\) around its mean. Another measure of dispersion is the standard deviation of \\(X\\), which is defined as the square root of the variance and is denoted by \\(\sigma_X\\).
\\[
    \sigma_X = \sqrt{\text{var}(X)}
\\]

### Expected Value Rule for Random Variable Functions

Let \\(X\\) be a random variable with PMF \\(p_X(x)\\) and let \\(g(X)\\) be a real-valued function of \\(X\\). Then, the expected value of the random variable \\(g(X)\\) is given by
\\[
    E[g(X)] = \sum_{x}{g(x)p_X(x)}
\\]

Let \\(X\\) be a random variable and let \\(Y = aX+b\\), where \\(a\\) and \\(b\\) are given scalars. Then, \\(E[Y] = aE[X] + b\\) and \\(\text{var}(Y) = a^2\text{var}(X)\\).

The variance of a random variable in terms of the moments expression is
\\[
    \text{var}(X) = E[X^2] - \left(E[X]\right)^2
\\]

Again, consider two independent coin tosses, each with a \\(\tfrac{3}{4}\\) probability of a head. Let \\(X\\) be the number of heads obtained. This is a binomial random variable with parameters \\(n=2\\) and \\(p=\tfrac{3}{4}\\). Its PMF is
\\[
    p_X(k) =
    \\begin{cases}
        \begin{align}
        &\left(\tfrac{1}{4}\right)^2 &\text{if } k=0\\\\
        &2\cdot\left(\tfrac{1}{4}\right)\cdot\left(\tfrac{3}{4}\right) &\text{if } k=1\\\\
        &\left(\tfrac{3}{4}\right)^2 &\text{if } k=2\\\\
        &0 &\text{otherwise}\\\\
        \end{align}
    \\end{cases}
\\]

The first two moments and variance are
\\[
    \\begin{align}
        E[X] &= 0 \cdot \tfrac{1}{4}^2 + 1 \cdot \left(2 \cdot \tfrac{1}{4} \cdot \tfrac{3}{4}\right) + 2 \cdot \tfrac{3}{4}^2 = \tfrac{24}{16} = \tfrac{3}{2}\\\\
        E[X] &= 0 \cdot \tfrac{1}{4}^2 + 1^2 \cdot \left(2 \cdot \tfrac{1}{4} \cdot \tfrac{3}{4}\right) + 2^2 \cdot \tfrac{3}{4}^2 = \tfrac{24}{16} = \tfrac{21}{8}\\\\
        \text{var}(X) &= \tfrac{21}{8} - \tfrac{3}{2}^2 = \tfrac{3}{8}
    \\end{align}
\\]

### Discrete Uniform Random Variable

What is the mean and variance of the roll of a fair six-sided die? Its PMF is
\\[
    p_X(k) =
    \\begin{cases}
        \tfrac{1}{6} \text{ if } k=1, 2, 3, 4, 5, 6\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

\\[
    \\begin{align}
        E[X] &= 3.5\\\\
        \text{var}(X) &= E[X^2]-\left(E[X]\right)^2\\\\
        &= \tfrac{1}{6}\left(1^2+2^2+3^2+4^2+5^2+6^2\right) - (3.5)^2\\\\
        &= \tfrac{35}{12}
    \\end{align}
\\]

The above random variable is a special case of a **discrete uniformly distributed random variable**, or **discrete uniform** for short.

The discrete uniform random variable has a PMF of the form
\\[
    p_X(k) =
    \\begin{cases}
        \tfrac{1}{b-a+1} \text{ if } k \in [a, b]\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]
where \\(a, b \in \mathbb{Z}, a < b\\).

The mean and variance are
\\[
    \\begin{align}
        E[X] &= \frac{a+b}{2}\\\\
        \text{var}(X) &= E[X^2] - \left(E[X]\right)^2 = \frac{(b-a+1)^2-1}{12}
    \\end{align}
\\]