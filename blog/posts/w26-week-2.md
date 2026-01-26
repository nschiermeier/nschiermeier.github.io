Another week down! It's crazy to think we're already 20% through this quarter, but it is 2/10 weeks. I guess it's a little less thank 20% if including finals week. There's already a lot of homework in classes, so I need to refresh on my notes and upload them here!

### STATS 200B

The first lecture of this class went over the classical Limiting theorems that were mentioned last quarter. These include the **Law of Large Numbers**, **Central Limit Theorem**, **Convergence Theorems for MGFs**, **Continuous Mapping Theorem**, and **Slutsky's Theorem**. Since these are already uploaded from last quarter (around weeks 8, 9, and 10) I don't want to rewrite them. The one theorem I do want to go over is the **Delta Method**, as that was mentioned very briefly last quarter but I wanted to understand it more.

For the Delta Method, suppose $a_n(X_n-b)\xrightarrow{d}X$ with $a_n\rightarrow\infty$ as $n\rightarrow\infty$, and suppose $g$ has a derivative $g'$ at b, and $g'(b) \neq 0$. Then, $a_n(g(X_n))-g(b)\xrightarrow{d}N(0,\sigma^2[g'(b)]^2)$ This is proved using Taylor Series expansions. The delta method is a method of deriving the asymptotic distibution of a random variable. In general, this is a good tool to prove asymptotics, when the random variables being considered is differentiable and asymptotically Gaussian.

In the second lecture of this class, we moved on to the first new concept of the class, which was principles of data reduction. The first part of this was defining what a **sufficient statistic** is: $T(\vec{X})$ is a sufficient statistic for $\theta$ if the conditional distribution of $\vec{X}$ given $T(\vec{X})$ does not depend on $\theta$. 

A sufficient statistic contains all the information about $\theta$ that is contained in the data, or, given a value of $T(\vec{X})$, we gain no information about $\theta$ from the original data.
I don't want to write the full example out (even I have a limit on how much LaTex I can write...), but a brief starter to this example is considering $X_1,...,X_n \~$ iid Bernoulli($p$) r.v.s, with $0<p<1$, Then $T(\vec{X})=\sum_{i=1}^nx_i$ is a sufficient statistic for $p$. Solving for $P(X_1=x_1,...,X_n=x_n|\sum_{i=1}^nx_i)$ $(\text{which is }\vec{X}$ given $T(\vec{X}))$ will result in a distribution that doesn't have $p$ in it at all, so we gain no information about $p$ $(\text{originally called }\theta)$ from the original data (The Bernoulli distn.)

Here is one Theorem relating to sufficient statistics: Let $f_\vec{X}(\vec{x}|\theta)$ be the joint density of $\vec{X}$ and $q(t|\theta)$ be the density of $T(\vec{X})$, then T(\vec{X}) is a sufficient statistic for $\theta$ if $\frac{f_\vec{X}(\vec{x}|\theta)}{q(T(\vec{X}|\theta)}$ is free of $\theta$. 

The second theorem we went over relating to this topic was the Factorization Theorem. This theorem is somewhat similar to the last, but is as follows: Let $f_\vec{X}(\vec{x}|\theta)$ be the joint density of $\vec{X}$. A statistic $T(\vec{X})$ is a sufficient statistic for $\theta$ if and only if we can factor $f_\vec{X}(\vec{x}|\theta)$ into: \[ f_\vec{X}(\vec{x}|\theta) = g(T(\vec{x})|\theta)h(\vec{x}) \forall \vec{x} \text{ & } \theta\] where:
- $g(T(\vec{x})|\theta)$ is a function of $\vec{x}$ only through $t$ and a function of $\theta$;
- $h(\vec{x})$ is a function of $\vec{x}$ and free of $\theta$.

### STATS 205

In Bayesian Data Analysis this week, we talked about some specific prior and posterior distributions that are often seen together (called **conjugates**), and ended the week talking about prediction for Bayesian statistics.

The first conjugate we talked about was the binomial-beta conjugate. If we let our prior distribution be $\theta \text{\~}p(\theta) = \text{Beta}(a,b)$ and our likelihood be $Y|\theta \text{\~}p(y|\theta) = \text{Binomial}(\theta)$ then our posterior is $p(\theta|y) = \text{Beta}(\tilde{a}=a+y,\tilde{b}=b+n-y)$. This adds the number of successes to a, and the number of failures to b. From here, we can calculate a bunch of *summary statistics* from these distributions. Those are the mean, mode, variance, and even credible intervals. For the posterior beta distribution, our mean is $\frac{\tilde{a}}{\tilde{a}+\tilde{b}}$, the mode is $\frac{\tilde{a}-1}{(\tilde{a}-1)+(\tilde{b}-1)}$, and the variance is $\frac{\tilde{a}\*\tilde{b}}{(\tilde{a}+\tilde{b}+1)\*(\tilde{a}+\tilde{b})^2}$.

An interesting note from this is that the posterior variance is usually smaller than the prior variance. This makes sense, as it shows that you are learning from the prior, which leads to a "better" interval. Also, if you have a large enough $n$ (sample size), then the mean will be the usual $\frac{y}{n}=\bar{y}$. This is because the data will "speak for itself", so the prior doesn't matter as much. The same applies to variance.

The other conjugate that was discussed was the Poisson-Gamma conjugate. For this one, we are given the sampling model $p(y|\theta) = \text{Poisson}(\theta)$. The prior to be used is (if you couldn't guess by the title of this conjugate...) $p(\theta) = \frac{b^a}{\Gamma(a)}\theta^{a-1}\*e^{-b\*\theta}$. From this, we can get our posterior $p(\theta|y)=\text{Gamma}(\tilde{a}=a+y,\tilde{b}=b+n)$. $a$ is the prior sum of observations, and $b$ is the piror sample size. The posterior mean is $\frac{\tilde{a}}{\tilde{b}}$, variance is $\frac{\tilde{a}}{\tilde{b}^2}$, and the mode is $\frac{\tilde{a}-1}{\tilde{b}}$ if $a > 1$, and $0 \text{ if } a \leq 0$.

The other important topic covered was predictions in a Bayesian setting. In Bayesian statistics, there are two ways to do predictions:
- the *prior predictive* distribution, which is predicting the outcome **before** having observed the data, and
- the *posterior predictive distribution*, which is predicting the outcome **after** having observed the data.

The prior predictive distribution is $p(y) = \int_{\theta \in \Theta} p(y, \theta)  d\theta = \int_{\theta \in \Theta}p(y|\theta)*p(\theta)d\theta$. This is the basic application of Bayes rule, splitting the joint probability into marginal $\times$ conditional.

For the posterior predictive distribution, suppose there is observed data $y_1,...,y_n$, and $y_{n+1}$ is wanted to be predicted, *given* what has been observed so far. In this case, the following conditional density is used: $p(y_{n+1}|y_1,...,y_n) = \int_{\theta\in\Theta}p(y_{n+1},\theta|y_1,...,y_n)d\theta$  $=\int_{\theta\in\Theta}p(y_{n+1}|\theta)*p(\theta|y_1,...,y_n)d\theta$.

In words, this takes the new data given the observed data, then breaks it down into marginal $\times$ conditional, but the marginal part is the new data to be predicted given some parameter, and the conditional is the posterior, which is the parameter already predicted given previous data. An important assumption that comes from this is actually *dependence*. If the new observation $Y_{n+1}$ were independent of the previous ones $Y_1, ..., Y_n$, then all the previous data would give us no information about $\theta$ which would in turn then give no information about $Y_{n+1}$. Therefore, dependence is assumed.

### STATS 211

In Statistical Methods II, we continued with some review from the first class in this series, including Ordinary Least Squares mean and variance, as well as optimality. For an OLS estimator to be the MLE, the estimator must be consistent, asymptotically normally distributed, and asymptotically efficient (meaning it achieves the Cramer-Rao lower bound).

Another important topic is what to do if we do not have the normality assumption. In this case, we make use of the **Gauss-Markov** Theorem. This theorem supposes $\text{Var}(\vec{Y})=\sigma^2I_n$, then **$\tilde{\beta}=CY$** is an unbiased estimator of $\vec{\beta}$, and the variance of these linear functions is at least as great as the variance of linear functions of $\hat{\vec{\beta}}$. 

If $\text{Var}(\vec{Y})=$ **$\Sigma$** is arbitrary, there can be a nonsingular symmetric matrix **$A$** such that **$\Sigma=AA$**. Then, we can get $Z=$**$A^{-1}$**$\vec{Y}$ with expectation **$A^{-1}X$**$\vec{\beta}$ and variance  **$A^{-1}\Sigma A^{-1}=I_n$**. If we let **$W=A^{-1}X$**, the ordinary least squares estimate for $\vec{\beta}$ is $\hat{\vec{\beta}}=$**$(W^TW)^{-1}W^T\vec{Z}$**. This looks very familiar to the standard OLS model learned last quarter!

Finally, in terms of the original response $\vec{Y}$ and predictors **$X$**, we get $\hat{\vec{\beta}}=$**$(X^T\Sigma^{-1}X)^{-1}X^T\Sigma^{-1}\vec{Y}$**. This is unbiased, and by GMT is the best linear unbiased estimator in this general setting.

However, if normality is assumed, and in the case of constant variance, $\hat{\vec{\beta}}\text{\~}N(\vec{\beta},\sigma^2(X^TX)^{-1})$, and this is the "exact distribution", which was always assumed in STATS 210 last quarter (and what I hinted at before). So it's interesting to see how now we are branching off, and starting to look at not-so-perfect scenarios!

Another topic when normality is not satisfied is to use the Lindeberg-Feller CLT. This states if $Y_1,...,$ are independent random variables, with $E[Y_i]=0, Var(Y_i) = \sigma^2_i, \text{ then let }S_n=\sum_{i=1}^nY_i, \sigma^2_{(n)}=\sum_{i=1}^n\sigma^2_i$, then:
1. $\frac{S_n}{\sigma_{(n)}}\xrightarrow{d} N(0,1)$
2. $\lim_{n\rightarrow\infty} \text{max}\{\frac{\sigma^2_i}{\sigma^2_{(n)}}, 1\leq i\leq n\} = 0$.

These hold iff: \[\forall \epsilon > 0, \lim_{n\rightarrow\infty} \frac{1}{\sigma^2_{(n)}}\sum_{i=1}^nE[|Y_i|^21_{[|Y_i|\geq \epsilon\sigma_{(n)}]}=0\]

The final way to help with normality is to center covariates. Doing this is only possible with independence, and it only holds if the max of the center is 0 as n goes to infinity.

### Personal

Cool stuff this week! I really enjoyed learning it, and some of it started to piece together and click, so I enjoyed the content covered. I went around to some professors office hours for the classes I'm in and started introducing myself, as they all seem very friendly and willing to chat. I'm glad I'm still mostly getting these digitized-notes out on time, too (MLK day was today, so technically I still got it out "this weekend...")

Also, I finished the second book in the *Foundation* trilogy. I just want to note that I saw the plot twist from the very beginning! I enjoyed the book, though it is somewhat tough to get through. I'm not sure if "dense" is the right word, but it is a lot to process in my opinion. I'm excited to read the third one though, but first, a slight divergence to a book my dad got me for Chirstmas about creating habits. I try to read a book to help better myself every January in anticipation of the New Years. Maybe this will put me closer to my goal of becomming smarter, by building good study habits. 
I do actually track books I've read in a Google Doc, and thought about adding a page to the website for my book tracker. It is actually fully made and updates live with the Google Doc, but I haven't published it yet, since I don't want this website to be too convoluted. It's always an option though.

I don't have anything else to add really, but I guess since this is the soapbox, I can complain about whatever I want to, right? Well, my main football team (Chargers) were eliminated from the playoffs last week, which sucked, and this weekend, both my backup (49ers) and my backup backup (Texans) were eliminated. So now I have no one to root for this year, so I guess I'll just watch for the commercials. Or, maybe this is a sign to study, seeing as I have a midterm the day after the superbowl... Or, maybe I'll just pick a backup backup backup team so I still have something to look forward to (go Seahawks..?)