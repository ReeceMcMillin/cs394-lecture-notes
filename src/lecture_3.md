# Lecture 3
### Sample Space & Events
Consider an experiment whose outcome is not predictable with certainty. The set of all possible outcomes of an experiment is known as the *sample space* of the experiment and is denoted by \\(\Omega\\).

<div class="ex">
<details>
<summary>
<strong>Example:</strong> What is the sample space if the outcome of an experiment consists of the determination of the sex of a newborn child? What about the order of finish in a race among 7 horses numbered 1-7?
</summary>

\\[
    \Omega = \\{ g, b \\}\\\\
    \Omega = \\{ \text{All } 7! \text{ permutations of } (1, 2, 3, 4, 5, 6, 7) \\}
\\]

</details>
</div>

Any subset \\(A\\) of the sample space is known as an event.

The event \\(A \cup B\\) occurs if either \\(A\\) or \\(B\\) occurs.
### Extra Credit: The Cake is a Lie

For any two events \\(A\\) and \\(B\\), we define the event \\(AB\\) as the *intersection* of \\(A\\) and \\(B\\), or \\(A \cap B\\).

The event consisting of no outcomes is denoted as \\(\emptyset\\).

If \\(AB = \emptyset\\), the \\(A\\) and \\(B\\) are said to be mutually exclusive.

We define the event which consists of all outcomes in \\(A_n\\) for at least one value of \\(n = 1, 2, \dots\\) as:
\\[
    A = \bigcup_{n=1}^\infty A_n
\\]

We define the event which consists of those outcomes in all events \\(A_n\\) for \\(n=1, 2, \dots\\) as:
\\[
    A = \bigcap_{n=1}^\infty A_n
\\]

We define \\(A^c\\) as the *complement* of \\(A\\). These are all events in \\(\Omega\\) but not in \\(A\\).

If all events in \\(A\\) are also in \\(B\\), then we can write \\(A \subset B\\).

If \\(A\\) contains exactly the same events as \\(B\\), then \\(A = B\\).

### Set Operations
\\[ \left(\bigcup_{i=1}^n A_i\right)^c = \bigcap_{i=1}^n A_i^c \\]
In other words, the complement of the union of *all* \\(A_i\\) is the *intersection* of all of the complements of each \\(A_i\\).

\\[ \left(\bigcap_{i=1}^n A_i\right)^c = \bigcup_{i=1}^n A_i^c \\]
In other words, the complement of the intersection of *all* \\(A_i\\) is the *union* of the all of the complements of each \\(A_i\\).

### Axioms of Probability

We can define the probability of an event occurring by its relative frequency in \\(n\\) repetitions of an experiment as \\(n \to \infty\\).

Define \\(P(A)\\) as the probability that event \\(A\\) occurs and \\(nA\\) as the number of times in the first \\(n\\) repetitions of an experiment that the event \\(A\\) occurs.

\\[P(A) = \lim_{n\to\infty}{\frac{nA}{n}} \\]
\\[P(A) = \frac{\text{number of elements in A}}{\text{number of possible outcomes}}\\]

<div class="def">

**Nonnegativity**: *\\(P(A) \geq 0\\) for every event \\(A\\).*
</div>

<div class="def">

**Additivity**: *if \\(A\\) and \\(B\\) are two disjoint events, then the probability of their union satisfies*
\\[
    P(A \cup B) = P(A) + P(B)
\\]

</div>

This expression generalizes to
\\[
    P\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^{\infty} P\left(A_i\right)
\\]

In other words, the probability of the union of all events in \\(A\\) is the sum of the probability of each event \\(A_i\\).

<div class="def">

**Normalization**: *The probability of the entire sample space \\(\Omega\\) is equal to \\(1\\).*

\\[
    P(\Omega) = 1
\\]

</div>

### Propositions
1. \\(P(A^c)=1-P(A)\\) for every event \\(A\\).
2. If \\(A \subset B\\), then \\(P(A) \leq P(B)\\).
3. \\(P(A \cup B) = P(A) + P(B) - P(A \cap B)\\)

*Note: proposition 3 can be generalized to any number of events.