Well, I'm not writing this on the weekend, but I still wanted to try to type out these lectures in my own way to hopefully understand them better. This was Week 9, from 11/24/25-11/26/25 (Thanksgiving break was at the end of this week).

### STATS 200A

This class went over some of the most important concepts in the class this week, which were Convergence in Probability, Convergence in Distribution, and Continuous Mapping Theorem.

Convergence in Probability is the idea that a sequence of random variables X<sub>1</sub>,...,X<sub>n</sub> converge in probability to a single random variable X if ∀ ε > 0, lim<sub>n→∞</sub> P(|X<sub>n</sub>-X| ≥ ε) = 0, then X<sub>n</sub>→<sup>P</sup>X
(We say, Xn converges in probability to X).
This is equivalent to lim<sub>n→∞</sub> P(|X<sub>n</sub>-X| < ε) = 1, by basic probability rules.

The next theorem we went over was Markov's inequality, which states if x is a non-negative r.v., then P(X ≥ α) ≤ (E[x]/α). The proof for this comes from splitting the integral from the formula for the expected value into two parts at α, then taking the *tail probability* (that is, ∫<sup>∞</sup><sub>α</sub> f(x) dx) and showing that multiplying it by α is less than the expected value alltogether.

Next is Chebyshev's inequality, which is similar to Markov's and the proof even uses Markov's Inequality. This theorem states that if x is a random variable with µ=E[x], Variance σ<sup>2</sup> = Var(x) < ∞, then
P(|x-µ| ≥ ε) ≤ (σ<sup>2</sup>/ε²). The proof for this comes from directly plugging in ε² as α in Markov's, and using Y = (x-µ)² instead of just |x-µ|. 

After these two comes the Weak Law of Large Numbers, which is what allows us to say that the average value of numbers converges to the mean, for the Normal Distribution. Specifically, if x<sub>1</sub>,...,x<sub>n</sub> are iid Normal(µ, σ²), x<sup>-</sup><sub>n</sub> = 1/n ∑<sup>n</sup><sub>i-1></sub> x<sub>i</sub>. Then, ∀ ε > 0, lim<sub>n→∞</sub> P(|x<sup>-</sup><sub>n</sub>-µ| ≥ ε) = 0, so x<sup>-</sup><sub>n</sub>→<sup>P</sup>µ.

The next important theorem we went over was Continuous Mapping Theorem, which states that if h() is a continuous function, then X<sub>n</sub>→<sup>P</sup>X => h(X<sub>n</sub>)→<sup>P</sup>h(X). For example, using WLLN, if h(x) = x², then (X<sup>-</sup><sub>n</sub>)² →<sup>P</sup> µ².

Following convergence in probability, there is also convergence in distribution. This is similar, and states that a sequence of random variables converges in distribution to a single random variable if lim<sub>n→∞</sub> F<sub>X<sub>n</sub></sub>(x) = F<sub>X</sub>(x). Similar to probability, this looks like X<sub>n</sub>→<sup>D</sup>X mathematically.
In words, this means the limit of this sequence of r.v.s converges to the distribution of another r.v. as n goes to infinity.

This is also true for MGFs, and if a sequence of r.v.s X<sub>1</sub>, ... ,X<sub>n</sub> have MGFs M<sub>1</sub>(t), ..., M<sub>n</sub>(t), and X is another r.v. with MGF M(t), then lim<sub>n→∞</sub> M<sub>n</sub>(t) = M(t), <=> X<sub>n</sub>→<sup>D</sup>X.

The Central Limit Theorem was the final big concept covered this week. This states that (X<sup>-</sup><sub>n</sub>-µ)/√(σ²/n) = √n(x<sup>-</sup></sub>n</sub>-µ)/σ →<sup>D</sup> N(0,1).

The proof for this theorem comes from basically putting everything else learned before this into one, and utilizing Taylor series expansions with the MGF as well as lots of algebra to get to the mgf of N(0,1), which shows convergence in distribution via the MGF, as shown before.

Alright, that was a lot for just one class, but it's all very important, possibly the most important takeaways from this class! This is a lot of how statistics all holds together, so it is crucial to any upcoming classes.


