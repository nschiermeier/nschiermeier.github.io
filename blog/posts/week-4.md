## Week 4

This post is coming in rather late, as I am trying to catch up on the first 4 weeks and stay current at the same time. I thnink the easiest thing would just be to create these posts as soon as possible, so then I don't forget about what happened and will be able to keep track of everything.

### STATS 200A

In STATS 200A this week, we continued discussing variable transformations and then started to discuss Expectations and Moment Generating Functions. In terms of variable transformations, we went over how the Cauchy distribution is obtained, by taking a Uniform Distribution from (-π/2, π/2) and then transforming it via the tangent function. By doing this, you can obtain the result of 1/(π(1+y^2)) which is the Cauchy distribution, which is important for statistical machine learning.

We also discussed expectations of functions. The expectation, on a basic level, is multiplying the sum of the distribution by x in a discrete case and multiplying the integral of the distribtuion by x in a continuous case, and is represented as E[x]. This is a basic way to obtain the expectation of a distribution, and it is useful to us because the expected value of a distribution is it's mean, 

We next went over Moments and Moment Generating Functions. The n-th moment of a function is the n-th expected value, or E[x<sup>n</sup>]. This is found in a similar way to the expectation, as now you multiply by x<sup>n</sup> rather than just x. From the above paragraph, it then follows that the first moment is just E[x], which is the mean of the distribution. You can then find E[x<sup>2</sup>], which is useful in finding the Variance of a distribution, which can be computed as E[x<sup>2</sup>]-(E[x])<sup>2</sup>.

The Moment Generating Function then, is M<sub>x</sub>(t) = E[e<sup>tx</sup>], and found the same as previously. The way that these are useful is that e<sup>tx</sup> can be represented as a Taylor Series expansion at 0. By having the MGF, we can find the n-th moment of any distribution by taking the n-th derivative of the MGF and solving for 0 at that point. This is useful because it is easier to calculate than just finding a formula for the n-th moment.

## STATS 210

In the Linear Regression Class, we went over inference for Multiple Linear Regression. This expands on how we estimate parameters using matrices for multiple values. The arguably most important formula is how you find <b>y^</b>, which is <b>X</b>(<b>X</b><sup>T</sup><b>X</b>)<sup>-1</sup>)<b>X</b><sup>T</sup><b>y</b> . The part before the <b>y</b> is called the Hat Matrix, which has two important properties: it is idempotent, meaning H<sup>T</sup> = H, and it is symmetric, meaning H<sup>2</sup> = H.
When doing a hypothesis test on these, you are testing that β<sub>1</sub>=β<sub>2</sub>=...=β<sub>k</sub>=0 against the alternative that at least one is not 0. This follows an F distribution with degrees of freedon p, n-(p+1).

We then went into more details on the F-test when comparing the full model to a reduced model. The reduced model follows your null hypothesis, so it just looks like y<sub>i</sub> = β<sub>0</sub> + ε<sub>i</sub>, since that is the only beta we are not testing to be 0 or not. We went a little into extra sum of squares, which is seeing how much our sum of squares will increase or decrease given the other variables are already in the model. This is done by looking at 

SSR(set2|set1) = SSR(set1 & set2) - SSR(set1) = SSE(set1) - SSE(set1 & set2)

For this, we use a partial F-test, which tests the whole model vs the explained model.

## STATS 270

TBD

## Personal

In terms of personal things, this week was the first week I met with my mentor! I thought the meeting went well, it's nothing formal, so just talking about whatever's going on at the time for about 30 minutes. I think it will be helpful to have a mentor who has been through the first two years already so that I can recieve guidance as needed. Other than this, I went home for a day over the weekend so I got to see my parents and my cat. 
