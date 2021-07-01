# Lecture 4
### Conditional Probability

<div class="def">

**Conditional Probability**: *The conditional probability that \\(A\\) has occurred given that \\(B\\) has occurred with \\(P(B) \geq 0\\) is defined as*
\\[
    P(A|B) = \frac{P(A\cap B)}{P(B)}
\\]

</div>

Rather than thinking about \\(P(A|B)\\) within universe \\(\Omega\\), think of \\(B\\) as *replacing* \\(\Omega\\).

\\(A\\) can be thought of as an event that occurs within the universe \\(B\\).

If the possible outcomes are finitely many and equally likely, then
\\[
    P(A|B) = \frac{\text{number of elements in }A\cap B}{\text{number of elements in }B}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong> A bin contains 25 light bulbs, 5 of which are in good condition (last at least a month), 10 of which are partially defective (works initially for 2 days), and 10 which are totally defective. Given that a bulb is lit initially for 2 days, what is the probability that it will still be working after a week?
</summary>

* Because the bulb works initially for 2 days, we know it's not totally defective. We can consider this \\(D^c\\), or the complement of the defective set. \\(D^c=\frac{15}{25}\\) because \\(\frac{10}{25}\\) are totally defective.

* We're looking for the probability that a bulb is perfectly good (\\(G\\)) *given* that it's not totally defective. The intersection of the non-defective bulbs and the perfectly good bulbs is \\(\frac{5}{25}\\) - in other words, 5 of the remaining bulbs are in good condition.

\\[
    P(G|D^c) = \frac{G\cap D^c}{P(D^c)} = \frac{\frac{5}{25}}{\frac{15}{25}}=\frac{1}{3}
\\]

</details>
</div>

### Extra Credit: Answer to the Universe = 42

### The Law of Total Probability

Let \\(A\\) and \\(B\\) be events. We may express \\(A\\) as
\\[
    A = (A \cap B) \cup (A \cap B^c)
\\]

We can also say that
\\[
    \\begin{align}
        P(A) &= P(AB) + P(AB^c)\\\\
        &=P(A|B)P(B) + P(A|B^c)P(B^c)
    \\end{align}
\\]

If the sample space \\(\Omega\\) can be partitioned into \\(n\\) mutually exclusive events \\(A_1, A_2, \dots, A_n\\), then
\\[
    \\begin{align}
        P(A) &= P(A \cap B_1) + P(A \cap B_2) + \dots + P(A \cap B_n)\\\\
        &=P(A|B_1)P(B_1) + \dots + P(A|B_n)P(B_n)
    \\end{align}
\\]

### Bayes' Formula

We can find the conditional probability \\(P(A_i|B)\\), in terms of \\(P(B|A)\\) using the law of total probability and Bayes' rule.

Let \\(A_1, A_2, \dots, A_n\\) be disjoint sets that form a partition of the sample space, and assume that \\(P(A_i) > 0\\) for all \\(i\\). Then, for any event \\(B | P(B) > 0\\), we have
\\[
    \\begin{align}
        P(A_i|B) &= \frac{P(A_i)P(B|A_i)}{P(B)}\\\\
        &=\frac{P(A_i)P(B|A_i)}{P(A_1)P(B|A_1) + \dots + P(A_n)P(B|A_n)}
    \\end{align}
\\]

<div class="ex">
<details>
<summary>
<strong>Example:</strong> A bowl contains three apples and four oranges. Bob walks by and randomly selects a fruit. Steve walks by 10 minutes later and also randomly selects a fruit from the bowl. 

Let \\(B_a\\) be the event that Bob choses an apple, \\(B_o\\) the event that Bob chooses an orange, \\(S_a\\) the event that Steve chooses an apple, and \\(S_o\\) the event that Steve chooses an orange.

What is the probability \\(P(S_a)\\) that Steve selects an apple? Use the law of total probability.
</summary>

\\[
    \\begin{align}
        P(B_a) &= \tfrac{3}{7}\\\\
        P(B_o) &= \tfrac{4}{7}\\\\
        P(S_a | B_a) &= \tfrac{2}{6} = \tfrac{1}{3}\\\\
        P(S_a | B_o) &= \tfrac{3}{6} = \tfrac{1}{2}\\\\
        P(S_a) &= P(S_a | B_a)P(B_a) + P(S_a | B_o)P(B_o)\\\\
        &= \tfrac{1}{3}\cdot\tfrac{3}{7} + \tfrac{1}{2}\cdot\tfrac{4}{7} = \tfrac{3}{7}
    \\end{align}
\\]

If Steve selected an orange, what's the possibility that Bob had also selected an orange?

\\[
    P(B_o | S_o) = \frac{}{} = \frac{\left(\tfrac{1}{2}\right)\left(\tfrac{4}{7}\right)}{\left(\tfrac{1}{2}\right)\left(\tfrac{4}{7}\right) + \left(\tfrac{2}{3}\right)\left(\tfrac{3}{7}\right)} = \frac{1}{2}
\\]

</details>
</div>

<div class="def">

**Independent Events**: *Events \\(A\\) and \\(B\\) are said to be independent if*

\\[
    \\begin{align}
        P(A | B) &= \tfrac{P(AB)}{P(B)} = P(A)\text{, or}\\\\
        P(AB)&=P(A)P(B)
    \\end{align}
\\]

</div>
