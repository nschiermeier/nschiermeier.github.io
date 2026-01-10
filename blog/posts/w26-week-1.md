Welcome to the first week of Winter Quarter 2026! From what I've heard from older students in the department, this is the toughest quarter for first-year students. The classes I'm taking this quarter are Intermediate Probability and Statistical Theory (the second in a three-part course sequence), Intro to Bayesian Data Analysis, and Stat Methods II: GLMs. Of these, I'm most excited for the Bayesian class, as this is a newer way of looking at statistics that many of my classmates are familiar with, but I have not had any exposure to this topic and it feels like the one key I am missing. I hope after this quarter, I will have a decent idea of what Bayesian stats are all about!

### STATS 200B
We started this class by going over a few inequalities, including Markov's Inequality and Chebyshev's Inequality that were covered in 200A. The two new inequalities we went over were the **Cauchy-Scwartz Inequality** and **Hölder's Inequality**. The Cauchy-Scwartz inequality is that $(E[XY])^2 \leq E[X^2]E[Y^2]$. Hölder's inequality states that for any $p, q > 0$, satisfying $\frac{1}{p} + \frac{1}{q}=1$, we have: $|E[XY]| \leq E[|XY|] \leq (E[|X|^p])^{1/p}(E[|Y|^q])^{1/q}$. 

We also went over Jenson's Inequality, which was talked about in 200A, but not explained too well. This inequality states that if $g$ is a convex function, then $E[g(x)] \geq g(E[X])$, provided that the expectation exists. I think this diagram helps show it: 
![Jenson's Inequality Graph] (Images/jenson.png)

Essentially, if $l$ is a tangent line to $g$ at $E[x]$, then $E[g(x)] \geq E[l(x)] = l(E[x]) = g(E[x])$ (this holds by properties of convexity).

In the second lecture of the week, we learned about the 4 modes of convergence.

The first is **almost sure convergence**, which states $X_n\rightarrow_{\text{a.s.}}X$ if $P(\lim_{n\to\infty}|X_n-X| < \epsilon) = 1, \forall \epsilon > 0$

Second is **Convergence in Probability**: $X_n\rightarrow_{\text{p}}X$ if $\lim_{n\to\infty}P(|X_n-X| < \epsilon) = 1, \forall \epsilon > 0$. notice the difference of these two being that in a.s. convergence, we take the probability of the limit, but in convergence in probability we take the limit of the probability.

Third is **Convergence in Distribution (or Law)**: $X_n\rightarrow_{\text{D}}X$ if $\lim_{n\to\infty} F_{X_n}(x) = F_X(x)$. This and the last mode were discussed in 200B, so this is just a refresher.

Fourth, we discussed **Convergence in r-th mean**: $X_n \rightarrow_{\text{r}}X$ if $E[|X_n-X|^r] \rightarrow 0 \text{ as } n \rightarrow \infty, r>0$. 

After this, we discussed the implications of these convergences:

a. If $X_n \rightarrow_{\text{a.s.}} X, \text{ then } X_n\rightarrow_{\text{p}}X$

b. If $X_n \rightarrow_{\text{p}} X, \text{ then } X_n\rightarrow_{\text{D}}X$

c. If $X_n \rightarrow_{\text{r}} X, \text{ then } X_n\rightarrow_{\text{p}}X$

That was a lot from this class, but after this was just a proof for those three implications, so now we can move on to the next class.
