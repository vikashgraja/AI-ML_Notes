# Probability and Statistics

**Permutations:**
- **Definition:** Arrangement of items in a specific order.
- **Formula:** $\ P(n, r) = \frac{n!}{(n-r)!} $
- **Example:** The number of ways to arrange 3 out of 5 items: $\ P(5, 3) = \frac{5!}{(5-3)!} = 60 $

**Combinations:**
- **Definition:** Selection of items without considering the order.
- **Formula:** $\ C(n, r) = \frac{n!}{r!(n-r)!} $
- **Example:** The number of ways to choose 3 out of 5 items: $\ C(5, 3) = \frac{5!}{3!2!} = 10 $

### Probability Axioms
- **Axiom 1:** $\ P(A) \geq 0 $ for any event $\ A $
- **Axiom 2:** $\ P(S) = 1 $ where $\ S $ is the sample space
- **Axiom 3:** For mutually exclusive events $\ A $ and $\ B $, $\ P(A \cup B) = P(A) + P(B) $

### Sample Space
- **Definition:** The set of all possible outcomes of an experiment.
- **Example:** For a die roll, the sample space $\ S $ is $\ \{1, 2, 3, 4, 5, 6\} $

### Events
- **Definition:** A subset of the sample space.
- **Example:** Event $\ A $ of rolling an even number with a die: $\ A = \{2, 4, 6\} $

### Independent Events
- **Definition:** Two events $\ A $ and $\ B $ are independent if $\ P(A \cap B) = P(A) \cdot P(B) $
- **Example:** Rolling a die and flipping a coin.

### Mutually Exclusive Events
- **Definition:** Two events $\ A $ and $\ B $ are mutually exclusive if $\ P(A \cap B) = 0 $
- **Example:** Rolling a 3 or a 5 on a single die roll.

### Marginal, Conditional, and Joint Probability
- **Marginal Probability:** Probability of a single event occurring, $\ P(A) $
- **Conditional Probability:** Probability of event $\ A $ given event $\ B $, $\ P(A|B) = \frac{P(A \cap B)}{P(B)} $
- **Joint Probability:** Probability of two events occurring together, $\ P(A \cap B) $

### Bayes Theorem
- **Formula:** $\ P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)} $
- **Application:** Used for updating probabilities based on new information.

### Conditional Expectation and Variance
- **Conditional Expectation:** $\ E(X|Y=y) $ is the expected value of $\ X $ given $\ Y = y $.
- **Conditional Variance:** $\ \text{Var}(X|Y=y) $ is the variance of $\ X $ given $\ Y = y $.

### Mean, Median, Mode, and Standard Deviation
- **Mean (μ):** Average of all data points.
- **Median:** Middle value when data points are ordered.
- **Mode:** Most frequently occurring value.
- **Standard Deviation (σ):** Measure of data spread, $\ \sigma = \sqrt{\text{Var}(X)} $.

### Correlation and Covariance
- **Correlation:** Measure of linear relationship between two variables, $\ \rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y} $.
- **Covariance:** Measure of how two variables change together, $\ \text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)] $.

### Random Variables
- **Definition:** A variable whose values are outcomes of a random phenomenon.
- **Types:** Discrete and Continuous.

### Discrete Random Variables and Probability Mass Functions (PMFs)
- **Discrete Random Variable:** Takes specific values.
- **PMF:** Function that gives the probability that a discrete random variable is exactly equal to some value.

### Uniform, Bernoulli, and Binomial Distribution
- **Uniform Distribution:** All outcomes are equally likely, $\ P(X=x) = \frac{1}{n} $.
- **Bernoulli Distribution:** Binary outcome (success/failure), $\ P(X=1) = p $, $\ P(X=0) = 1-p $.
- **Binomial Distribution:** Number of successes in $\ n $ independent Bernoulli trials, $\ P(X=k) = \binom{n}{k} p^k (1-p)^{n-k} $.

### Continuous Random Variables and Probability Density Functions (PDFs)
- **Continuous Random Variable:** Takes any value within an interval.
- **PDF:** Function that describes the likelihood of a random variable to take on a particular value.

### Uniform, Exponential, Poisson, Normal, Standard Normal, t-Distribution, Chi-Squared Distributions
- **Uniform Distribution:** Equal probability across an interval, $\ f(x) = \frac{1}{b-a} $ for $\ a \leq x \leq b $.
- **Exponential Distribution:** Time between events in a Poisson process, $\ f(x; \lambda) = \lambda e^{-\lambda x} $.
- **Poisson Distribution:** Number of events in a fixed interval, $\ P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!} $.
- **Normal Distribution:** Bell-shaped curve, $\ f(x) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}} $.
- **Standard Normal Distribution:** Normal distribution with mean 0 and variance 1.
- **t-Distribution:** Used in hypothesis testing for small sample sizes, similar to normal but with heavier tails.
- **Chi-Squared Distribution:** Sum of the squares of $\ k $ independent standard normal random variables.

### Cumulative Distribution Function (CDF)
- **Definition:** Function that gives the probability that a random variable is less than or equal to a certain value, $\ F(x) = P(X \leq x) $.

### Conditional PDF
- **Definition:** PDF of a random variable given that another random variable takes on a certain value.

### Central Limit Theorem
- **Statement:** The distribution of the sum (or average) of a large number of independent, identically distributed random variables approaches a normal distribution, regardless of the original distribution.

### Confidence Interval
- **Definition:** Range of values used to estimate the true value of a population parameter.
- **Formula:** $\ \bar{x} \pm z \frac{\sigma}{\sqrt{n}} $ for a normal distribution.

### Z-Test
- **Definition:** Test to determine if there is a significant difference between sample and population means.
- **Formula:** $\ z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}} $

### T-Test
- **Definition:** Similar to Z-test but used when the sample size is small and the population variance is unknown.
- **Formula:** $\ t = \frac{\bar{x} - \mu}{\frac{s}{\sqrt{n}}} $

### Chi-Squared Test
- **Definition:** Test to determine if there is a significant association between categorical variables.
- **Formula:** $\ \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i} $ where $\ O_i $ and $\ E_i $ are observed and expected frequencies.
