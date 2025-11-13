Well, I accidentally wrote the STATS 270 Lecture in week 6, so I'm moving it here now. I'll see if I get around to fixing that later or not...



### STATS 200A



### STATS 210



### STATS 270



Periods and simple random walks. A Period is the largest integer \*d\* of state \*i\* such that all p<sup>n</sup><sub>ij</sub> = 0 whenever n is not a positive integer multiple of d (i.e., n±d, 2d, 3d, ...). A state with period d=1 is called <u>aperiodic</u>.

It can also be shown that if state i has period d, and i ↔ j, then state j also has period d.



We also learned about \*\*recurrent\*\* and \*\*transient\*\* states. For these, we define \*f\* <sup>n</sup><sub>ij</sub> to be the probability of the first transition into j at time n, given that the process starts in i, (so this is P(X<sub>n</sub> = j, X<sub>k</sub> ≠ j, k = 1, ..., n-1 | X<sub>0</sub> = i)). <br>

State j is recurrent if \*f\* <sup>n</sup><sub>ij</sub> = 1, <br>

State j is transient if \*f\* <sup>n</sup><sub>ij</sub> < 1 <br>

It then follows that state j is recurrent if Σ<sup>∞</sup><sub>n=1</sub> p<sup>n</sup><sub>ij</sub> = ∞, and it is transient if Σ<sup>∞</sup><sub>n=1</sub> p<sup>n</sup><sub>ij</sub> < ∞. <br> 

A wordy proof for this is that recurrence means that a process starting in j will eventually return to j. However, by the MArkovian property, it follows that the process restarts itself upon returning to j. Hence, with probability 1, it will return again to j, thus it returns to j infinitely often which leads to the expectation being infinity. If j is transient, the process never returns to j with probability 1- \*f\* <sup>n</sup><sub>ij</sub> > 0. Hence, the number of visits to j follows a Geometric distribution with mean < ∞,s ot he sum will also be less than infinity.



Moving on to the Simple Random Walk, this is p<sub>i, i+1</sub> = p = 1 - p<sub>i, i+1</sub>, i = 0, ±1, ±2, ..., 0 < p < 1. Since all processes communicate, they are either all transient or all recurrent. 





### Personal

