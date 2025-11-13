Okay, I'm finding that it is kind of difficult to keep up with these blog posts... I've just now finished week 4, and am skipping week 5 to immediately go to week 6. Luckily this week should be short, as two of the classes had midterms in them, so there isn't a lot of lecture material to upload here.

### STATS 200A

This class has my second midterm of the quarter this week! So there is only one lecture to go over, and on top of that, it's just finishing off Poison Processes, which I've already covered in other STATS 270 Lectures from earlier weeks. We went over independent Poisson processes, showing how the independence is similar to that of probabilities. The sum of two Poisson processes, N(t) = N<sub>A</sub>(t) + N<sub>B</sub>(t) ~ Poisson (λ<sub>A</sub> + λ<sub>B</sub>).

We started to go over something new, which are Multivariate Random Variables. These are multiple r.v.s that have a joint cdf or a joint pdf, which is a combined cdf or pdf for all the r.v.s present. There are a few propositions from this, those being the Law of Total PRobability, which allows you to find a specific probability by marginalizing (that is, either summing if discrete or integrating if continuous) over all the other variables. The other proposition is conditional probabilities, which hold similarly to how they do in the single random variable case. 

We ended by going over Independence of Multivariate r.v.s, which is similar to the univariate case, but now it would be: f<sub>X,Y</sub>(x,y) = f<sub>X</sub>(x)*f<sub>Y</sub>(y). You have to be careful here, because two r.v.s are not independent if the bounds of one of them rely on the other. This would make them dependent.

### STATS 210

In this class, we went over multicollinearity for the first lecture, and Categorial Variables for the second lecture. Multicolinnearity is when you have multiple variables that are linear dependence. In more mathematical terms, this means there are constants a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>p+1</sub> that are not all 0, but the sum a<sub>1</sub>x<sub>1</sub>, a<sub>2</sub>x<sub>2</sub>, ..., a<sub>p+1</sub>x<sub>p+1</sub> = 0. This is because the matrix X<sup>T</sup>X is then singular, and thus <u>not</u> invertible. If two variables are highly correlated, then adding one after the other won't have much effect on the total model. 

In order to deal with this, you can use VIF, which is 1/(1-R<sup>2</sup><sub>j</sub>>). If this value is greater than 5, it requires a closer look at the model, and if it is greater than 10 it is problematic to the model as a whole. To deal with this, you can remove some correlated prediction variables, or try to combine into one predictor, such as with an average of two variables, or use PCA / some other dimensionality reduction.

Categorical variables can be either ordered (ordinal) or unordered (nominal). Categorical variables need to be encoded, and there are a few ways to do this. One way is just a binary option, or "flipping the variables on and off". For example, you can have:

 X<sub>ctrl</sub> = 1 if control, 0 o.w. <br>
 X<sub>trt1</sub> = 1 if treatment 1, 0 o.w. <br>
 X<sub>trt2</sub> = 1 if treatment 2, 0 o.w.

The output of this is the difference between each treatment and the control.
The issue with this is that the intercept will be 1 for all points. In order to account for this, one option is to use dummy variables, where you set up to (k-1) dummy vars to represent k categories, and they are not used in the reference category. 

Alternatives to the reference category are removing the intercepts completely. However, this will turn the output into mean for each variable, rather than difference between the variable and control group. This could be useful in its own right if you wanted to know the mean for each variable, but then you aren't comparing them to a control, as the original intention is.

### STATS 270

This class also had a midterm this week. However, since I am just auditing it, I didn't have to take the midterm (woo!). So, just one lecture for this class, which was a continuation of Markov Chains, specifically renewal processes. A renewal process is represented by N(t), and is the number of times the process is in state *j* by time *t*, if j is recurrent and X<sub>0</sub> = j. We can define μ<sub>jj</sub> as the expected number of steps needed to return to state j from state j, which is equal to Σ<sup>∞</sup><sub>n=1</sub> n*f* <sup>n</sup><sub>ij</sub>.  <br>
If μ<sub>jj</sub> < ∞ and j is recurrent, then this is **positive recurrent** <br>
If μ<sub>jj</sub> = ∞ and j is recurrent, then this is **null recurrent** <br>
If state i is either positive or null recurrent, and i ↔ j, then j is respectively positive or null recurrent.

The next topic we covered is what it means for a process to be stationary, which is if the probability distribution {P<sub>j</sub>, j >= 0} for a Markov Chain if P<sub>j</sub> = Σ<sup>∞</sup><sub>i=0</sub> P<sub>i</sub>P<sub>ij</sub>, j >= 0.

We ended the class with going over a lengthy example showing how the Hardy-Weinberg Law is a Markov Chain. This problem considers a large population of individuals, where each individual has a particular pair of alleles, which is either class A or class a. We want to see how previous generations will affect the next generation. Without getting too math-y for the proof, randomly choosing a parent and then randomly choosing one of its alleles is equivalent to just randomly choosing an allele from the total allele population. Essentially, grand parents, great grand parents, etc. don't matter, and the only one that matters is the direct parent, which makes this a Markov Chain, as nothing over than the direct previous event affect the alleles. This can be shown with the transition matrix.

### Personal

Not too much personal stuff happeend this week. I got to see a frined from high school who's attended UCI for a few years now, but I haven't had the chance to hang out with him much. He and some other friends and I went to the Irvine Spectrum, which is a really large outdoor mall, and walked around for a little bit. I don't really think too much else happened personally. Maybe if I remember more later, I will update this section.