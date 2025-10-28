### Week 0

Yes, this story starts at Week 0. School started on Thursday, September 25th, where I had two of my classes. 
The first class was STATS 210, which is titled "Statistical Methods I: Linear Models". This class is an applied stats course, meaning we learn how to interpret data and use coding software such as R.
This class is similar to STAT 525 which I took at Purdue last year, so it is mostly a recap class for me, which isn't necessarily a bad thing, as it can be good to have a refresher as I adjust to grad school.

The next class I had was STATS 280, which is a seminar class where researchers from other places come in to give a brief lecture on their work. The point of this class is to expand my network and exposure to research. The first seminar was abit different however, and it was more of a "State of the Union" speech by our department chair. 

### Week 1

On Monday of Week 1, I had STATS 200A, "Intermediate Probability and Statistical Theory", which is an intro probability course. This class is also similar to a class I have taken before, though the one I took was in sophomore year and at an undergraduate level, so though it is a "recap" course, there are a lot of things I haven't thought of in a very long time, so it might take some extra time and effort to remember all the key aspects of this class. 

After that I had STATS 295 which is a special topics course in Clinical Trials. This class seems interesting and is based on giving a presentation to the class, as well as discussing one other peer's presentation. My presentation date isn't until December, so I'll have time to prepare. The topic I chose was reinforcement learning in a contextualized-bandit approach, and though I'm not entirely sure what that means, the abstract sounded interesting so I decided to choose that one.

My final class is one I'm just auditing, STATS 270, titled "Stochastic Processes."
I decided to audit this class because I understand that stochastic processes are a very important part of statistics, though I didn't want to overload my schedule in my first quarter. This class appears to be the most interesting out of the bunch, though the professor moves at a very quick pace, so it can be somewhat hard to keep up with.

This is just a stream of conscious, but I'm not entirely sure how I want to structure these blogs. I want them to be a kind of weekly recap, but I don't know _how_ I want that to happen. I don't think I necessarily want to do a day-by-day type thing, but maybe just at the end of each week I'll upload and have the headers be the classes? I think that sounds good for me. This first one will be a little off though, because it is a recap of the last 4 weeks, so I think each week I'll just have a little paragraph or something. Not entirely sure...

Because of this, this post might also take a while to write. I have to remember everything and go bakc through my notes, so it mightt take a bit to fully finish. Luckily my midterms are right around now, so maybe while reviewing I will type up what I learned. Also, probably no pictures for this one, just due to the nature of it being so long and different already. I hope to incorporate pictures into the future entries, however. 

In STATS 210, we went over basic statistical concepts, such as assumptions of a linear model and what it means to be an unbiased estimator. We also went over some of the most important parts of linear regression, those being Sums of Squares, which appear a lot in this class. In specific, there are two types: Sum of Squares Regression, (**SSR**) and Sum of Squares Error (**SSR**). \
SSR is variation explained by predictors, and SSE is error that cannot be explained by your model. The sums of these two yield Sum of Squares Total (**SST**). We also went over inference, some distributions, and hypothesis testing. The basics of hypothesist testing are that you want to know if a variable is not significant to your model (i.e., = 0). To do this, you see if a value called the t-statistics falls within an expected range, or if it is unlikely to obtain that value. If the value is "extreme", then it can be said that there is sufficient evidence against the original claim that the value isn't significant. If you fail to reject, you conclude that the variable is 0. \
We also learned about the mean response and prediction of a new value. The difference between these two is that the prediction interval now introduces an error term, eta. This error term is independent of the errors in the original model. The prediction interval has a larger Standard Error than the mean response, which means it also follows that it has a wider confidence interval. This is because the prediction interval is covering the whole range, while the mean response is for one value. Mathematically, the range is wider because there is an added sigma<sup>2</sup> term.

In STATS 200A, We learned basic set theory during the first week. This includes the basics such as union, intersection, complimentation, and difference. Unioning two sets means an element is in set A _or_ in set B. Intersection means an element is in **both** set A and set B. The compliment of a set means that the element is **not** in the set, and the difference of a set means an element is in A but not in B. \
Following this, two sets are disjoint if their union contains the empty set. If there are multiple sets in the universe, then any two are mutually disjoint if their union is the empty set. A partition of the universe is when there are multiple pairwise disjoint sets, and the union of all of them is the universe. \
There are other basic properties of sets, such as the communicative, associative, and distributive property. \
We also went over the rules of what it means to be a probability measure. These are: \
1. P(A) > 0,
2. P(Universe) = 1,
3. If A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub> are pairwise disjoint, then the probability of the untion of all A<sub>i</sub> = the sum of all P(A<sub>i</sub>)

STATS 270 started with a brief overcap of probability -- all stuff that can be found in the 200A recap. We also went over some limit theorems, such as almost sure conjvergence, convergence in probability, and convergence in distribution. These go from strongest to weakest in the order that I have written them. A.S. convergence and convergence in probability are similar, while convergence in distribution looks at the cdf of the functions (I'll explain the cdf when we get there in 200A) \
We then also defined two important theorems: The Law of Large Numbers, and the Central Limit Theorem:\
The Law of Large Numbers states that if x<sub>1</sub>, x<sub>2</sub>,... are iid, with a finite expectation and mean equal to the expected value, then the average of the values is the mean.\
The Central Limit Theorem states that if x<sub>1</sub>, x<sub>2</sub>,... are iid, with mean equal to the expected value and a finite variance, then the data follows a Normal distribution.

We also started learning about stochastic processes, as the name of the course would suggest. A stochastic process is a collection of random variables {x(t) : t in T}, where T is an index set, and t is often referred to as time. The sample space of x(t) is called the state space, and is denoted by S.\
There are discrete state processes, real-valued stochastic processes, d-vector processes, discrete-time stochastic processes, and continuous-time stochastic processes. 

We then moved on to Poisson Processes, which are counting processes. This means we have a stochastic process {N(t): t > 0} where N(t) represents the total number of events that have occurred by time t. Also, Poisson Processes must follow the following properties:\
1. N(0) = 0
2. The process has stationary and incrementing processes
3. P(N(h) = 1) = \(\lambda \) (h) + o(h) for a constant \(\lambda \)
4. P(N(h) = 2) = o(h)

### Week 2


