Okay, I'm finding that it is kind of difficult to keep up with these blog posts... I've just now finished week 4, and am skipping week 5 to immediately go to week 6. Luckily this week should be short, as two of the classes had midterms in them, so there isn't a lot of lecture material to upload here.

### STATS 200A

This class has my second midterm of the quarter this week! So there is only one lecture to go over, and on top of that, it's just finishing off Poison Processes, which I've already covered in other STATS 270 Lectures from earlier weeks. We went over independent Poisson processes, showing how the independence is similar to that of probabilities. The sum of two Poisson processes, N(t) = N<sub>A</sub>(t) + N<sub>B</sub>(t) ~ Poisson (λ<sub>A</sub> + λ<sub>B</sub>).

We started to go over something new, which are Multivariate Random Variables. These are multiple r.v.s that have a joint cdf or a joint pdf, which is a combined cdf or pdf for all the r.v.s present. There are a few propositions from this, those being the Law of Total PRobability, which allows you to find a specific probability by marginalizing (that is, either summing if discrete or integrating if continuous) over all the other variables. The other proposition is conditional probabilities, which hold similarly to how they do in the single random variable case. 

We ended by going over Independence of Multivariate r.v.s, which is similar to the univariate case, but now it would be: f<sub>X,Y</sub>(x,y) = f<sub>X</sub>(x)\*f<sub>Y</sub>(y). You have to be careful here, because two r.v.s are not independent if the bounds of one of them rely on the other. This would make them dependent.

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

This class also had a midterm this week. However, since I am just auditing it, I didn't have to take the midterm (woo!). So, just one lecture for this class, which was on Periods and simple random walks. A Period is the largest integer *d* of state *i* such that all p<sup>n</sup><sub>ij</sub> = 0 whenever n is not a positive integer multiple of d (i.e., n±d, 2d, 3d, ...). A state with period d=1 is called <u>aperiodic</u>.
It can also be shown that if state i has period d, and i ↔ j, then state j also has period d.

We also learned about **recurrent** and **transient** states. For these, we define *f* <sup>n</sup><sub>ij</sub> to be the probability of the first transition into j at time n, given that the process starts in i, (so this is P(X<sub>n</sub> = j, X<sub>k</sub> ≠ j, k = 1, ..., n-1 | X<sub>0</sub> = i)). <br>
State j is recurrent if *f* <sup>n</sup><sub>ij</sub> = 1, <br>
State j is transient if *f* <sup>n</sup><sub>ij</sub> < 1 <br>
It then follows that state j is recurrent if Σ<sup>∞</sup><sub>n=1</sub> p<sup>n</sup><sub>ij</sub> = ∞, and it is transient if Σ<sup>∞</sup><sub>n=1</sub> p<sup>n</sup><sub>ij</sub> < ∞. <br> 
A wordy proof for this is that recurrence means that a process starting in j will eventually return to j. However, by the MArkovian property, it follows that the process restarts itself upon returning to j. Hence, with probability 1, it will return again to j, thus it returns to j infinitely often which leads to the expectation being infinity. If j is transient, the process never returns to j with probability 1- *f* <sup>n</sup><sub>ij</sub> > 0. Hence, the number of visits to j follows a Geometric distribution with mean < ∞,s ot he sum will also be less than infinity.

Moving on to the Simple Random Walk, this is p<sub>i, i+1</sub> = p = 1 - p<sub>i, i+1</sub>. 

### Personal
