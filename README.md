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

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

1. T(n) = T(1/13) + 5
   
   = T(n/169) + 5 + 5
   
   = T(n/2197) + 5 + 5 + 5
   
   ...
   
   = T(n/13^i) + 5i
   
Take i = logn

   = T(1) + 5log(n) = $\Theta log(n)$

2. T(n) = 13T(n/13) + 5
   
   = 13(13T(n/169) + 5) + 5
   
   = 13(13(13T(n/2197) + 5) + 5) + 5
   
   ...
   
   = 13^iT(n/13^i) + 5$\sum_{j = 0)^i 13^j$
   
Take i = log(n)

   = nT(1) + 5$\sum_{j = 0}^\log(n) 13^j$ = $\Theta n$

3. T(n) = 13T(n/13) + 2n
   
   = 13(13(n/169) + 2(n/13)) + 2n
   
   = 13(13(13(n/2197) + 2(n/169)) + 2(n/13)) + 2n
   
   ...
   
   = 13^iT(n/13^i) + 2in
   
Take i = log(n)

   = n + 2nlog(n) = $\Theta nlog(n)$
