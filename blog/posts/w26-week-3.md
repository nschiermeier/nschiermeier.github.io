Another week down! Remind me to maybe add more a description before this...

### STATS 200B

We finished the data reduction chapter this week, and started to go over Point Estimation, which relates to concepts such as Maximum Likelihood Estimation, which is used a lot in machine learning, so it was something I recognized.

We talked about **minimum sufficient statistics**, which are functions of any other sufficient statistic, that compresses the data at least as much as any other sufficient statistic. This function may be one-to-one or many-to-one, but never one-to-many, which intuitively makes sense, since you are compressing the data, you don't want your output to have more dimensions than your input. A theorem to go with this is as follows: Let $f_\vec{X}(\vec{x}|\theta)$ be the join density of $\vec{x}$, then $T(x)$ is sufficient for $\theta$ if for every two sample points $\vec{x}, \vec{y}$ ratio of $\frac{f_\vec{X}(\vec{x}|\theta)}{f_\vec{X}(\vec{y}|\theta)}$ is free of $\theta$ iff $T(\vec{x})=T(\vec{y})$. This is one way to find a minimum sufficient statistic.

We also learned about **Ancillary Statistics**, which is a statistic who's *distribution* doesn't depend on $\theta$. For a brief example, if we have $X_1,...,X_n \text{\~ iid} N(\mu, \sigma^2)$, where $\sigma^2$ is known, then $X_1 - X_2 \text{\~} N(0,2\sigma^2)$, which is free of $\mu$.

Next, we went over a very fundamental process in statistics, which is the **exponential family**. A random variable X belongs to an exponential family if its density can be written as $f_X(x|\theta) = h(x)c(\theta)e^{\sum_{j=1}^kw_j(\theta)t_j(\theta)}$, where:
- $\theta = (\theta_1, ..., \theta_d), d < k;$
- $c(\theta), w_j(\theta), j = 1,...,k$ are all functions of $\theta;$
- $h(x), t_j(x), j = 1,...,k$ are functions of $x$

Some notable distributions that belong to exponential families include Normal, Poisson, and Binomial! I remember learning about exponential families in STATS 526 at Purdue, and remember them being somewhat tricky to deal with... They were defined a little differently than here, so maybe this way of seeing it as well as it being the second time dealing with them will make it easier to understand.

The next thing we went over was the **Method of Moments**. These are estimators obtained by replacing population moments by sample moments: $\mu'_k = E[x^k]\rightarrow k^{th}$ population moment, $m_k = \frac{1}{n}\sum_{i=1}^nx_i^k \rightarrow k^{th}$ sample mean. Our goal is to estimate $\mu'_k$ by $m_k$, and to estimate $\tau(\theta)$, by first expressing it as a function of population moments ($\theta(\theta) = h(\mu'_1,...,\mu'_k$), then estimate $\tau(\theta)$ by $\hat{\tau}(\theta) = h(m_1,...,m_k)$

These methods are useful because they are consistent. They are often used when other methods fail or are extremely complicated (or to achieve robustness), or sometimes as preliminary estimators.

The last concept talked about this week was *Maximum Likelihood Estimators*. The **likelihood function** of $n$ random vars $X_1,...,X_n$ is defined to be the joint density of the $n$ random variables: $f_{X_1,...,X_n}(x_1,...,x_n) = f_\vec{X}(\vec{x}|\theta)$, which is a function of $\theta$. If these random variables are a random sample from the density, then the likelihood function is $\Pi_{i=1}^n f_X(x_i|\theta)$. Often times, the notion $L(\theta|\vec{X}) = f_\vec{X}(\vec{x}|\theta)$ is used.

The goal of this (as the name implies) is to find a value of $\theta \in \Theta$ that maximizes $L$. This is often does via maximizing the log-likelihood function (since log is a monotonic transformation, meaning it doesn't affect the rank of the data.)

To find the MLE, the standard approach is:
1. Take the log of the likelihood function
2. Solve for the first derivative to find the candidate(s)
3. Check the concavity of the likelihood function (sign of the second derivative)
  - If the sign is negative definite for all $\theta$, then the original derivative found in step 2 is the unique global maximizer.
  - If it is negative but not for all $\theta$, then $\hat{\theta}$ is a local max, and you need to compare all local maxes across all boundary points.