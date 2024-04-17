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

We can start by looking at iterations of the recurracne realtion to find a pattern.
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

We can use the same technique from question one to determine the Big $\Theta$ bounds.
- First we find the pattern. 
    - $T\left(n\right) = 13T\left(\frac{n}{13}\right) + 5$
    -  $T\left(\frac{n}{13}\right) = 13\left(13T\left(\frac{\frac{n}{13}}{13}\right) + 5\right) + 5 = 13^{2}T\left(\frac\{n}                    {13^{2}}\right) + 13\left(5\right) + 5$
    - $T\left(\frac{n}{13^{2}}\right) = 13^{3}T\left(\frac{n}{13^{3}}\right) + 13^{2}\left(5\right) + 13\left(5\right) + 5$
    - $T(n) = 13^i T\left(\frac{n}{13^i}\right) + \sum_{j=1}^{i} 13^{j-1}(5)$
- Now we want to solve for n
    - $\frac{n}{13^{i}} = 1$
    - $n = 13^{i}$
- Subsititute $i$ back in.
    - $T(n) = 13^{\log_13 n}T\left(\frac{n}{13^{\log_13 n}}\right) + \sum_{j = 1}^{\log_13 n} 13^{j - 1}\left(5\right)$
    - $T(n) = n\left(T(1)\right) + \sum_{j = 1}^{\log_13 n} 13^{j - 1}\left(5\right)$
    - The sumation of the geometric series with $\log_13 n
        - $5\cdot \sum_{j = 1}^{\log_13 n} 13^{j - 1} = \frac{13^{\log_13 n} - 1}{13 - 1} = 5\left(\frac{n - 1}{12}\right)$ 
- This allows us to ingore the constant factors and give us the asymtotic complexity $T(n) = \Theta\left(n\right)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

- Following a similar process we get the pattern 
    - $T(n)  = 13^{i}T\left(\frac{n}{13^{i}}\right) + \left(2\cdot i\right)n$
- Then we solve for n to determine i
    - $n = 13^{i}$
    - $i  = \log_{13} \left(n\right)$
- Substituting $i$ back in
    - $T\left(n\right) = 13^{\log_{13}n}T\left(\frac{n}{13^{\log_{13}n}}\right) + 2\left(\log_{13}n\right)\cdot n$
- This give us
    - $T\left(n\right) = n + 2\left(\log_{13}n\right)n$
- The asymtotic complexity is
    - $T\left(n\right) \in \Theta \left(n\log n\right)$
 
I look at recurrent-recurrences-rmille70, recurrent-recurrences-kbuss26 and worked with the TA. 
