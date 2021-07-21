# Lecture 7

### Joint CDFs

The joint CDF of two random variables \\(X\\) and \\(Y\\) is defined as
\\[
    F_{X,Y}(x,y) = P(X\leq x, Y\leq y) = \int_{-\infty}^{x}{\int_{-\infty}^{y}{f_{X,Y}(s, t)}dt}ds
\\]


<div class="ex">
<details>
<summary>
<strong>Example</strong>

\\[
    F_{X,Y}(x,y)=
    \\begin{cases}
        \frac{xy}{25} \text{ if } 0 \leq x, y \leq 5\\\\
        0 \text{ otherwise}
    \\end{cases}
\\] 
</summary>

The sample space is the square \\((0, 0)\\) to \\((5, 5)\\).

Find \\(P(X \leq 4, Y \leq 3)\\).
\\[
    P(X \leq 4, Y \leq 3) = F_{X,Y}(4,3)=\frac{12}{25}
\\]

</details>
</div>

The joint PDF \\(f_{X,Y}(x,y)\\) can be derived from the joint CDF by taking the derivatives with respect to both \\(x\\) and \\(y\\).
\\[
    f_{X,Y}(x,y) = \frac{\delta^2}{\delta x\delta y}F_{X,Y}(x,y)
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong> Let the joint CDF be


\\[
    F_{X,Y}(x,y) =
    \\begin{cases}
        \frac{xy}{25} \text{ if } 0 \leq x, y \leq 5\\\\
        0 \text{ otherwise }
    \\end{cases}
\\]

</summary>
The PDF will be

\\[
    \frac{delta^2}{\delta x \delta y} \cdot \frac{xy}{25} = \frac{1}{25}
\\]
</details>
</div>

### Marginal Distributions

The marginal distributions \\(f_X(x)\\) and \\(f_Y(y)\\) can be calculated as follows:
\\[
    \\begin{align}
        f_X(x) &= \int_{-\infty}^{\infty}{f_{X,Y}(x,y)}dy\\\\
        f_Y(y) &= \int_{-\infty}^{\infty}{f_{X,Y}(x,y)}dx
    \\end{align}
\\]

The expectation of a function of a joint random variable is:

\\[
    E[g(X,Y)] = \int_{-\infty}^\infty{\int_{-\infty}^\infty{g(x,y)f_{X,Y}(x,y)}dx}dy
\\]

### Conditional PDF

The conditional PDF of a continuous random variable \\(X\\), given an event \\(A\\) with \\(P(A) > 0\\), is defined as a nonnegative function

\\[
    P(X \in B|A) = f_{X|A}(x)dx
\\]

For any subset \\(B\\) of the real line,

\\[
    f_{X|{X \in A}} = 
    \\begin{cases}
        \frac{f_X(x)}{P(X \in A)} \text { if } x \in A\\\\
        0 \text{ otherwise }
    \\end{cases}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong>


The time \\(T\\) until a new light bulb burns out is an exponential random variable with parameter \\(\lambda\\). Ariadne turns the light on, leaves the room, and when she returns \\(t\\) time units later, finds the light bulb still on, which corresponds to the event \\(A = \\{T \in T\\}\\). Let \\(X\\) be the additional time until the light bulb burns out. What is the conditional CDF of \\(X\\) given event \\(A\\)?
</summary>


\\[
    \\begin{align}
        P(X > x|A) &= P(T > t + x|t > t)\\\\
        &= \frac{P(T > t + x,T > t)}{P(T>t)}\\\\
        &= \frac{P(T > t+x)}{P(T>t)}\\\\
        &= \frac{e^{-\lambda(t+x)}}{e^{-\lambda t}}\\\\
        &= e^{-\lambda x}
    \\end{align}
\\]
</details>
</div>

### Conditioning

For multiple random variables, if we condition on a positive probability event of the form \\(C=\\{(X,Y) \in A\\}\\), we have

\\[
    f_{XY|C}(x,y) =
    \\begin{cases}
        \frac{f_{X,Y}(x,y)}{P(C)} \text{ if } (x,y) \in A\\\\
        0 \text{ otherwise }
    \\end{cases}
\\]

In this case, the conditional PDF of \\(X\\) given this event can be obtained from the formula

\\[
    f_{X|C}(x) = \int_{-\infty}^\infty{f_{XY|C}(x,y)}dy
\\]

The above two formulas allow us to obtain the conditional PDF of a random variable \\(X\\) when the conditioning event is not of the form \\(\\{X \in A\\}\\) but is instead defined in terms of multiple random variables.

Let \\(X\\) and \\(Y\\) be continuous random variables with joint PDF \\(f_{X,Y}\\). For any \\(y\\) with \\(f_Y(y) > 0\\), the conditional PDF of \\(X\\) given that \\(Y=y\\) is defined by
\\[
    f_{X|Y}(x|y) = \frac{f_{X,Y}(x,y)}{f_Y(y)}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong>

Ben throws a dart at a circular target of radius \\(r\\). We assume that he always hits the target, and that all points of impact \\((x, y)\\) are equally likely so that the joint PDF of the random variables \\(X\\) and \\(Y\\) is uniform. Since the area of the circle is \\(\pi r^2\\), we have:

\\[
    f_{X,Y}(x,y) =
    \\begin{cases}
        c=\frac{1}{\text{area}} \text{ if } (x, y) \text{ is in the circle}\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

In other words,
\\[
    f_{X,Y}(x,y) =
    \\begin{cases}
        \frac{1}{\pi r^2} \text{ if } x^2+y^2 \leq r^2\\\\
        0 \text{ otherwise}
    \\end{cases}
\\]

</summary>

To calculate the conditional PDF \\(f_{X|Y}(x|y)\\), first find the marginal PDF \\(f_Y(y)\\). For \\(|y| \leq r\\), it is given by

\\[
    \\begin{align}
        f_Y(y) &= \int_{-\infty}^\infty{f_{X,Y}(x,y)}dx\\\\
        &= \frac{1}{\pi r^2}\int_{x^2+y^2 \leq r^2}dx\\\\
        &= \frac{1}{\pi r^2} \int_{\sqrt{r^2-y^2}}^{\sqrt{r^2-y^2}}dx\\\\
        &= \frac{1}{\pi r^2}\sqrt{r^2-y^2} \text{ if } |y| \leq r
    \\end{align}
\\]

Note that the marginal PDF \\(f_Y\\) is not uniform. The conditional PDF is:

\\[
    f_{X|Y}(x|y) = \frac{f_{X,Y}(x,y)}{f_Y(y)} = \frac{\frac{1}{\pi r^2}}{\frac{2}{\pi r^2}\sqrt{r^2-y^2}} \text{ if } x^2+y^2 \leq r^2
\\]

</details>
</div>
