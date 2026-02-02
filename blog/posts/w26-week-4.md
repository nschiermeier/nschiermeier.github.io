Another week down!

### STATS 200B

In this class we continued discussing Maximum Likelihood estimation. As a recap, the MLE is found by taking the log of the likelihood function, then taking the second derivative, and seeing if $\hat{\theta}$ is maximized, and if it is, then it is the MLE. There is an invariance property for MLE, and the theorem is if $\hat{\theta}$ is the MLE for $\theta$, then for any one-to-once function $\tau$, $\tau(\theta)$ is the MLE of $\tau(\theta)$. Proving this theorem comes from taking the inverse of the MLE function, then applying that to the likelihood.

There are a few methods to evaluate estimators. the first is **unbiasedness**: suppose $\hat{\theta}$ is an estimator for $\theta$, then the *bias* of $\hat{\theta}$ is defined as $E[\hat{\theta}]-\theta$. If the bias is zero $\forall \theta$, then $\hat{\theta}$ is an unbiased estimator for $\theta$. This is similar to / has already been covered in the applied courses, when we go over bias there. It is the same here, where we want $E[\hat{\theta}] = \theta$.

The next is the **Mean Squared Error** of an estimator (again, something already covered!) $\theta$ is defined as $E[(\hat{\theta}-\theta)^2]$. One property from this is that $MSE(\hat{\theta}) = Var(\hat{\theta}-\theta) + \{E[\hat{\theta}-\theta]\}^2 = Var(\hat{\theta}) + \{Bias(\theta)\}^2$.

If we cannot find an estimator that is uniformly the best $\forall \mu$, then we usually shrink the space we are considering, and find the best estimator in a restricted class. This is common in all of statistics.

### STATS 200B

Next, we talked about a **uniform minimum variance unbiased estimator** (UMVUE), where $W^\*(\vec{X})$ is a UMVUE of $\tau(\theta)$ if it satisfies:
1. $E_\theta[W^\*(\vec{X})] = \tau(\theta) \forall \theta$, i.e. $W^\*$ is an unknown unbiased estimator, and
2. $Var_\theta (W^\*(\vec{X})) \leq Var_\theta(W(\vec{X})) \forall\theta$ and any unbiased estimator $W$.

Note that UMVUE is the best estimator in terms of MSE. This was interesting to learn about, because I have heard the term UMVUE previously, but hadn't formally learned what it was. This definition makes sense to me, though!

Another very important concept talked about this week was the **Cramer-Rao Lower Bound**. This concept is important because if an estimator achieves this lower bound, then it is considered *efficient* (having the smallest possible variance). If $X_1,...,X_n$ are a sample with joint density function $f_{\vec{X}}(\vec{x}|\theta), W(\vec{X})$ is an estimator, with $\theta \in \Theta \subset \Re$, then suppose:
- $\frac{\delta}{\delta\theta}logf_{\vec{X}}(\vec{x}|\theta)$ exists $\forall\vec{x}, \theta$
- $\frac{\delta}{\delta\theta}\int f_{\vec{X}}(\vec{x}|\theta) d\vec{x} = \int \frac{\delta}{\delta\theta} f_{\vec{X}}(\vec{x}|\theta) d\vec{x}, \frac{\delta}{\delta\theta}\int W(\vec{X})f_{\vec{X}}(\vec{x}|\theta) d\vec{x} = \int W(\vec{X}) \frac{\delta}{\delta\theta} f_{\vec{X}}(\vec{x}|\theta) d\vec{x}$
- $I(\theta) = E_\theta[\frac{\delta}{\delta\theta}\{logf_{\vec{X}}(\vec{x}|\theta)\}^2] > 0$ (This is the Cramer-Rao Lower bound)

\\[Var_\theta(W(\vec{X})) \geq \frac{\frac{\delta}{\delta\theta}E_\theta[W(\theta)]^2}{E_\theta[\frac{\delta}{\delta\theta}\{logf_{\vec{X}}(\vec{x}|\theta)\}^2]}\\]

Some final terminology before wrapping up this class, the function $S(X|\theta) = \frac{\delta}{\delta\theta}\log f_X(x|\theta)$ is called the **score function**. Then, the quantity $I(\theta) = E[\{\frac{\delta}{\delta\theta}\log f_X(x|\theta)\}^2] = E_\theta[S^2(X|\theta)]$ is called the **Fisher Information**. I believe both of these have kind of been covered last week in STATS 205, but here they are again.

### STATS 205

There was again only one lecture this week for this class, and it covered Bayesian hypothesis testing. For this, we start with assigning probabilities to the hypotheses. There is $p_0 = P(H_0 \text{ is true})$, and $p_1 = P(H_1 \text{ is true})$, where $p_0+p_1=1$, since these represent the probabilities of the null and alternative hypotheses *prior* to observing any data. Under these hypotheses, the data is assumed to follow a given sampling model, $p(y|H_0)$ and $p(y|H_1)$. Using Bayes Theorem, the posterior probability given observed data $\vec{y}$ is $p(H_0|\vec{y}) = \frac{p(\vec{y}|H_0)*p(H_0)}{p(\vec{y})} = \frac{p_0 * p(\vec{y}|H_0)}{p(\vec{y})}$.
To choose between $H_0$ and $H_1$, we compare the posterior probabilities, then choose $H_0$ if and only if $P(H_0|\vec{y}) \geq P(H_1|\vec{y})$

