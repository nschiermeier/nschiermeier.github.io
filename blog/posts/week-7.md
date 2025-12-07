Well, I did not do a great job of keeping up with these throughout the quarter, so I've switched my objective. It is currently the weekend before finals, so I think I will use this as a way to review and go through my notes. My hope is that typing my notes out in a way that's suitable for this blog will really help me to learn and understand everything. It's also a more engaging way to go through notes than just reading them, which is what I usually do, and I don't feel like that's the most effective way to study.

Due to the time constraint (finals start in just 4 days...) I won't be typing out personal things or STATS 270 notes, since I'm just auditing 270 and want to get through everything for 200A and 210 before the finals actually start.

I think my goal is to do 2 weeks per day (it is currently Saturday) so I can be done before the weekend ends. We'll see how this works out!

### STATS 200A

The first theorem that we learned in class this week was one of the most important: **Linearity**. This theorem states that if we have two Random Variables, X and Y, as well as constants a, b, and c, then the expected value E[aX + bY + c] = aE[X] + bE[Y] + c. The proof for this comes from linearity of integrals, in which we can move constants out of integrals that don't rely on them. (Note to self, I said I would put pictures in these blogs but never did, but this would be a great opportunity to do so, should I want to come back and do that...)
This theorem is very useful in many other ways that will appear very soon.

The next important concept we went over was Mutual Independence. Mutual Independence is when we have a function of many rvs: f(x<sub>1</sub>, x<sub>2</sub>,...,x<sub>n</sub>), and this function equals the pi-sum of them individually, i.e. Π<sup>n</sup><sub>i=1</sub> f(x<sub>i</sub>) = f(x<sub>1</sub>) \* f(x<sub>2</sub>) \* ... \* f(x<sub>n</sub>).
From this, we also get that the expected sum of values is equal to the sum of expected values of mutually indep. r.v.s (this stems from linearity!), as well as the MGF of a sum of r.v.s being equal to the sum of MGFs.
The proofs for these again come from linearity, as well as definitions of expectations and pi-sums.

The next concept we went over is also very important, and it was Conditional Expectation / Variance. The conditional expectation of Y given X would be E[Y|X=x], and the conditional variance of that would be Var(Y|X=x). 
For the expectation, in the continuous case this is equal to the integral of g(Y) \* f<sub>Y|X</sub>(y|x) dy, and it is similar for the discrete case as well for some function g(Y) and f(y|x).
We learned previously that Var(X) = E[x<sup>2</sup>] - (E[x])<sup>2</sup>, so it also holds that Var(Y|x) = E[Y<sup>2</sup>|x] - (E[Y|x])<sup>2</sup>. Uses for these conditional expectations and variances come from mixture distributions, where you have two different distributions used while model one problem.
An important calculation that can be made from this is rearranging to solve in terms of expectations: E[Y<sup>2</sup>|x] = Var(Y|X) + (E[Y|x])<sup>2</sup>.

Another concept that stems from this is iterative expectation, which is that E[X] = E[E[X|Y]], or more generally, E[E[g(x)|Y]]. (Note to self, another great place to put the picture of the proof...)

The second lecture of this week also focussed on the conditional variance, and was started off with the Law of Total Variance. This law states Var(X) = E[Var(X|Y)] + Var(E[X|Y]). Again, expanding the variance formula and using iterative expectation, we can get Var(X) = E[E[X<sup>2</sup>|Y]] - (E[E[X|Y]])<sup>2</sup>. The proof for this one (maybe picture...) comes from the rearranging of the conditional variance formula that was given above, and expanding other expectations to get what we want.

The rest of this class was just a lot of examples that I don't want to paste here, so I will move on to the next class.

### STATS 210

Well, this is anticlimactic... The first lecture of STATS 210 this week was canceled due to Veteran's Day holiday, and the second one was canceled by the lecturer, so there isn't actually anything to put here for week 7. Week 8 will be longer for this class as a result.
