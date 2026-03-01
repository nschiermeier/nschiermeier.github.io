Okay, don't look at the date I'm writing this...
Yes it has been about 4 weeks since I've written a blog, but midterms started so I spent the website-writing time studying instead.
I know the irony being that I wanted website-writing to be a studying technique... Anyways, without further ado, welcome to week 5!

### STATS 205

We wrapped up MLE in this class this week. Another specific corollary for the attainment of CR bound is as follows: For a random sample $\vec{X}$, if the regularity conditions hold, then the unbiased estimator $W(\vec{X})$ for $\tau(\theta)$ attains the CRLB if and only if the score function $S_n(\vec{x}|\theta)$ can be written as $S_n(\vec{x}|\theta) = a(\theta)[W(\vec{x})-\tau(\theta)]$ for some function $a(\theta)$. Some notes on this subject are that the UMVUE may not achieve the CRLB, and it is uncommon for an unbiased estimator to achieve the CRLB, and there is an approach to finding a better unbiased estimator, which is what the next section is on.

To get a better unbiased estimator, if we already have $W(\vec{x})$ as an unbiased estimator of $\tau(\theta)$, then we define $\phi(T) = E[W(\vec{X})|T]$, then it holds that $E[\phi(T)] = E[E[W(\vec{X})|T]] = E[W(\vec{X})] = \tau(\theta)$ by basic conditional probability rules. Also, $Var(\phi(T)) = Var(E[W(\vec{X})|T]) = Var(W(\vec{X}))-E[Var(W(\vec{X})|T)] \leq Var(W(\vec{X}))$, again by probability rules. What this means is that we have a better unbiased estimator, since when using $T$ we reduced variance of our original unbiased estimator.

The next topic covered was asymptotic evaluations. The first definition is **consistency**, where $W_n$ is a consistent estimator for $\tau(\theta)$ if $W_n\xrightarrow{p}\tau(\theta)$. 
One theorem that holds from this is if $W_n$ is a sequence of estimators of $\tau(\theta)$, if $(1) \lim_{n\rightarrow\infty}Bias(W_n) = 0, (2) \lim_{n\rightarrow\infty}Var(W_n)=0$ for $\theta \in \Theta$, then $W_n$ is consistent for $\tau(\theta)$.

The 6 basic asymptotic regularity assumptions hold here too, which I believe were outlined in STATS 211 previously, and since there's a lot of them I don't want to rewrite them here.

A theorem related to MLE here is if $\hat{\theta}$ is MLE $\forall \theta$, and $\tau(\theta)$ is a continuous function of $\theta$, under the first four regularity conditions, $\tau(\hat{\theta})$ is a consistent estimator of $\tau(\theta)$ ( This is *sort of* like CMT)

Some final notes are that Regularity conditions may be different for difference problems, and they may be sufficient conditions for desirable asymptotic properties of concerned estimators (like MLE, Moment estimators, etc.)

### STATS 205

This class had a midterm this week, so there is just one lecture, which is on Normal models.

Since the normal distribution has two parameters, we need to find a conjugate prior distribution for both. The first would be $\mu$, which needs a conjugate prior of the form $\exp\{-c_2(\mu-c_1)^2)\}$. This can be found as $p(\mu|y_1,...,y_n,\sigma^2)\propto \exp\{-\frac{1}{2}\frac{\sum(y_i-\mu)^2}{\sigma^2}+\frac{(\mu-\mu_0)^2}{\tau_0^2}\}$. Then, this can be solved quadratically to get $A=\frac{n}{\sigma^2}+\frac{1}{\tau_0^2}, B = \frac{\sum y_i}{\sigma^2}+\frac{\mu_0}{\tau_0^2}, C = \frac{\sum y_i^2}{\sigma^2}+\frac{\mu_0^2}{\tau_0^2}$. So, a conjugate prior for $\mu$ is normal, with distribution $N(\frac{B}{A},\frac{1}{A})$. 

Also, note that $\tau^2$ is called the **precision**, and it is the inverse of the variance that is typically used. The *larger* the precision (smaller variance), the *less uncertainty / spread* in the density. Also, note that anything with the subscript $0$ means it is from the prior. The posterior precision for the model is just $A$ that was found above, and in words can be described as the precision in the data + the prior precision.

### STATS 211

In this class, we finally got to the heart of General Linear Models. 

There are three components of a GLM:
1. **Random Component**: This is the specification of the probability distribution of the outcome $Y_i$. There are different things to consider, such as if you have binary outcomes, nonnegative counts, or continuous outcomes.
2. **Systematic component**: Also known as the linear component, this is the specification of a linear combination of the explanatory variables. Why is it called the linear component? Because it's actually the same as in normal linear regression! That is, this part is taken to be $\beta_0 + \beta_1X_1 +...+\beta_{p-1}X_{p-1}$
3. **Link function**: This is the transformation of the mean response, and it "links" the mean to the systematic component. Specifically, $g(E[Y]) = g(\mu) = \beta_0 + \beta_1X_1 +...+\beta_{p-1}X_{p-1}$, and $g(.)$ is called the *link function*.

Some common choices for link functions are the identity link (aka, no link), the logit link ($g(\mu) = \log[\frac{\mu}{1-\mu}]$), or the log link ($g(\mu) = \log(\mu)$). 

The next topic covered was the **exponential family**. For this, we have $\theta$, which is out scientific parameter of interest, and $\phi$, which is a nuisance parameter. A distribution is a member of the exponential family if it's probability density function can be written in the following form:

\\[ f(y;, \theta, \phi) = \exp\left[\frac{y\theta-b(\theta)}{a(\phi)} + c(y, \phi)\right]\\]

The mean of an exponential family is $E[Y_i] = b^p(\theta_i)$, and the Variance is $Var[Y_i] = a_i(\phi)b^{pp}(\theta_i)$, where the p denotes the derivative. 

Also, for GLMs, the maximum likelihood estimation is equivalent to weighted least squares estimation for a transformed response. Essentially, GLMs keep updating a linear model until convergence. An initial value of $\vec{\beta}^{(0)}$ is chosen and updated. The weights are changed in the linear model, and updated via a 1st order Taylor expansion. I am simplifying a lot here, but it is a pretty cool process in detail.

### Personal 

Since I am updating this so late, I don't fully remember any personal annecdotes or stories that I would like to share for this week. But it's good to get back in the swing of things, and I hope I can be fully caught up with the website by the end of the week so I can go back to updating it on a regular basis.