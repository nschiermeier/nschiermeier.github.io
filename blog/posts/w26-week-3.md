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

The next thing we went over was the **Method of Moments**. These are estimators obtained by replacing population moments by sample moments: $\mu^,_k = E[x^k] \rightarrow k^{th}$ population moment, $m_k = \frac{1}{n}\sum_{i=1}^nx_i^k \rightarrow k^{th}$ sample mean. Our goal is to estimate $\mu^,_k$ by $m_k$, and to estimate $\tau(\theta)$, by first expressing it as a function of population moments ($\tau(\theta) = h(\mu^,_1,...,\mu^p_k$)), then estimate $\tau(\theta)$ by $\hat{\tau}(\theta) = h(m_1,...,m_k)$

These methods are useful because they are consistent. They are often used when other methods fail or are extremely complicated (or to achieve robustness), or sometimes as preliminary estimators.

The last concept talked about this week was *Maximum Likelihood Estimators*. The **likelihood function** of $n$ random vars $X_1,...,X_n$ is defined to be the joint density of the $n$ random variables: $f_{X_1,...,X_n}(x_1,...,x_n) = f_\vec{X}(\vec{x}|\theta)$, which is a function of $\theta$. If these random variables are a random sample from the density, then the likelihood function is $\Pi_{i=1}^n f_X(x_i|\theta)$. Often times, the notion $L(\theta|\vec{X}) = f_\vec{X}(\vec{x}|\theta)$ is used.

The goal of this (as the name implies) is to find a value of $\theta \in \Theta$ that maximizes $L$. This is often does via maximizing the log-likelihood function (since log is a monotonic transformation, meaning it doesn't affect the rank of the data.)

To find the MLE, the standard approach is:
1. Take the log of the likelihood function
2. Solve for the first derivative to find the candidate(s)
3. Check the concavity of the likelihood function (sign of the second derivative)
  - If the sign is negative definite for all $\theta$, then the original derivative found in step 2 is the unique global maximizer.
  - If it is negative but not for all $\theta$, then $\hat{\theta}$ is a local max, and you need to compare all local maxes across all boundary points.
  
### STATS 205

There was only one lecture for this class this week, due to MLK day on Monday. The two big topics covered in this lecture were Posterior predictive checking, as well as Jeffrey's Prior.

To check the posterior prediction, **composition sampling** is used. To do this, first $\theta^{(1)}$ is sampled from the posterior distribution $p(\theta|y_1,...,y_n)$ already calculated. Then, $y_{n+1}^{(1)}$ is sampled from the new distribution created, $p(y|\theta^{(1)})$. This is repeated $B$ times, and then plotted to see if it has a similar shape to the actual data. If it does, the model is appropriate for the data.

The next concept is **Jeffrey's prior**, which has local uniformity (meaning it does not change much over the region that the likelihood is also in, and it does not have large values outside this range) making it a non-informative prior. Jeffrey's prior is calculated by first finding Fisher's Information, which is the expected value of the second derivative of the log likelihood, or 

\\[I(\theta)=-E_{y|\theta}\left[\frac{\delta^2\log p(y|\theta)}{\delta\theta^2}\right] \\]

for all you more math-y people. Then, Jeffrey's prior is $p(\theta)\propto|I(\theta)|^{1/2}$.  An interesting fact about this prior is that it is *invariant*, so it yields the same result result if applied to a transformed parameter.

### STATS 211

The main topic covered this week was associations among covariates, and the role of adjustment variables. This happens by effect modifiers, which are another way of saying "interaction terms", which were covered last quarter. We can call this effect modifier $W$, and it is the association between the predictor of interest $X$ and the outcome of interest $Y$ which differs with each level of $W$. Essentially, adding more $W$s adds more tests, because you then test association between $X$ and $Y$ at each $W$.

A lot of these names / terms for these adjustment variables specific to my professor, but I will describe them in a way that is hopefully pretty general.

The first variable is a **confounding variable**. This variable is both causally related with $X$ and $Y$. 

<img src="posts/Images/confounder.png" alt="Confounding Variable" width="100%">

The next type of adjusting variable is a **mediator**. This type of variable lies in the causal pathway between $X$ and $Y$. If you remove the pathway from $X\rightarrow W$, you can no longer relate $X$ to $Y$.

<img src="posts/Images/mediator.png" alt="Mediator" width="100%">

The third type is a **precision variable**. This covariate is related to the $Y$ but not to $X$.

<img src="posts/Images/precision.png" alt="Precision Variable" width="100%">

The final type is a **nuisance variable**. This is the opposite of a precision variable, because it _may or may not_ be related to $X$ only, and not $Y$.

<img src="posts/Images/nuisance.png" alt="Nuisance Variable" width="100%">

For these variables, we have two models: 

- $E[Y_i] \beta_0 + \beta_1X_i$, which is unadjusted, where $\beta_1$ is the difference in the mean of $Y$ for groups differing by 1-unit in $X$, and 
- $E[Y_i]=\gamma_0+\gamma_1X_i+\gamma_2W_i$, which is the adjusted model, where $\gamma_1$ is the difference in the mean of Y for groups differing by 1-unit in $X$, but having the same $W$ value.

There are two important things to consider for these models, those being the bias and the variance. To check these, we consider $r_{XW}$, the correlation of $X$ and $W$, and $\gamma_2$, the relation between $W$ and $Y$. The following chart shows how these considerations hold for different values of $r_{XW}$ and $\gamma_2$:

<img src="posts/Images/rho_gamma_matrix.png" alt="Decision Matrix for two Models" width="100%">

That was the big topic for this week. Other than that, we went over remedies for nonconstant variance in linear regression. There are three ways to address this problem:
1. Transform the outcome variable
2. Robust variance estimators
3. Weighted Least Squares (discussed briefly last quarter)

The first and third methods have been discussed last quarter, so I will just focus on the second one, which is new (at least to me). This one this involves using a matrix $\Sigma$ which has all its diagonal elements as $\sigma^2_i$. Now, the true variance of $\hat{\vec{\beta}} = (X^TX)^{-1}X^T\Sigma X(X^TX)^{-1}$. 

A common estimator of $\sigma^2_i$ the squared residual, $e_i^2=(Y_i-\hat{Y_i})^2$, which results in $\hat{\Sigma}$. This is called the _robust_ variance estimator, and requires a large sample for reliable estimates. Another funny name for this estimator is the *sandwich* estimator, because it is sandwiched in between the two $(X^TX)^{-1}$ terms. 

### Personal

For the thought-tank, I will recount a personal experience I had this week.
I met with a Professor here at UCI to try and begin working on a project with him. This professor's interests are in using statistical modeling implemented into the flexibility of AI. That sounded like something right up my alley, so I emailed him and askled to meet with him. I may have talked about this last quarter, but there was a lab-fair that was held in the department, and this professor had some research using satellite imagery, which is what I did a lot of at JPL, so it seemed like a good entry point. His other research seemed really interesting to me too. The project I asked him about is essentially trying to predict wildfires based on spatiotemporal data. I thought that this was really neat, especially given the fires that swept across California last year and impacted some people I know. Though I haven't had any formal education for spatial data (UCI is offering a class on it this quarter, but the three classes I'm in are core classes and cannot be skipped...) but I did take a Time Series course at Purdue in my last semester, so I still remember a decent amount from it. I'm really looking forward to this project, it seems interesting, and I think I clicked well with the professor, so here's hoping all goes well!
