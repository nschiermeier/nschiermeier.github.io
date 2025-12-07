You know, I realized I should probably somewhere put the dates of the weeks that these classes actually were, because right now I'm just putting the date I write these blogs. I'll have to go back and edit a bunch, but I think that might be good info to have. I'll also have to decide where to put it. But, here is week 8 (11/17/2025 - 11/20/2025)

### STATS 200A

This week, we focussed on Functions of Multivariate r.v.s and Bivariate Transformations. For the functions of multivariate r.v.s, it was mostly just examples given, so I'll try to explain them how I understood what we were doing. 
Essentially, we are given two random vars that follow a distribution, and then we want to know the resulting distribution if we do something like adding, dividing, taking the minimum of, or even expressing them in terms of other variables. To solve these, the first step is to write the probability (which is given as a function of the new variables) in terms of the old variables. This could be as simple as plugging them in, or rearranging terms mathematically. 
Once the variables have been rearranged, the pdf/pmf can be used if it is known. From there, the problem can be solved / simplified accordingly. 

The next topic, **Bivariate Transformation**, is defined as follows: if X,Y are continuous & assume g<sub>1</sub>(X,Y) and g<sub>2</sub>(X,Y) are one-to-one from A and B, with the inverse functions X=h<sub>1</sub>(U,V), Y=h<sub>2</sub>(U,V), with the Jacobian matrix (photo here?), then 
*f*<sub>U,V</sub>(u,v)=*f*<sub>X,Y</sub>(h<sub>1</sub>(u,v), h<sub>2</sub>(u,v)) \* ||J||

Note: ||J|| is the absolute value of the determinant of J.

In words, this allows us to take a function of two variables and transform them into terms of two other variables that are functions of the first two variables. This can help with complex continuous distributions where the calculations are too complex to just compute.

The second lecture of this class went over ordered statistics. The ordered statistic represents the number of elements smaller than the current element in a list, for example X<sub>(1)</sub> = min{x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>}, X<sub>(n)</sub> = max{x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>}, so X<sub>(k)</sub> is the kth smallest element. The distribution of X<sub>(1)</sub> = 1-(1-F(t))<sup>n</sup>, the distribution of X<sub>(n)</sub> = (F(t))<sup>n</sup>, and the distribution of X<sub>k</sub> is really long and has a lot of combinatitorics so I'll just explain the intuition behind it: essentially, we're trying to find the k<sup>th</sup> smallest variable. From this, it follows that we have (k-1) ordered stats smaller than our current one, and (n-k) ordered statistics larger than the current one. These are not necessarily ordered, so we have to choose a probability to represent this.  

### STATS 210

In this class, we went over interaction effects, as well as Model Selection. Up to this point, we have been using additive models, so for E[Y] = β<sub>0</sub> + β<sub>1</sub>x<sub>1</sub> + β<sub>2</sub>x<sub>2</sub>, this is interpreted as "an increase in x<sub>1</sub> *or* x<sub>2</sub> will result in an increase in β<sub>1</sub> or β<sub>2</sub> while **holding the other one constant**". Essentially, the effect of x<sub>1</sub> on y does *not* depend on the value of x<sub>2</sub>, and vice versa. If one of these is a categorical predictor, the slopes are the same, and the only thing that changed between them would be the intercept. However, this is not entirely realistic in most settings, and often two variables will have interactions with eachother. 

n an interaction effects model, we now have the term β<sub>3</sub>(x<sub>1</sub>+x<sub>2</sub>). Now, and increase in x<sub>1</sub> will increase β<sub>1</sub>+β<sub>3</sub>x<sub>2</sub> when holding x<sub>2</sub> constant. Because of this interaction effect, the slopes are no longer the same. This also now warrants an F-test to test for significance, since we can look at a model with interaction as a full model, and the model without interaction as a reduced model.

For this F-test, we now want to test H<sub>0</sub>: β<sub>1</sub> = β<sub>3</sub> = 0 to see if x<sub>1</sub> has any effect directly or through interaction with x<sub>2</sub>. Note that this setup can be a little confusing, as we're not testing if the betas are equal, so another way to think about this would be that we are testing β<sub>1</sub> = 0 **and** β<sub>3</sub> = 0.

Increasing this to two categorical variables also increases the number of dummy variables required to two. Also for this, β<sub>0</sub> is meaningful, because it is the sample mean for the reference group (as opposed to in the one categorical variable case, seen in Week 5). The total number of coeficients is i \* j, because we have (i-1) for the first factor, (j-1) for the second factor, (i-1) \* (j-1) from the interaction, and one for the intercept. Adding all those together will just leave i\*j. 

Moving on to Model Selection, we start with our full model that has P predictors, and also have a reduced model with 0<=p<=P predictors. The most basic way to evaluate the model performance is through R<sup>2</sup><sub>p</sub> while trying different models, but the issue with this is that it usually gets higher with an increased number of parameters. Because of this, there are a few other model selection criteria that penalize for having an increased number of predictors:

- Adjusted R<sup>2</sup>: (1-R<sup>2</sup><sub>p</sub>) \* (n-1)/(n-p-1) , higher is better
- Mallow's CP: (SSE<sub>p</sub>/MSE<sub>p</sub>) \* 2(p+1) , want this to be about p+1
- AIC: nlog(SSE<sub>p</sub>/n) + 2(p+1), smaller is better
- BIC: nlog(SSE<sub>p</sub>/n) + (p+1)\*log(n), smaller is better
- PRESS: Σ<sup>n</sup><sub>i=1</sub>(y<sub>i</sub>-y^<sub>i(-i)</sub>)<sup>2</sup> , which i leave-one-out cross validation.

There are also ways to "automatically" select these in a programming language like R. There's forward selection, which starts with no predictors then continues adding them until a certain threshold is met, backwards selection, which starts with all predictors and removes them until a certain threshold is met, and stepwise, which is a combination of both.


### Personal
I'm not going to write this out now, but say something here about the Lab Fair 