The next topic is the *average probability of error*, which is found by $p_e = P(\text{choose } H_0|H_1) * P(H_1) + P(\text{choose} H_1|H_0) * P(H_0)$. From this, another way to choose the hypothesis is to choose one that minimizes a certain "cost" function. This can be represented as $c_{10}$, the cost of choosing $H_1$ when $H_0$ is true, and $c_{01}$, the cost of choosing $H_0$ when $H_1$ is true. Then, the average cost is calculated as $C = c_{10} * P(\text{choose } H_0|H_1) * P(H_1) + c_{01} * P(\text{choose} H_1|H_0) * P(H_0)$, so the decisions comes down to choosing $H_0$ if and only if $c_{10} * P(H_0|\vec{y}) \geq c_{01} * P(H_1|\vec{y})$, or if $\frac{P(H_0|\vec{y})}{P(H_1|\vec{y})} \geq \frac{c_{01}}{c_{10}}$, where the term on the left is called the **posterior odds** . Of course following Bayes Theorem, this term is equivalent to $\frac{p(\vec{y}|H_0)}{p(\vec{y}|H_1)} \times \frac{P(H_0)}{P(H_1)}$, which is the **Bayes Factor** times the *prior odds*. Bayes Factor measures the change from prior to posterior odds in favor of the null hypothesis, and is the Bayesian equivalent of the likelihood ratio test. 

### STATS 211

This week we covered more asymptotic likelihood theory. The first part of what was covered was largely the same as in STATS 200B this week, that being MLE. We also discussed. One thing that was covered more in this class were the six regularity assumptions regarding maximum likelihood estimates, which are as follows:
1. The true value of $\vec{\theta}$ is $\vec{\theta}_0$
2. (identifiability): $f_i(y; \vec{X}_i, \vec{\theta}_1) = f_i(y; \vec{X}_i, \vec{\theta}_2) \forall y \implies \vec{\theta}_1 = \vec{\theta}_2$
3. (common support) $A_i = \{y : f_i(y; \vec{X}_i, \vec{\theta}_1) > 0\}$ is independent of $\vec{\theta}$
4. $\frac{\delta}{\delta\vec{\theta}} \int f_i(y; \vec{X}_i, \vec{\theta}) dy = \int \frac{\delta}{\delta\vec{\theta}} f_i(y; \vec{X}_i, \vec{\theta}) dy$ (In words, we have reasonably smooth likelihood functions)
5. $\frac{\delta^3}{\delta\vec{\theta}^3} f_i(y; \vec{X}_i, \vec{\theta})$ is bounded in some open neighborhood of $\vec{\theta}_0$. This means that bounding the third deriv bounds variance (2nd moment) too.
6. As $n \rightarrow \infty$, Fisher's Information matrix is of constant rank in some open neighborhood of $\vec{\theta}_0$, and the eigenvalue all grow to $\infty$. This assumption is here because we need to be able to invert the matrices.

We also talked about the asymptotic distribution of test statistics. One important one is about the multivariate normal distribution, and that is the **quadratic form**: If $y$ has a $n$-dimensional multivariate normal distribution with mean $\mu$ and variance $\Sigma$, then: $(y-\mu)^T\Sigma^{-1}(y-\mu) \~ \chi^2_n$. The two terms on either side of the variance matrix are both Normally distributed with 0 means. 

In specific, there are 3 different tests: These are the *Score Test*, the *Wald Test*, and the *Likelihood Ratio Test*. The Wald test measures the difference between a predicted and observed statistics $\theta$, the LRT test is for the difference in the likelihood of a test statistic (when we maximize it vs. observed), and the Score Test measures if the slope is close enough to 0 to be simply from sampling error. Here is a diagram that helps visualize it:

<img src="posts/Images/three_tests.png" alt="Picture showing how the three tests interact" width="100%">

### Personal

I don't have much to write about here yet again... I can think of two topics off the top of my head: The first being this blog, and the second being dealing with setbacks.

For the blog, I feel like I started questioning the purpose again. I realized it's kind of becomming a note dump, but I kind of wanted it to be more personal than that. That's why last and this week I tried interjecting a few anecdotes about the notes, such as remembering what I've done previously. I really felt that last week but forgot to add it to the personal section, this week I didn't feel that as much, which is good, though I still don't want this to just be a note dump and want it to have more personality than that.

The second thing I want to put here is related to a post-it note I've had on my desk all year. It's about the popular product WD-40, believe it or not. I attended some seminar over summer where the speaker told us the story behind WD-40, a product that probably a majority of households own, and use somewhat frequently. WD40 stands for Water Displacement 40. I (and probably many others) have always thought it was some chemical formula, whatever W and D are on the periodic table, and then isotope 40 or something like that. But the reason it's called WD-40 is because that was the *40th try at the Water Displacement formula*. And this is a huge product that has generated tons of money, and it took them 40 tries (or 39 *failures*, if you're looking at it negative-binomially) before they finally found one that worked. 

I really like this story because it shows how perserveriance leads to success. Earlier this week, I got a homework grade back that I wasn't too pleased about. It wasn't a bad grade itself, though it was lower than what I thought I got. I wasn't necessarily upset, but I wasn't completely unbothered either. It just felt like something pestering me in the back of my mind, and I was afraid I would be thinking about it through the weekend. It wasn't until my girlfriend came over and asked about the post-it note that I realized I wrote it, but hadn't thought of it or followed it much. But then I thought about it more, and wasn't upset about this grade anymore. I see it as a way that I can improve, because if it took WD-40 39 fails, then this 1 (it wasn't even a failing grade!) shouldn't stop me, and I should be able to look over this minor setback and use it for growth.