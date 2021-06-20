# Lecture 2

<div class="def">

**The Counting Principle**: *Consider a process of \\(r\\) stages. Suppose that:*
1. There are \\(n_1\\) possible results at the first stage.
2. For every possible result at the first stage, there are \\(n_2\\) possible results at the second stage.
3. More generally, for any sequence of possible results at the first \\(i - 1\\) stages, there are \\(n_1\\) possible results at the \\(i^{th}\\) stage.
* Then, the total number of possible results of the r-stage process is
\\[
    n_1n_2 \cdots n_r
\\]

</div>

<div class="idea">

**Big Idea**: *For problems __without permutation or replacement__, a series of decisions can be enumerated by multiplying the number of possible decisions at each stage.*
</div>

## **Extra Credit**: Favorite Sport: Football

<div class="ex">

<details>
<summary>
<strong>Example:</strong> A pixel in a digital image is represented by 8 bits. How many encodings are possible for one pixel?
</summary>

\\[
    2^8 = 256
\\]

</details>
</div>

<div class="def">

**Mutually Exclusive Counting**: *Suppose that \\(X_1, \dots, X_t\\) are sets and that the \\(i^{th}\\) set \\(X_i\\) has \\(n_i\\) elements. If \\({X_1 \dots, X_i}\\) is a _pairwise disjoint_ family, the number of possible elements that can be selected from \\(X_1\\) or \\(X_2\\) or \\( \dots \\) or \\(X_t\\) is*
\\[
    n_1 + n_2 + \dots + n_t
\\]
</div>

<div class="idea">

**Big Idea**: *Because the set family is pairwise disjoint, we can think of these sets like bubbles on a Venn Diagram that don't overlap. Counting total elements across these sets is the same as just adding the number of elements from each.*
</div>

<div class="ex">

<details>
<summary>
<strong>Example</strong>: A six person committee Alice, Ben, Connie, Dolph, Egbert, and Francisco is to select a chairperson, secretary, and treasurer.
</summary>

1. In how many ways can this be done?
\\[
    6\cdot5\cdot4=120
\\]
2. In how many ways can this be done if Alice or Ben must be chairman?
\\[
    5\cdot4 + 5\cdot 4 = 40
\\]
3. How many ways if Egbert holds one of the offices?
\\[
    \\begin{align}
        5\cdot4 + 5\cdot4 + 5\cdot4 &= 60\\\\
        3(5\cdot4) &= 60
    \\end{align}
\\]
4. How many ways if both Dolph and Francisco holds one of the offices?
\\[
    4\cdot3\cdot2=24
\\]
</details>
</div>

<div class="def">

**Inclusion-Exclusion Principle for Two Sets**:
\\[
    |X \cup Y| = |X| + |Y| - |X \cap Y|
\\]
</div>

<div class="idea">

**Big Idea**: *If two sets intersect, adding the cardinality of both individually would double-count the overlap so it's subtracted away.*
</div>

<div class="def">

**Permutation**: *A permutation of \\(n\\) distinct elements \\(x_1, \dots, x_n\\) is an ordering of the \\(n\\) elements \\(x_1, \dots, x_n\\). There are \\(n!\\) permutations of \\(n\\) elements.*
</div>

<div class="ex">
<details>
<summary><strong>Example</strong>: ABCDEF Permutations</summary>

1. How many permutations of the letters ABCDEF are there with the substring DEF?
   * *Consider DEF to be a single element:*
\\[
    4! = 24
\\]
2. How many permutations of the letters ABCDEF are there with DEF together in any order?
   * *Number of ways to order DEF is \\(3!\\). The number of permutations with DEF together is*
\\[
    3!4! = 144
\\]
3. How many ways can you seat 6 people around a round table? (if everybody moves \\(n\\) seats to the left or right, that is considered the same seating)
\\[
    5!
\\]
</details>
</div>

<div class="def">

**R-Permutation**: *An r-permutation of \\(n\\) distinct elements \\(x_1, \dots, x_n\\) is an ordering of an r-element subset of \\(x_1, \dots, x_n\\). The number of r-permutations of n distinct elements is*
\\[
    P(n, r) = \frac{n!}{(n-r)!}
\\]
</div>

<div class="ex">
<details>
<summary>
<strong>Example:</strong> How many ways can we select a chairperson, vice-chairperson, secretary, and treasurer froma  group of 10 persons?
</summary>

\\[
    P(10, 4) = 10 \cdot 9 \cdot 8 \cdot 7
\\]

</details>
</div>

<div class="ex">
<details>
<summary>
<strong>Example:</strong> In how many ways can seven distinct Martians and five distinct Neptunians wait in line if no two Neptunians stand together?
</summary>

* The Martians can stand together however they'd like, so there are \\(7!\\) options for them. Because the Neptunians must have a Martian between them, there are 8 possible positions for them to stand. This means there are \\(P(8, 5)\\) possible orderings of Neptunians.

\\[
    7! \cdot P(8, 5) = 33,868,800
\\]

</details>
</div>

<div class="def">

**Combination**: *An r-combination of \\(X\\) is an unordered selection of r elements of \\(X\\). The number of r-combinations of \\(n\\) distinct objects is*
\\[
    C(n, r) = \frac{P(n, r)}{r!} = \frac{n!}{(n-r)!r!}
\\]

* **Notation**: \\(C(n, r) = \binom{n}{r} \\)
</div>

<div class="ex">
<details>
<summary>
<strong>Example:</strong> In how many ways can we select a committee of two women and three men from a group of 5 distinct women and 6 distinct men?
</summary>

\\[
    C(5, 2) \cdot C(6, 3) = 200
\\]
</details>
</div>

<div class="ex">
<details>
<summary>
<strong>Example:</strong> How many 8-bit strings contain exactly 4 ones?
</summary>

\\[
    C(8, 4) = 70
\\]

</details>
</div>
