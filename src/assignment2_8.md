# Assignment 2, #8

Poker dice is played by simultaneously rolling 5 dice. Show each of the following.

1. \\(P(\text{no two alike}) = 0.0926\\)
\\[
    \frac{\binom{6}{5}\cdot 5!}{6^5} = \frac{5}{54} \approx 0.0926
\\]

<center>
<details>
<summary><strong>Explanation</strong></summary>

There are \\(\binom{6}{5}\\) ways to choose a roll containing 5 distinct numbers and \\(5!\\) ways to order those rolls. This is taken out of \\(6^5\\) possible rolls for five dice.
</details>
</center>

2. \\(P(\text{one pair}) = 0.4630\\)
\\[
    \frac{\binom{6}{1}\binom{5}{2}\cdot 3!\binom{5}{3}}{6^5} = \frac{3600}{6^5} \approx 0.4360
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

There are \\(\binom{6}{1}\\) choices for which number has a pairing and \\(\binom{5}{2}\\) ways to choose that pair from a roll of 5 dice. There are \\(\binom{6-1}{3}\\) ways to choose the remaining values (one value from the original 6 is off-limits) with a total of \\(3!\\) orderings, again taken out of \\(6^5\\) possible events.
</details>
</center>

3. \\(P(\text{two pairs}) = 0.2315\\)
\\[
    \frac{\binom{6}{2}\binom{5}{2}\binom{3}{2}\binom{4}{1}}{6^5} = \frac{1800}{6^5} \approx 0.2315
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

There are \\(\binom{6}{2}\\) ways to choose the two numbers that make up each pair. From here, we have \\(\binom{5}{2}\\) ways to choose the first pair (choosing 2 dice from 5) and \\(\binom{3}{2}\\) ways to choose the second (choosing another 2 dice from remaining 3).

From here our only remaining choice is the value of the final die, choosing 1 value from 4 remaining options, or \\(\binom{4}{1}\\).
</details>
</center>

4. \\(P(\text{three alike}) = 0.1543\\)
\\[
    \frac{\binom{6}{1}\binom{5}{3}\cdot 2!\binom{5}{2}}{6^5} = \frac{1200}{6^5} \approx 0.1543
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

There are \\(\binom{6}{1}\\) ways to choose which number makes up our three-alike and \\(\binom{5}{3}\\) ways to select three dice from five. \\(2!\binom{6-1}{2}\\) accounts for the selection of the remaining two from five potential values with \\(2!\\) potential orderings.
</details>
</center>

5. \\(P(\text{full house}) = 0.0386\\)
\\[
    \frac{\binom{6}{1}\binom{5}{3}\binom{5}{1}}{6^5} = \frac{300}{6^5} \approx 0.0386
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

There are \\(\binom{6}{1}\\) ways to select which value has a three-alike pairing and \\(\binom{5}{3}\\) ways to select that pairing from five dice. Since the remaining two dice must have the same value and one value from the original 6 is off-limits, we're selecting one value from the remaining five, or \\(\binom{6-1}{1}\\).
</details>
</center>

6. \\(P(\text{four alike}) = 0.0193\\)
\\[
    \frac{\binom{6}{1}\binom{5}{4}\binom{5}{1}}{6^5} = \frac{150}{6^5} \approx 0.0193
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

There are again \\(\binom{6}{1}\\) ways to decide which value will make up our four-alike and \\(\binom{5}{4}\\) ways to select four dice from five. \\(\binom{6-1}{1}\\) accounts for the ways to select a value for the remaining die.
</details>
</center>

7. \\(P(\text{five alike}) = 0.0008\\)
\\[
    \frac{\binom{6}{1}\binom{5}{5}}{6^5} = \frac{6}{6^5} \approx 0.0008
\\]
<center>
<details>
<summary><strong>Explanation</strong></summary>

Given \\(\binom{6}{1}\\) ways to select which value has a five-alike pairing, there's only \\(\binom{5}{5} = 1\\) way to roll each value.
</details>
</center>
