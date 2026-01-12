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

### STATS 205

The first lecture of this class was about what Bayesian statistics is. In short, this subject is about taking a prior distribution, applying it to a likelihood, and then using the resulting posterior distribution. The first step of this is to determine which distribution you would like to use as the prior. There is some belief before observing your data, such as an expert's opinion, historical evidence, etc.  By doing this, it turns the parameter $\theta$ into a random variable.

As a basic example, suppose there's a dataset that records 9 Heads in 12 Flips on a coin. The goal is to test whether the coin is fair or not (That is, the parameter $\theta=\frac{1}{2}$.) There are two ways this experiment could have been conducted: the first would be a Binomial distribution with 12 flips, and we recorded the number of heads from those 12 flips. The other way is to use a Negative Binomial distribution, where we were flipping the coin until we got 3 fails (tails). 

Interestingly, conducting a hypothesis test with these two leads to two different results! One of them leads to a rejection of the null, why the other does not reject it (though I did not write down which was which, oops...)

In the second lecture of this class, we discussed Joint Density Priors. 

Some very important terminology for this class are the following:
- $p(\theta)$ is the **prior probability**, which expresses the beliefs regarding $\theta$ before observing the data
- $p(y|\theta)$ is the **sampling model** for the data, and what yields the likelihood
- $p(y)$ is the **marginal density** of the data

To get the joint density, we can apply Bayes' Theorem from STATS 200A, and do marginal distribution $\times$ conditional distribution to get the joint. Using the definitions from above, this leads to: \[ p(\theta|y) = \frac{p(y|\theta) * p(\theta)}{p(y)}\]

which is what we learned in 200A.

One important question that follows is how do we choose a prior distribution and what does it represent? There are two types of priors: a **non-informative prior**, which is a dispersed distribution and doesn't hold a lot of weight, and a **improper prior**, which is where the integral of the prior is $\infty$.

Finally, we discussed prior sensitivity, which checks to see if the results change when using different priors (like in that coin flip example above).

### STATS 211

This class is an extension of STATS 210 (Linear Models) and goes over Generalized Linear Models. The first classes went over very broad concepts about being a statistician as a whole. We started by talking about two different types of analyses: **cluster analysis** is when there is no well-defined response, but you look for clusters of individuals that are similar. The other is **factor analysis**, which relates to high vs low dimensionality.

We also discussed hypothesis generation, which uses data-driven modeling, and hypothesis testing, which doesn't use data-driven modeling, as that would turn it into a conditional estimation question (such as looking at diabetes vs blood pressure, then testing diabetes vs blood pressure at a similar weight, which is *conditioning on weight*). 

In hypothesis generation, we need to know what defines the sample, as well as what we are generalizing to. We can't generalize to the entire world, just the population of our sample (i.e., all patients in hospital A when we took a sample of 30 random patients from hospital A).

Finally, we went over the required steps for a data analysis. These are understanding the aims of data analysis, establishing the context of the analysis, developing a statistical model, evaluating the properties of the design, computation, then interpreting the results. This was a big part of STATS 210, so we just did a brief recap of it. One important note is that if you transform your response to help with issues such as nonconstant variance in the model, this changes the question you are answering. Many times, the scientific question to be addressed can be viewed as *comparing the distribution across subpopulations*.

We ended the class by talking about a few different models, and discussing how everything talked about in STATS 210 (Like $\chi^2$, t-test, ANOVA, etc.) all build up from a Linear Model. There are three different types of parameters for a model, too. If all parameters of interest are in $\vec{\beta}$, the model can be *parametric* if there are finite dimensions and *semiparametric* if there are infinite dimensions. If $\vec{\beta}$ does not contain all parameters of interest and there are infinite dimensions, the model is called *nonparametric*.
