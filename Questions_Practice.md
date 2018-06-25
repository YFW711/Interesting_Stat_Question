Stat Questions
================
Evan YF W.
2018-06-24

### Question 1 - Pr(death with 500 jumps)

Here is to understand two ideas - disjoint & independent

Disjoint: Disjoint events cannot happen at the same time. In other words, they are mutually exclusive. : In math word, A and B are disjoint if P(A∩B) = 0 : P(A or B) = P(A) + P(B) Independence: the probability that one event occurs in no way affects the probability of the other event occurring. : P(A∩B) = P(A) · P(B) : P(A|B) = P(A) or P(B|A) = P(B) : P(A U B) = P(A) + P(B) - P(A ∩ B)

Per this question, we know Pr(death) per each jump would be 0.001 - now we gonna restate the question: We gonna calculate the probability of at least 1 failure among jumps, which is Pr(at least 1 death among 500 jumps). Then we can apply two abovementioned concetps to do the calculation and the idea:

1.  if one considers this as a disjoint case, it would be less precise than the independence case as we exclude the fact the these events could happen in an order, which is true: so here we know the results we get by disjoint idea is more like a expected value to evaluate the worst scenario. Note that even the prob in real case goes over the expected value calculating by joint formula, it doesn't mean it's going to happen. Result1 = 0.001 \* 500 \[\sum_{i=1}^{500}P_i, P_i = 0.001\]

2.  How about independence case? The following provide the logic to identify whether the case is dependent or not. Here just take Pr(Death within 2 jumps)- P(D within 2 J) = 1 - Pr(Survive within 2 J) = 1 - Pr(Survive \#1 ∩ Survive \#2 ) = 1 - Pr(Survive \#1) \* Pr(Survive \#2 | Survive \#1) = 1 - Pr(Survive \#1) \* Pr(Survive \#2), by independence = 1 - 0.999^2 So, we know the result per this case is 1 - 0.999^500 = 0.3936211. From the calculated result, we know this way to get us more precise prediction.

![alt text here](/Users/wangevan/Google%20Drive/Work_Doc/Stat/dependent-or-independent-event.jpg) Source: <http://www.statisticshowto.com/probability-and-statistics/dependent-events-independent/>

### Question 2 - Spoiled drinks

Assume there are 1000 cans of drinks Store B produced 1000 \* 30% = 300 bottles, of which 300 \* 2% = 6 cans spolied Store J produced 1000 \* 20% = 200 bottles, of which 100 \* 2% = 2 cans spolied Store F produced 1000 \* 50% = 500 bottles, of which 500 \* 3% = 15 cans spolied Given a spoiled can is detected, What's the Pr(B | Spoiled)? Pr(B | Spoiled) = P(B ∩ Spoiled) / P(Spoiled) = 6 / (6+2+15)

### Question 3 - Convert PDF to CDF:

2 cases here: One is to convert PDF to CDF, another one is CDF to PDF

Q2.1 First case- f(x) = k(x^2 + x), if 0 &lt;= x &lt;= 1 = 0, else

Q3.1.1. find k Give this integrated pdf = 1, we get: \[\int{k(x_i^2 + x_i)} = 1 \] \[  = k\int_{i=0}^{1}{(x_i^2 + x_i)}dx\] \[  = k(x_i^3 / 3 + x_i^2 / 2)   |_{0}^{1}\] \[  => k(1 / 3 + 1 / 2) = 1 \]

Process 1. pdf = 1 2. get the constant out of integrated part 3. definite integral of a variable raised to a power 4. X = max value 5. get the k

Q3.1.2 find CDF CDF is the area of PDF - we can get it by integrating PDF from infinity to an arbitrary value x If x is in the interval \[0, 1\], then \[F(X) = k\int_{-\infty}^{x}f(t)dt \] \[     = k\int_{-\infty}^{0}f(t)dt + k\int_{0}^{x}f(t)dt \] \[     =        0                  + 5/6(x^3 / 3 + x^2 / 2) \]

Source: <http://blogs.ubc.ca/math105/continuous-random-variables/example/>

### Question 4 - Convert CDF to PDF

Given the CDF, F(X): \[ F(X) = 1 - (\frac{2000}{X + 2000})^3\] As we know the pdf is the first derivative of the cdf, We are going to calculate its PDF and its expected value- \[ \frac{dh(x)}{dx} = \frac{d}{dx} h(x) = \frac{d}{dx} 1 - \frac{2000}{X + 2000}^3 \] then we let u = x + 2000, \[= \frac{d}{du} 1 - (\frac{2000}{u})^3 \frac{du}{dx} \] By the chain rule, we will get \[ = \frac{d}{du}(1 - 2000^3 u^{-3}) * \frac{d}{dx}(x+ 2000)\] then, \[ = ( 3 * 2000^3 * u^{-4}) * 1  = \frac{3 * 2000^3}{(x+2000)^4} \]

Expected value(Long-run average) formula: \[E[x] = \int_{-\infty}^{\infty} x f(x) dx \] Take this as example - f(x) = 1/20 , 0&lt;= x &lt;= 20, \[E[x] = \int_{0}^{20} x \frac{1}{20} dx = [\frac{x^2}{40}]_{0}^{20} = 10 \]

Now back to the questoin, \[E[x] = \int_{-\infty}^{\infty} x f(x) dx = \int_{0}^{\infty} x \frac{3 * 2000^3}{(x+2000)^4} dx \] then adjust it with some tricks here(again let u = x+2000 and x = u - 2000), \[\int_{0}^{\infty} x \frac{3 * 2000^3}{(x+2000)^4} dx (du/du) =  \int_{0}^{\infty}[(u - 2000)\frac{3 * 2000^3}{(u)^4} du (dx/du)] \] and x = 0 correspond to u = 2000, also, since x = u - 2000, dx / du = 1 \[=  \int_{2000}^{\infty}[(u - 2000)\frac{3 * 2000^3}{(u)^4} du (1)] \] \[=  \int_{2000}^{\infty}(...)du \] \[=  (\frac{-3}{2} \frac{2000^3}{u^2} + \frac{2000^4}{u^3}) |_{2000}^{\infty} \] \[=  (\frac{-3}{2} \frac{2000^3}{\infty^2} + \frac{2000^4}{\infty^3}) -(\frac{-3}{2} \frac{2000^3}{2000^2} + \frac{2000^4}{2000^3}) = 0-(-3000+2000)  \]

#### Note for other derivative rules

1.  \[\frac{d}{dx} f(x)g(x) = f`{(x)} g(x) + g`{(x)} f(x) \]
2.  \[\frac{d}{dx} g(x)/f(x) = \frac{g`{(x)} f(x)  - f`{(x)} g(x)}{f(x)^2} \]
3.  \[\frac{d}{dx} exp(x) = exp(x) \]
4.  \[\frac{d}{dx} ln(x) = 1/x \]
5.  \[\frac{d}{dx} g(f(x)) = g`{f(x)} f`{(x)}\] \[                     = \frac{d}{df(x)} g(f(x)) * \frac{d}{dx} f(x)\]
