Well, I'm not writing this on the weekend, but I still wanted to try to type out these lectures in my own way to hopefully understand them better. This was Week 9, from 11/24/25-11/26/25 (Thanksgiving break was at the end of this week).

### STATS 200A

This class went over some of the most important concepts in the class this week, which were Convergence in Probability, Convergence in Distribution, and Continuous Mapping Theorem.

Convergence in Probability is the idea that a sequence of random variables X<sub>1</sub>,...,X<sub>n</sub> converge in probability to a single random variable X if ∀ ε > 0, lim<sub>n→∞</sub> P(|X<sub>n</sub>-X| ≥ ε) = 0, then X<sub>n</sub>→<sup>P</sup>X
(We say, Xn converges in probability to X).
This is equivalent to lim<sub>n→∞</sub> P(|X<sub>n</sub>-X| < ε) = 1, by basic probability rules.

The next theorem we went over was Markov's inequality, which states if x is a non-negative r.v., then P(X ≥ α) ≤ (E[x]/α). The proof for this comes from splitting the integral from the formula for the expected value into two parts at α, then taking the *tail probability* (that is, ∫<sup>∞</sup><sub>α</sub> f(x) dx) and showing that multiplying it by α is less than the expected value alltogether.

Next is Chebyshev's inequality, which is similar to Markov's and the proof even uses Markov's Inequality. This theorem states that if x is a random variable with µ=E[x], Variance σ<sup>2</sup> = Var(x) < ∞, then
P(|x-µ| ≥ ε) ≤ (σ<sup>2</sup>/ε²). The proof for this comes from directly plugging in ε² as α in Markov's, and using Y = (x-µ)² instead of just |x-µ|. 

After these two comes the Weak Law of Large Numbers, which is what allows us to say that the average value of numbers converges to the mean, for the Normal Distribution. Specifically, if x<sub>1</sub>,...,x<sub>n</sub> are iid Normal(µ, σ²), x<sup>-</sup><sub>n</sub> = 1/n ∑<sup>n</sup><sub>i-1</sub> x<sub>i</sub>. Then, ∀ ε > 0, lim<sub>n→∞</sub> P(|x<sup>-</sup><sub>n</sub>-µ| ≥ ε) = 0, so x<sup>-</sup><sub>n</sub>→<sup>P</sup>µ.

The next important theorem we went over was Continuous Mapping Theorem, which states that if h() is a continuous function, then X<sub>n</sub>→<sup>P</sup>X => h(X<sub>n</sub>)→<sup>P</sup>h(X). For example, using WLLN, if h(x) = x², then (X<sup>-</sup><sub>n</sub>)² →<sup>P</sup> µ².

Following convergence in probability, there is also convergence in distribution. This is similar, and states that a sequence of random variables converges in distribution to a single random variable if lim<sub>n→∞</sub> F<sub>X<sub>n</sub></sub>(x) = F<sub>X</sub>(x). Similar to probability, this looks like X<sub>n</sub>→<sup>D</sup>X mathematically.
In words, this means the limit of this sequence of r.v.s converges to the distribution of another r.v. as n goes to infinity.

This is also true for MGFs, and if a sequence of r.v.s X<sub>1</sub>, ... ,X<sub>n</sub> have MGFs M<sub>1</sub>(t), ..., M<sub>n</sub>(t), and X is another r.v. with MGF M(t), then lim<sub>n→∞</sub> M<sub>n</sub>(t) = M(t), <=> X<sub>n</sub>→<sup>D</sup>X.

The Central Limit Theorem was the final big concept covered this week. This states that (X<sup>-</sup><sub>n</sub>-µ)/√(σ²/n) = √n(x<sup>-</sup></sub>n</sub>-µ)/σ →<sup>D</sup> N(0,1).

The proof for this theorem comes from basically putting everything else learned before this into one, and utilizing Taylor series expansions with the MGF as well as lots of algebra to get to the mgf of N(0,1), which shows convergence in distribution via the MGF, as shown before.

Alright, that was a lot for just one class, but it's all very important, possibly the most important takeaways from this class! This is a lot of how statistics all holds together, so it is crucial to any upcoming classes.


### STATS 210

This class only met once this week, due to the Thanksgiving Holiday. We went over outliers in that class. Outliers are extreme observations in the dataset. In order to detect outliers in the Y direction, residuals are able to be used. In the X direction, the residuals may not be that large, so we need another way to detect them.

**Leverage** is how far away a predictor is from its mean. It is how we detect outliers in the predictor variable X. This value is h<sub>ii</sub>, or the diagonal value of the hat matrix for predictor *i*. In words, the *i*<sup>th</sup> leverage measures influence of the *i*<sup>th</sup> observation on its own fitted value y<sup>^</sup><sub>i</sub>. Larger leverage means that observation has more influence.

The sum of all leverage points is ∑<sup>n</sup><sub>i=1</sub>*p*<sup>~</sup>, which is the number of regression coefficients (yes, this would include β<sub>0</sub>. Then, a common rule of thumb to detect how outliers would be any points that are two or three times the average of *p*<sup>~</sup>.

To detect Y outliers, the standardized residuals can be used. This is *r<sub>i</sub>* = (e<sub>i</sub>/σ√(1-h<sub>ii</sub>)), where *e* is the residual value. We use this because it has a standardized variance, which is helpful because it allows them to be comparable across observations.

An issue with this is that σ includes the estimate for *i*. This is an issue because is *i* is an outlier, then e<sub>i</sub> will be large, but since σ includes e²<sub>i</sub>, σ will be large, and since that is in the denominator, the whole standardized residual will appear smaller than it should. The way we fix this is by using **deleted residuals**, which utilize *e<sub>(i)</sub>*, the residual for the i<sup>th</sup> observation obtained by fitting the model *without* that observation. 

e<sub>(i)</sub> = y<sub>i</sub>-y<sup>^</sup><sub>i</sub>, where y<sup>^</sup><sub>i</sub> is the fitted value without observation i. This also equals (e<sub>i</sub>/1-h<sub>ii</sub>), so the entire model does not need to be refit. Larger leverage leads to larged deleted residual compared to the original. We can then use the **studentized residual** *t<sub>i</sub>* = (e<sub>i</sub>/σ<sup>^</sup><sub>(i)</sub>√(1-h<sub>ii</sub>)).
The degrees of freedom for this statistic is n-p<sup>~</sup>-1. The cutoff to determine an outlier with this method is |*t<sub>i</sub>*| > the t-stat for an alpha value with the previously mentioned df.

That is it for this class for this week!

### Personal

Thanksgiving. Will upload more when I get around to it...
