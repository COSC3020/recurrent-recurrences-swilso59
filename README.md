[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

- We can start by looking at iterations of the recurracne realtion to find a pattern.
- $T\left(n\right) = T\left(\frac{n}{13}\right) + 5$
- $T\left(\frac{n}{13}\right) = T(\frac{\frac{n}{13}}{13}) + 5 + 5 = T\left(\frac{n}{13^{2}}\right) + 5 + 5$
- $T\left(\frac{\frac{n}{13^{2}}}{13}\right) + 5 + 5 + 5 = T\left(\frac{n}{13^{3}}\right) + 5 + 5 + 5$
- With these iterations we can see the patter $T\left(\frac{n}{13^{k}}\right) + 5i$
- We want to get to the base case $n \leq 1$.
- We do this by solving $\frac{n}{13^{k}} \leq 1$
- We can multiply $13^{k}$ to both sides then take the $\log_{13}$ of each side which gives us.
- $\log_{13}n \leq k$
- which tells us that it will take $\log_{13}n \leq k$ iterations for us to reach our base case.
- Next we can replace $k$ and $i$ with $\log_{13}n$ to find the Big $\theta$ bound.
- $T\left(n\right) = \frac{n}{13^{\log_{13}}n} + 5\log_{13}n$
- This shows us that the asymtotic complexity is $T(n) \in \Theta\\left(log\space n\right)$
   
2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

- We can use the same technique from question one to determine the Big $\Theta$ bounds.
- First we find the pattern. 
- $T\left(n\right) = 13T\left(\frac{n}{13}\right) + 5$
- $T\left(\frac{n}{13}\right) = 13\times13T\left(\frac{\frac{n}{13}}{13}\right) + 5 + 5$
- Then we solve for n.
- 
- Subsititute back in.
- 
- The asymtotic compleixty is $T(n) = \Theta\left(n\right)

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$
